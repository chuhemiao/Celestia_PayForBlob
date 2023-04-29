# Performance Analysis of Celestia Light Nodes in High Configuration

## VPS Env

Memory: 8 GB RAM

NVM.e: 50 GB NVMe or 200 GB SSD

CPU: 4 vCPU Cores

Bandwidth: up 100M

Run the following commands to get an overview of the node service usage and running processes. This is to analyze the problems encountered by the light node in operation and how to improve its speed and online rate.

### 1. uptime

![alt uptime](https://github.com/chuhemiao/Celestia_PayForBlob/blob/main/imgs/uptime.png?raw=true)

From the results the server has been running for almost a month and its average load is: 0.58 0.43 0.33.

It is the only quick way to see the system load, the load average is the 3 values that count the changes in system load over the last 1, 5 and 15 minutes in a decreasing manner.

### 2. sysstat

To view network throughput, first we install the sysstat service `apt install sysstat`

Then execute `sar -n DEV 1`

![alt sar-n](https://github.com/chuhemiao/Celestia_PayForBlob/blob/main/imgs/sar-n.jpeg?raw=true)

The throughput of the network interface is checked to see if it has reached its sending and receiving limits. From the results, it looks like the throughput is at a very low value, because my server has a high configuration, so there is basically no throughput shortage.

### 3. Disk IO and CPU

Run `iostat -xz 1` and `mpstat -P ALL 1`.

![alt iost-z](https://github.com/chuhemiao/Celestia_PayForBlob/blob/main/imgs/iost-z.jpeg?raw=true)

![alt mpstat-p](https://github.com/chuhemiao/Celestia_PayForBlob/blob/main/imgs/mpstat-p.jpeg?raw=true)

Since the server has only 4 processor cores, there is some fluctuation in the early runs, but after the blocks are synchronized it works easily with lighter nodes. The load is constantly changing, but the average is about 1%.

The disk IO is also changing, but the system wait time is very low, probably due to the SSD.

### 4. Check the memory free -m

![alt free-m](https://github.com/chuhemiao/Celestia_PayForBlob/blob/main/imgs/free-m.jpeg?raw=true)

From the result, there is no swap usage, and there is 5.6G free, so there is no load on the server.

### 5. top to check the overall situation

![alt top](https://github.com/chuhemiao/Celestia_PayForBlob/blob/main/imgs/top.jpeg?raw=true)

From the overall situation, only one service, celestia light node, is running, so the average use of memory is 60% and CPU load is about 40%, but this is only in case of fluctuations.

### Analysis of node running state

From the results of the above parameters, we can see that the CPU, memory and bandwidth are running very well, only in the case of the first synchronized node and the installation of the whole Celestia service and dapp, the load is at the peak of the whole service, so we can see that the official request for memory and bandwidth when installing the node is also due to the fact that at some point the synchronized nodes and blocks need more at some point when synchronizing nodes and blocks. That's why I deployed the whole service with a very high configuration, because I was worried about the quality of service and data availability of the service would be under pressure.
