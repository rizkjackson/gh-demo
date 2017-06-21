<div class="alert alert-warning" role="alert">
To get access to the below software, see Configuration / <a href="{{ '/configuration/cbc-shared-software.html' | relative_url }}">Enable CBC-shared Software</a>.
</div>

# CBC-shared Software

Whenever we in the [Computational Biology Core (CBC)](http://cbc.ucsf.edu/) installs and/or update scientific software, we do it such that it can be shared with everyone.


## The `cbc` command-line tool (deprecated)
The `cbc` command-line tool is part of the CBC setup (otherwise accessible via `/home/shared/cbc/bin/cbc`) is useful tool for listing CBC installed software and utility scripts.

```sh
$ /home/shared/cbc/bin/cbc
Computational Biology Core (http://cbc.ucsf.edu) bash toolkit

Usage:
 cbc [options] <command>

Commands:
 -a | --aliases   : List aliases shared by CBC
 -c | --cluster   : Display current cluster status
 -e | --envvars   : List environment variables set by CBC
 -f | --functions : List shell functions created by CBC
 -h | --help      : Display this help
 -m | --motd      : Display the "message of the day" again
 -s | --software  : List software shared by CBC
 -u | --utils     : List command-line utilities created by CBC

Example:
 cbc -s

How to install:
Add the following to your ~/.bashrc script:
 source /home/shared/cbc/bashrc
```


## Details on shared software
Several cluster users, including us at CBC, install software tools ourselves as plain users.  Sometimes the exact same software version is installed by different users.  In order to minimize the overall work, we at CBC decided several years ago to link to all known software installation available from different users.  These links are available under `/home/shared/cbc/software/`.  For instance, here are all available bedtools versions:
```sh
$ ll /home/shared/cbc/software/ | grep bedtools
lrwxrwxrwx 1 henrik cbc 46 Dec  2 08:32 bedtools2-2.13.4 -> /home/jocostello/tools/BEDTools-Version-2.13.4
lrwxrwxrwx 1 henrik cbc 29 Dec  2 08:35 bedtools2-2.15.0 -> /opt/BEDTools/BEDTools-2.15.0
lrwxrwxrwx 1 henrik cbc 29 Dec  2 08:35 bedtools2-2.16.2 -> /opt/BEDTools/BEDTools-2.16.2
lrwxrwxrwx 1 henrik cbc 46 Dec  2 08:28 bedtools2-2.26.0 -> /home/shared/cbc/software_cbc/bedtools2-2.26.0
lrwxrwxrwx 1 henrik cbc 16 Dec  2 14:48 bedtools2-latest -> bedtools2-2.26.0
```
The naming convention is such that it is easy to see what the different versions are and there's always a `*-latest` version that links to the most recent version installed.

Note that nothing is installed under `/home/shared/cbc/software/` per se.  Instead, the different versions may be installed in different locations on the file system. For instance, some versions may be centrally installed (under `/opt/local/bin/`) whereas others are installaed by individual users or by us in the CBC group.  Regardless where they are installed, this setup is such that you can use `/home/shared/cbc/software/` as the go-to folder to check for available shared software before installing them yourselves.

By calling `source /home/shared/cbc/bashrc` (for instance in `~/.bashrc`), the paths to the `*-latest` of many of the above shared software tools are added to the `PATH` environment variable.  This way one will get automatic access to the latest versions of most of these tools.  For details on exactly how the `PATH` etc is setup, see script [/home/shared/cbc/bashrc](https://github.com/UCSF-CBC/TIPCC-Tools/blob/master/cbc/shared/bashrc) on the cluster.

[Enable CBC-Shared Software]: {{ '/configuration/cbc-shared-software.html' | relative_url }}

