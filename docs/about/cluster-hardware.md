# Cluster Hardware

Node      | Nbr of cores | CPU (GHz) | RAM (GiB) | Local disk (TiB) | Notes                        | Priority
----------|-------------:|----------:|----------:|-----------------:|------------------------------|-----------
n0        |           64 |      2.6  |       512 |              5.2 | InfiniBand (IB), FMA4        | CBC, Taylor Lab
n1        |           48 |      2.6  |       512 |              2.5 | InfiniBand (IB), FMA4        | (communal)
n2        |           48 |      2.6  |       512 |              2.5 | InfiniBand (IB), FMA4        | (communal)
n3        |           48 |      2.4  |       384 |              5.2 | InfiniBand (IB), FMA4        | Krummel Lab
n4        |           12 |      2.4  |        32 |              1.8 |                              | (communal)
n5        |           12 |      2.4  |        32 |              1.8 |                              | (communal)
n6        |           12 |      2.4  |        32 |              1.8 | Allowed for interactive use  | (communal)
n7        |           12 |      2.3  |        64 |              1.8 |                              | (communal)
n8        |           12 |      2.3  |        64 |              1.7 |                              | (communal)
n9        |           12 |      2.3  |        64 |              1.8 |                              | (communal)
n10       |           12 |      2.3  |        64 |              1.7 |                              | (communal)
n11       |           12 |      2.3  |        64 |              1.8 |                              | (communal)
n12       |           48 |      2.3  |       384 |              1.7 | Tesla M2070 GPU w/ 448 cores | (communal)
n13       |           48 |      2.3  |       512 |              1.6 | Tesla M2070 GPU w/ 448 cores | (communal)
n14       |           12 |      3.47 |       128 |             0.84 | InfiniBand (IB), Intel       | Witte Lab
n15       |           64 |      2.6  |       128 |              1.7 | InfiniBand (IB), FMA4        | Witte Lab
n16       |           64 |      2.6  |       128 |             10.7 | InfiniBand (IB), FMA4        | Witte Lab
n17       |           64 |      2.6  |       512 |              5.2 | InfiniBand (IB), FMA4        | CBC, Taylor Lab
n18       |           64 |      2.6  |       512 |              5.2 | InfiniBand (IB), FMA4        | Diaz Lab, Costello Lab, Fung Lab, Song Lab
n19       |           64 |      2.6  |       512 |              5.2 | InfiniBand (IB), FMA4        | Diaz Lab, Costello Lab, Fung Lab, Song Lab
n20       |           64 |      2.6  |       512 |              5.2 | InfiniBand (IB), FMA4        | Diaz Lab, Costello Lab, Fung Lab, Song Lab
n21       |           48 |      2.8  |       256 |              5.2 | InfiniBand (IB), FMA4        | Bandyopadhyay Lab
n22       |           48 |      2.8  |       384 |              5.2 | InfiniBand (IB), FMA4        | Molinaro Lab
n23       |           48 |      2.8  |       384 |              5.2 | InfiniBand (IB), FMA4        | Molinaro Lab
n26       |           12 |      2.4  |        32 |              1.7 |                              | (communal)
n27       |           48 |      1.4  |       384 |              5.2 | InfiniBand (IB), FMA4        | Costello Lab
n28       |           64 |      2.3  |       512 |              2.6 | InfiniBand (IB), FMA4        | Shannon Lab
n29       |           28 |      2.4  |       512 |              7.2 | InfiniBand (IB), Intel       | Sweet-Cordero Lab
n30       |           28 |      2.4  |       512 |              7.2 | InfiniBand (IB), Intel       | Sweet-Cordero Lab
**Total** |     **1072** |           |           |                  |                              |

The head node specs: 12 cores, 2.4 GHz CPU, 128 GiB RAM.
The local disk space is unique to each node and mounted as `/scratch/`.
All nodes have AMD processors, except n14, n29, and n30 which have Intel processors.
Nodes n24 and n25 are being migrated to become "login" nodes. /February 2016  
Source: `pbsnodes`, `cat /proc/cpuinfo` and `grep -F SRCFG /opt/moab/etc/moab.cfg`.

_Notes_:
1. The "communal" nodes has a [maximum walltime of 168 hours](https://github.com/UCSF-TI/TIPCC/issues/52#issuecomment-221402795) and will not take a job requesting more.
2. Nodes n4-n11, which are all communal, need to be rebooted on-site if they go down.  The others can be rebooted remotely.
2. Occasionally there are (planned or non-planned) power outages in the building.  Our compute cluster is typically _not_ affected by these, because the cluster operators on a separate power grid from the house.

<style>
table {
  margin-top: 2ex;
  margin-bottom: 2ex;
}
tr:last-child { border-top: 2px solid #000; }
</style>
