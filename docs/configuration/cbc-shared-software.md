<div class="alert alert-warning" role="alert">
The below configuration instructions will soon be deprecated in favor of using <code>module load cbc-shared</code>.  To make use of the latter, see <a href="{{ '/software/modules.html' | relative_url }}">software environment modules</a>.
</div>

# Enable CBC-shared Software (instructions soon to become deprecated)

Whenever we in the [Computational Biology Core (CBC)](http://cbc.ucsf.edu/) installs and/or update scientific software, we do it such that it can be shared with everyone.  You can find them all under `/home/shared/cbc/software/`.

To get access to the CBC-shared software tools and settings, add
```sh
source /home/shared/cbc/bashrc
```
to your `~/.bashrc` script _after_ the if statement that call to `/etc/bashrc`.  After starting a new shell (e.g. logging in and out), you should have access to all CBC-shared software and utilities.

As an example, here is what `~/.bashrc` may look like after adding the above:
```sh
if [ -f /etc/bashrc ]; then
	. /etc/bashrc
fi
source /home/shared/cbc/bashrc
```


_Warning_: Do *not* put it `~/.bash_profile` because that is only sourced in interactive mode, i.e. it will not work for submitted jobs etc.
