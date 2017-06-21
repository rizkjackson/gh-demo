## Permission denied (publickey).
Do you get
```sh
$ ssh n6
Permission denied (publickey).
```
when you try to log into node n6 from the head node?  In order to be able to log in to node n6, you need to have ssh public-private keys set up properly.  This should have been done for you already, but if for some reason it does not work, here is how you can fix it.

First, make sure that your `~/.ssh/authorized_keys` can only be read by you.  It should look like this:
```sh
$ ls -l  ~/.ssh/authorized_keys
-rw------- 1 johndoe cbc 5941 Apr 12 07:07 /home/johndoe/.ssh/authorized_keys
```
where `-rw-------` says you (and only you) have read and write permissions to this file.   If you see any other letters where the dashes are, make sure to reset the file permissions to the above, which you can do by:
```sh
$ chmod go-rw ~/.ssh/authorized_keys
```
Try to log in to node n6 again, i.e. `ssh n6`.

If the above wasn't the problem or didn't help, then regenerate a new pair of ssh keys _and_ append them `~/.ssh/authorized_keys`.  This can be done as:
```sh
$ ssh-keygen
$ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
```
Again, make sure the file permissions are correct.  Then retry with `ssh n6`.