# Using local /scratch/ space

All nodes have their own locally storage mounted as `/scratch/`.  The `/scratch/` storage is fast - faster than system-wide storage such as `/home/` and `/work/` - which make it ideal for holding intermediate data files.  This will also lower the load on the system-wide storage and the local network.


Here is how you should use `/scratch/`:

* **Write to `/scratch/$USER/`**.  This will minimize the risk for clashing with other users, which may happen if you use the same filename and write to `/scratch/`.

* **Write _intermediate_ data files to `/scratch/$USER/` whenever possible**.  Any job that writes _intermediate_ data to file and later read then back will run faster if using the local scratch storage on the node.

* **Don't leave files on `/scratch/` longer than necessary**.  For instance, have your jobs cleanup after themselves.

* **Specify how much local storage your job will need**.  Local storage is limited to [0.84 - 10.7 TiB depending on node]({{ '/about/cluster-hardware.html' | relative_url }}).  If your job will use up to 400 GiB of disk space, you can specify this resource as `-l gres:scratch=400` (units is in GiB) when submitting the job.  A node with 2,000 GiB of scratch space will at most have five `-l gres:scratch=400` jobs running at the same time.

* **All files on `/scratch/` is local to that node**.  Any files copies / written to a node's `/scratch/` space will only be accessible from that node and not from anywhere else.


To clarify, the `scratch` resource is just a bunch of tokens available per node that are handed out to jobs and recollected when those jobs are done.  The number of tokens available for a given node depends on how big it's `/scratch/` drive is.  What is not automatically accounted for is the actual _free_ disk space available on `/scratch/`.  Because of this, it is important that we all have our jobs clean up `/scratch/` usage after themselves so the next user / job can safely run.
