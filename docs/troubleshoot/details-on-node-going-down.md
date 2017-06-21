## Introduction
The `monitor` account is used for automated gathering performance logs on the master, the compute nodes and the scheduler (the queue).  The logs, which are available to all cluster users, are stored under `~monitor/logs/`.

## When did a node go down
The `~monitor/cron/master/c4-status` script is run regularly and logs to `~monitor/logs/<YYYYMMDD>/master/c4-status.log`.  For instance, assume that node n13 went down recently.  Then you can scan these log files for when it was first reported down, e.g.
```sh
$ grep -B 5 -E ".*13.*[ ]+down" ~monitor/logs/20160829/master/c4-status.log
[...]
TIMESTAMP: 20160829-09:03:01
# Cluster status

## Nodes
Node(s)                        Status       Mode       User        Group
13,19,24-25                    down         ---------- root        root       
--
TIMESTAMP: 20160829-18:33:01
# Cluster status

## Nodes
Node(s)                        Status       Mode       User        Group
13,19,24-25                    down         ---------- root        root       
--
TIMESTAMP: 20160829-19:03:02
# Cluster status

## Nodes
Node(s)                        Status       Mode       User        Group
13,19,24-25                    down         ---------- root        root       
--
[...]
```
This tells us that n13 was "down" 2016-08-29 at 09:03 and then down again at 18:33 the same day, and from there on it remained down.


## Jobs running when a node went down
The `~monitor/cron/queue/qstat` script runs `qstat -t -n -1` regularly and logs to `~monitor/logs/<YYYYMMDD>/queue/qstat.log`.
Say node n13 went down around 18:30 on 2016-08-29 (example above).  Then we can extract the log from this file for this date starting around 18:00-18:59 using:
```sh
$ grep -A 10000 -E "20160829_1[8]" /home/henrik/cron-bin/logs/stats-qstat.log > /tmp/qstat.log
```
and then search for what jobs were running on `n13` during this time:
```sh
$ grep -F n13 /tmp/qstat.log
```
Looking at this output we can see which jobs was running and by whom before and at the time of the node was going down.  There's also some info on some of the `qsub` parameters used, e.g.
```r
                                                                                  Req'd    Req'd       Elap
Job ID                  Username    Queue    Jobname          SessID  NDS   TSK   Memory   Time    S   Time
----------------------- ----------- -------- ---------------- ------ ----- ------ ------ --------- - ---------
[...]
507988.cclc01.som.ucsf  johndoe     batch    rna.rsem_count   276528     1     12    1gb  72:00:00 R  15:11:15   
```
