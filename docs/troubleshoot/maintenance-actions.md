# Head Node Troubleshooting

## Inspect head-node processes

The `c4 head` command reports on (i) the five _non-user_ processes that consumes the most memory on the head node as well as (ii) any _user_ processes running on the head node (excluding basic ones such as `ls`, `more`, `cp` etc.)
 
```sh
$ c4 head
# Head-Node Status

## High-memory non-user processes
USER	PID	%CPU	%MEM	PROCESS
root	381362	21.3	44.9	/opt/moab/sbin/moab
root	5682	2.4	1.7	/usr/sbin/pbs_server
tomcat	3984	52.7	1.2	/usr/java/jdk1.7.0_72/bin/java
root	3455	0.0	0.1	java
mysql	3730	24.0	0.1	/usr/libexec/mysqld

## User processes (excl. white-listed ones)
alice [Alice Aliceson (alice@honeypot.ucsf.edu)]:
PIDs (on the head node): 87013
USER        PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
alice    87013  0.0  0.0 100944   104 pts/77   S+   Sep27   0:00 tail -f pilot.minfi.R.out

bob [Bob Bobson (bob@honeypot.ucsf.edu)]:
PIDs (on the head node): 514934
USER        PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
bob      514934  0.0  0.3 789660 403548 pts/51  S+   Sep16   1:05 /opt/R/R-3.2.0/lib64/R/bin/exec/R
```
