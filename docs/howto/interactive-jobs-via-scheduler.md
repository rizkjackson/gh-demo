# Interactive jobs via scheduler

You can use node n6 (`ssh n6`), for simple interactive prototyping, low-load installations etc., but if you need to run large _interactive jobs_, please let the scheduler allocate the resources that you need.

## Request interactive shell
Using option `-I` (upper case i) will tell `qsub` that you want an _interactive job shell_, e.g.
```sh
{cclc01}$ qsub -I
qsub: waiting for job 693822.cclc01.som.ucsf.edu to start
qsub: job 693822.cclc01.som.ucsf.edu ready
{n3}$: echo $PBS_NUM_PPN  ## Maximum number of parallel tasks
1
{n3}$: 
```
This will give a single-core slot on any machine that the scheduler finds suitable (here it happened to be `n3`).  From here on you can use the terminal as a regular terminal.  Your job is listed by `qstat -u $USER` just like any other jobs.  As soon as you log out, the job will be freed. 


## Request interactive shell for high-memory multi-core processing

To run multi-core processes interactive, you can request more cores.  Likewise, you can specify memory needs and other resources.  For instance, if you need four cores and 10 GiB of RAM, use:
```sh
$ qsub -I -l nodes=1:ppn=4 -l vmem=10gb
qsub: waiting for job 693829.cclc01.som.ucsf.edu to start
qsub: job 693829.cclc01.som.ucsf.edu ready
{n2}$: echo $PBS_NUM_PPN  ## Maximum number of parallel tasks
4
{n2}$: 
```

