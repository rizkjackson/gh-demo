# Software Environment Modules (BETA)

Since December 2016, we support [software environment modules](https://en.wikipedia.org/wiki/Environment_Modules_(software)), but since they are **currently in beta, users need to change their settings to be able to use them** - for instructions, see Section 'Enable Lmod modules' at the end.

To see the set of available software, see Page [Software Available Modules](https://github.com/UCSF-TI/TIPCC/wiki/Software-Available-Modules).

## Introduction

Modules has been around since early 1990s and provides a straightforward way for users to specify exactly what software tools they need in a particular analysis.  For instance, if you or your script needs Samtools, then call:
```sh
$ module load samtools
```
When we load a module, the default is that get access to the most recent version installed on the system, e.g.
```sh
samtools --version
samtools 1.3.1
Using htslib 1.3.1
Copyright (C) 2016 Genome Research Ltd.
```
You can access older versions of the software as well.  This is one of the rationales for using modules.  Whenever you request another version, the old module will automatically be unloaded.  For instance, if we later do:
```sh
$ module load samtools/1.2

The following have been reloaded with a version change:
  1) samtools/1.3.1 => samtools/1.2
```
we'll now have access to version 1.2 of Samtools instead:
```sh
$ samtools --version
samtools 1.2
Using htslib 1.2.1
Copyright (C) 2015 Genome Research Ltd.
```

## Under the hood ("no magic")

When loading a module, various environment variables, notably `PATH` and `LD_LIBRARY_PATH`, are updated such that your current shell environment finds the software and the version you asked for.  That's the main feature of modules - instead of having to tediously and manually edit those environment variables and making sure their search paths are in the correct order, the module framework will do it for us.  Another advantage is that we don't have to know or specify where the different software tools are installed - all we need to know are their names.  This makes it easier to run the code elsewhere.


## Multiple modules at the same time

You can of course have multiple modules loaded at the same time, e.g.
```sh
$ module load samtools/1.2
$ module load tophat/2.0.9
$ module load bowtie2/2.1.0
```
or short
```sh
$ module load samtools/1.2 tophat/2.0.9 bowtie2/2.1.0
```

## Currently used modules
To see which modules you have currently loaded, do:
```sh
$ module list
Currently Loaded Modules:
  1) samtools/1.2   2) tophat/2.0.9   3) bowtie2/2.1.0
```

To start over from scratch, just call
```sh
$ module purge
```
and all loaded modules will be unloaded;
```sh
$ module list
No modules loaded
```

## Modules available on the cluster

Page [Software Available Modules](https://github.com/UCSF-TI/TIPCC/wiki/Software-Available-Modules) gives detailed information (name, versions, and description) on the software modules available on the cluster.

To see currently available modules from the command line, do:
```sh
$ module avail

-------------------------- /home/shared/cbc/apps/modulefiles/Linux ---------------------------
   anaconda-python/2.7.13        igv/2.3.68               r/3.2.3
   anaconda/default              igv/2.3.92        (D)    r/3.2.4
   bamutil/1.0.14                igvtools/2.3.68          r/3.2.5
   bcftools/1.2                  igvtools/2.3.91   (D)    r/3.3.0
   bcftools/1.3.1                jdk/1.6.0                r/3.3.1
   bcftools/1.4           (D)    jdk/1.7.0                r/3.3.2
   bedops/1.2.2c                 jdk/1.8.0         (D)    r/3.3.3patched
   bedtools2/2.13.4              lua/5.1.4                r/3.3.3
   bedtools2/2.15.0              lua/5.3.3         (D)    r/3.4.0devel
   bedtools2/2.16.2              luarocks/2.4.2           r/3.4.0patched
   bedtools2/2.26.0       (D)    matlab/7.11.0.584        r/3.4.0
   blast/2.2.26                  matlab/7.14.0.739 (D)    r/3.5.0devel
   bowtie2/2.0.0-beta6           pandoc/1.19.2-0          s3cmd/1.5.0-alpha3
   bowtie2/2.1.0                 pip/9.0.1                samtools/0.1.12a
   bowtie2/2.2.6                 python/2.7.3             samtools/0.1.17
   bowtie2/2.2.9          (D)    python/2.7.4             samtools/0.1.18
   bwa/0.5.10                    python/2.7.9             samtools/0.1.19-patched
   bwa/0.6.1                     r-extras/0.1.0           samtools/0.1.19
   bwa/0.7.5a                    r/devel                  samtools/1.2
   bwa/0.7.12             (D)    r/oldrel                 samtools/1.3.1          (D)
   cbc-bin/0.1.0                 r/patched                snpeff/2.0.2
   cbc-tools/0.1.0               r/release         (D)    snvmix2/0.11.8-r3
   cbc-tools/0.1.1        (D)    r/2.11.0                 sratoolkit/2.3.4-2
   control-freec/2.5             r/2.11.1                 sratoolkit/2.4.1
   control-freec/7.2-3    (D)    r/2.12.2                 sratoolkit/2.5.7
   cufflinks/1.0.3               r/2.13.1                 sratoolkit/2.8.2-1      (D)
   cufflinks/1.3.0        (D)    r/2.13.2                 tophat/1.3.0
   example/0.1                   r/2.14.0                 tophat/1.3.1
   fastqc/0.10.1                 r/2.15.0                 tophat/1.4.0
   fastqc/0.11.2          (D)    r/2.15.1                 tophat/2.0.3
   fiji/2.0.0                    r/2.15.2                 tophat/2.0.9
   gdc-client/1.0.1              r/2.15.3                 tophat/2.0.10
   genetorrent/3.0.2             r/3.0.0                  tophat/2.1.0
   genetorrent/3.8.5a-94  (D)    r/3.0.1                  tophat/2.1.1            (D)
   git/2.1.1                     r/3.0.2                  udocker/1.0.0
   git/2.1.3              (D)    r/3.0.3                  valgrind/3.8.1          (D)
   gitflow/0.4.2                 r/3.1.0                  valgrind/3.10.0
   htop/1.0.3                    r/3.1.1                  varscan/2.2.3
   htseq/0.5.4p3                 r/3.1.2                  varscan/2.3.9           (D)
   htseq/0.6.1            (D)    r/3.1.3                  vcftools/0.1.13
   htslib/1.3.2                  r/3.2.0                  wordspy/1.5
   igv/2.1.2                     r/3.2.1
   igv/2.3.31                    r/3.2.2

--------------------------- /home/shared/cbc/apps/modulefiles/Core ---------------------------
   StdEnv          gcc/4.8.1    gcc/4.9.2        spack-gcc-4.9.2    spack/0.10.0
   StdEnv-spack    gcc/4.8.4    gcc/5.1.0 (D)    spack-gcc-5.4.0

---------------------- /home/shared/cbc/apps/lmod/lmod/modulefiles/Core ----------------------
   lmod/7.1    settarg/7.1

-------------------------------------- /etc/modulefiles --------------------------------------
   compat-openmpi-psm-x86_64

----------------------------------- /opt/scyld/modulefiles -----------------------------------
   acml-5.1.0/open64_64_fma4         open64-4.5.1.1
   acml-5.1.0/open64_64       (D)    python/2.6.5
   gcc/5.1.0                         python/2.7.10              (D)
   maui                              samtools/0.1.18
   misopy/0.5.3/python.2.7.10        scipy/0.16.1/python.2.7.10
   net-snmp-scyld                    telseq/102115
   numpy/1.10.1/python.2.7.10        vcftools/0.1.13/gcc.4.4.7

  Where:
   D:  Default Module

Use "module spider" to find all possible modules.
Use "module keyword key1 key2 ..." to search for all possible modules matching any of the
"keys".
```
(The above set is from 2017-06-13).


## Create your own modules

As a user you can also add your own modules.  Each module is simply a small [Lua](https://www.lua.org) script.  You can look at one of the existing ones by using `module show samtools/1.2` (or see `module avail` for its location).  Our setup is such that any module files added under `$HOME/modulefiles` will be automatically available.  Say you have your own installation of FunnyR 3.1.2 and wish to add that to the list of modules that you see by creating an empty file `$HOME/modulefiles/funnyr/3.1.2.lua` - we recommend to use all lowercase module names.  You can then look at the content of one of the existing Lua module files and use that as your template, e.g.
```sh
$ module show r
--------------------------------------------------------------------
   /home/shared/cbc/apps/modulefiles/Linux/r/release.lua:
--------------------------------------------------------------------
help([[The R Programming Language
]])
whatis("Version: 3.4.0")
whatis("Keywords: Programming, Statistics")
whatis("URL: https://www.r-project.org/")
whatis("Description: The R programming language")
prepend_path("PATH", "/home/shared/cbc/software/R-3.4.0/bin")
```
That shows a cleaned up version of the Lua code in `/home/shared/cbc/apps/modulefiles/Linux/r/release.lua`.  As you see, it is pretty straightforward.

If your module depend on other modules, you can specify that too, e.g.
```sh
load("r")
load("python")
load("samtools/1.2")
-- additional specific settings below
prepend_path("PATH", ...)
```
You can use this approach to create "super" modules that loads a set of common modules that you always use.  That is what the `cbc-shared` module does.


## Enable Lmod modules (BETA)
The Lmod environment module is currently in beta on our cluster and each user needs to enable them manually by adding
```sh
MODULE_FRAMEWORK=lmod
```
to the top of the `~/.bashrc` startup script _before_ the if-then statement calling `/etc/bashrc`.  That's it!  

_NOTE: This change alone should *not* affect any of your existing scripts or experience at the command line._


## Technical details
This new module framework is using the [Lmod Module Framework](http://lmod.readthedocs.io/en/latest/), which is a framework that supports both the classical modules written in the Tcl language as well as modules written in the Lua language.

