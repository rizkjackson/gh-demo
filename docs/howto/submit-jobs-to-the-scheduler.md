Our compute cluster uses the TORQUE/PBS standard for submitting, listing and killing jobs.

_If you have any tips, tricks or suggestions, please add them below._

## Submitting jobs

Submitting a job as a shell script:
```sh
qsub script.sh
```
You can pass arguments that can be parsed by the script using `$*`, `$1`, `$2`, ..., by specify `-F` after your script, e.g.
```sh
qsub script.sh -F first second third
```
Arguments are then passed as if you called the script as `script.sh first second third`.  Note that `-F` is consumed by `qsub` and is not seen by `script.sh`.


### Request a specific node (rarely needed)
Request to work on a specific node (using one core; the default):
```sh
qsub -l nodes=n23 script.sh
```

### Request number of cores for parallel processing
Request to get a single node (any one) with at least four cores available:
```sh
qsub -l nodes=1:ppn=4 script.sh
```

**NOTE**: Please do **not** use `-l procs=4` for this; it does _not_ work and will still allocate / give you a single core (which can be seen from `qstat -n -1`).

Request to work on a specific node using eight of its cores:
```sh
qsub -l nodes=n26:ppn=8 script.sh
```

### Request total and maximum amount of memory to be used

Request one node with one task consuming up to 8 GiB of RAM:
```sh
qsub -l vmem=8gb script.sh
```
Valid units are `kb`, `mb` and `gb`, which are specified in IEC units (multiples of 1024, e.g. 1 GiB = 1024 MiB = 1024^2 KiB = 1024^3 bytes).  It is _not_ possible specify memory sizes using decimal numbers - only integers.  For instance, `vmem=7.5gb` will give an error on submission.  Instead, one can use `vmem=7680mb` (because 7.5 GiB = 7.5*1024 MiB = 7680 MiB).

Request one node with 12 tasks together consuming up to 96 GiB of RAM (e.g. 11 tasks could use 1 GiB each and one task 85 GiB):
```sh
qsub -l nodes=1:ppn=12 -l vmem=96gb script.sh
```

If TORQUE (the scheduler) detects a job (one or more processes) that is using more memory than it requested (by `vmem`), it will [terminate the job process by signalling `SIGTERM` ("Ctrl-C") and write a message to standard error](
https://github.com/adaptivecomputing/torque/blob/f1a292619d9744d864411f8ad79f4da1be78d0d7/src/resmom/mom_main.c#L5687-L5716), e.g.
```sh
=>> PBS: job killed: vmem 92954931200 exceeded limit 86973087744
```
This messages says that PBS killed the job because it used 92,954,931,200 bytes (= 86.6 GiB), which is more than the requested 86,973,087,744 bytes (= 81 GiB; `vmem=81gb`).

_Note_: We _highly recommend_ to specify `vmem` rather than `mem`.  Both will find a node that meets your memory requests, but it's only `vmem` that enforces it (which is a good thing in the end of the day).  


## Listing jobs
All jobs on the system including those from other users:
```sh
qstat
```
To get information where the jobs are running, use:
```sh
qstat -n -1
```
Same information on your jobs only:
```sh
qstat -n -1 -u $USER
```


## Killing jobs
To kill a specific job:
```sh
$ qstat -u $USER  => Identify all of your jobs and their job ids (an integer)
$ qdel <jobid>
```
Comment: `qdel` does not give any output confirming that the job was actually deleted.  In other words, no output often means that it works.  It might take some time before the job is actually terminated and therefore it will take a few moments before it disappears from the `qstat` output.

To kill _all_ of your submitted jobs:
```sh
$ qdel all
qdel: Unauthorized Request  MSG=operation not permitted all
```
Comment: In this case `qdel` gives that somewhat misleading message, because _all_ of your jobs are indeed deleted if you use this command.


## Error 'qdel: Server could not connect to MOM'
Sometimes the compute node where you job is running is extremely overloaded to the point that it might even be reported as "down" by `pbsnodes`.  However, it might still be that the machine is running (i.e. it responds to `ping`) but is so clogged up that it is very slow responding to outside requests.  One such request is `qdel`.  When you try to kill a job that is running on an overloaded node, you might get the following error:
```sh
$ qdel 520437
qdel: Server could not connect to MOM 520437.cclc01.som.ucsf.edu
```
This means that `qdel` failed to send the signal that would kill the job.

If this happens, you could try to login (e.g. `ssh n15`) to the node itself and use the `kill` command to kill one or more of your processes.  In order to do this, you need to identify the process ID for your job, which is not the same as the job ID.  Instead it is the same as the session ID, so look for that in the output of `qstat`.  For example, in order to _kill_ the process for job '523813' we can do: 
```sh
$ qstat -n -1 -u $USER

cclc01.som.ucsf.edu: 
                                                                                  Req'd    Req'd       Elap
Job ID                  Username    Queue    Jobname          SessID  NDS   TSK   Memory   Time    S   Time
----------------------- ----------- -------- ---------------- ------ ----- ------ ------ --------- - ---------
523813.cclc01.som.ucsf  cbctest     batch    echo_152617-2016 242728     1      1    --   99:23:59 R  00:01:33   n2/34
523814.cclc01.som.ucsf  cbctest     batch    echo_152618-2016 242741     1      1    --   99:23:59 R  00:01:33   n5/5
523815.cclc01.som.ucsf  cbctest     batch    echo_152618-2016 242757     1      1    --   99:23:59 R  00:01:33   n2/45
```
and there we see column `SessID`.  For job '523813', we see that the session ID is '242728'.  We also note that this job / process is running on node n2.  Now with this information we can, from the head node, terminate this process on n2 using:
```sh
$ ssh n2 kill -TERM 242728
```
The `-TERM` option sends a "terminate" signal to the process, which gives the running software a chance to capture this and nicely quit (e.g. some software might save the current state to file, but not all).  If it doesn't work to ask the process to terminate this way, you can always go harder at it and call: 
```sh
$ ssh n2 kill -KILL 242728
```
That will just kill the process without asking (it) first.

Comment: Note that if the node is extremely overloaded, calling the above `ssh` commands might take several minutes before the node even responds and the `kill` command can be completed.  So, be patient. On the other hand, this should only be needed in extreme cases.
