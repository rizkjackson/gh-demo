# HOW TO: Troubleshoot cluster performance

## Identify what processes runs

### All processes on the cluster
```sh
ps uax | bpstat -P
```

### All processes on a particular node
For example, node \#17:
```sh
ps uax | bpstat -P | grep -E "^17 "
```

### All processes on the head node
All processes on the head node (i.e. those without a node assignment in the first column):
```sh
ps uax | bpstat -P | grep -E "^  "
```
All processes on the head node by a certain user:
```sh
ps uax | bpstat -P | grep -E "^  " | grep cbctest
```
A bit cleaner:
```sh
user=cbctest
ps uax | bpstat -P | grep -E "^  " | grep -v "grep $user" | grep -v root | grep $user
```

All processes on the head node by all users:
```sh
users=$(cat /etc/passwd | grep -F "/home/" | grep -E "(@|inactive)" | cut -d':' -f1)
for user in $users; do echo $user:; ps uax | bpstat -P | grep -E "^  " | grep -v "grep $user" | grep -v root | grep $user; done
```
