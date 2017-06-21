# HOW TO: Compress files (as a job)
Instead of running `gzip` in an interactive session, you can submit a job for doing it using `qgzip`.  For example, to submit a job that compresses all FASTQ files in a certain directory, do:
```sh
qgzip /path/to/*.fastq
```
or
```sh
cd /path/to/
qgzip *.fastq
```
This "queued" version of `gzip` takes the same options as `gzip`, so you can also do things such as:
```sh
## Recursively find all files and compress them with maximum efficiency
qgzip -r -9 /path/to/
```

Analogue to `qgzip` there is a queued version of `bzip2`, i.e. `qbzip2`.  

These commands are available in `/home/shared/cbc/bin/`.

## Benchmarking
Compression a 10 GiB FASTQ file on `/scratch/` using `gzip` took approximately 25 minutes and resulted in a 2.2 GiB FASTQ.gz file. 