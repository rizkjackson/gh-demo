## Cleanup temporary disk usage on each node

If you have no jobs running, you can run the following to clean out all _your_ files have on the temporary disks on the head node and on each of the nodes:
```sh
$ /home/shared/cbc/bin/clean_tmp --cleanup
```

To inspect how much total temporary disk space are used (everyone's files), do:
```sh
$ /home/shared/cbc/bin/clean_tmp --usage
```

**TIPS**: It's recommended to set `$TMPDIR` to your own subdirectory.  If you're already using the [CBC-shared Software] setup, this is already done for you.  Otherwise, add the following to your `~/.bashrc/` startup script:
```bash
export TMPDIR=/tmp/$USER
mkdir -p $TMPDIR
```

[CBC-shared Software]: {{ '/configuration/cbc-shared-software.html' | relative_url }}
