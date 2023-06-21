## Ontology Modeller
This project aims to model an ontology for HPC computing environment based on some of the sample datasets produced by real-world HPC cluster tools.
- In this project, we'll focus on the datasets collected from SURF's LISA HPC cluster and CINECA's Marconi100 HPC cluster (consisting of metrics clooected at various levels from the HPC environment).
- The ontology modelling aims to extend or improve upon an HPC ontology already derived by the HPC-FAIR research team at https://hpc-fair.github.io/ontology/ [[1]](#1).
- The aim of this project is to reuse the HPC-FAIR ontology while mapping metrics from these datasets (which have been made available for research) as much as possible and adding the missing ones.

## Metrics mapping
1.CINECA's Marconi100 cluster dataset consists of metrics associated with different plugins as described below:
* IPMI plugin (https://gitlab.com/ecs-lab/exadata/-/blob/main/documentation/plugins/ipmi.md)
    * metric (description; unit; value type; sampling period)
    * ambient (Temperature at the node inlet; measured in °C; values are of type float; sampled at 20s from each node)
    * dimmX_temp (Temperature of DIMM module X. X=0..15; measured in °C; values are of type int; sampled at 20s from each node)
    * fanX_Y (Speed of the Fan Y in module X. X=0..3, Y=0,1; measured in revolutions (RPM); values are of type int; sampled at 20s from each node)
    * fan_disk_power (Temperature at the node inlet; measured in Watts; values are of type int; sampled at 20s from each node)
    * gpuX_core_temp (Temperature of the core for the GPU id X. X=0,1,3,4; measured in °C; values are of type int; sampled at 20s from each node)
    * gpuX_mem_temp (Temperature of the memory for the GPU id X. X=0,1,3,4; measured in °C; values are of type int; sampled at 20s from each node)
    * gv100cardX (Nvidia Quadro GV100 Card for the GPU id X. X=0,1,3,4; measurement is unspecified; values are of type int; sampled at 20s from each node)
    * pX_coreY_temp (Temperature of core Y in the CPU socket X. X=0..1, Y=0..23; measured in °C; values are of type int; sampled at 20s from each node)
    * pX_io_power (Power consumption for the I/O subsystem for the CPU socket X. X=0..1; measured in Watts; values are of type int; sampled at 20s from each node)
    * pX_mem_power (Power consumption for the memory subsystem for the CPU socket X. X=0..1; measured in Watts; values are of type int; sampled at 20s from each node)
    * pX_power (Power consumption for the CPU socket X. X=0..1; measured in Watts; values are of type int; sampled at 20s from each node)
    * pX_vdd_temp (Temperature of the voltage regulator for the CPU socket X. X=0..1; measured in °C; values are of type int; sampled at 20s from each node)
    * pcie (Temperature at the PCIExpress slots; measured in °C; values are of type float; sampled at 20s from each node)
    * psX_input_power (Power consumption at the input of power supply X. X=0..1; measured in Watts; values are of type int; sampled at 20s from each node)
    * psX_input_voltag (Voltage at the input of power supply X. X=0..1; measured in Volts; values are of type int; sampled at 20s from each node)
    * psX_output_curre (Current at the output of power supply X. X=0..1; measured in Amps; values are of type int; sampled at 20s from each node)
    * psX_output_volta (Voltage at the output of power supply X. X=0..1; measured in Volts; values are of type float; sampled at 20s from each node)
    * total_power (Total node power consumption; measured in Watts; values are of type int; sampled at 20s from each node)

| metric (description)                                                                  	  | unit                          	| value type               	| sampling period              	|
|------------------------------------------------------------------------------------------|-------------------------------	|--------------------------	|------------------------------	|
| ambient (Temperature at the node inlet)                                                	 | measured in °C                	| values are of type float 	| sampled at 20s from each node 	|
| dimmX_temp (Temperature of DIMM module X. X=0..15)                                     	 | measured in °C                	| values are of type int   	| sampled at 20s from each node 	|
| fanX_Y (Speed of the Fan Y in module X. X=0..3, Y=0,1)                                 	 | measured in revolutions (RPM) 	| values are of type int   	| sampled at 20s from each node 	|
| fan_disk_power (Temperature at the node inlet)                                         	 | measured in Watts             	| values are of type int   	| sampled at 20s from each node 	|
| gpuX_core_temp (Temperature of the core for the GPU id X. X=0,1,3,4)                   	 | measured in °C                	| values are of type int   	| sampled at 20s from each node 	|
| gpuX_mem_temp (Temperature of the memory for the GPU id X. X=0,1,3,4)                  	 | measured in °C                	| values are of type int   	| sampled at 20s from each node 	|
| gv100cardX (Nvidia Quadro GV100 Card for the GPU id X. X=0,1,3,4)                      	 | measurement is unspecified    	| values are of type int   	| sampled at 20s from each node 	|
| pX_coreY_temp (Temperature of core Y in the CPU socket X. X=0..1, Y=0..23)             	 | measured in °C                	| values are of type int   	| sampled at 20s from each node 	|
| pX_io_power (Power consumption for the I/O subsystem for the CPU socket X. X=0..1)     	  | measured in Watts             	| values are of type int   	| sampled at 20s from each node 	|
| pX_mem_power (Power consumption for the memory subsystem for the CPU socket X. X=0..1) 	  | measured in Watts             	| values are of type int   	| sampled at 20s from each node 	|
| pX_power (Power consumption for the CPU socket X. X=0..1)                              	  | measured in Watts             	| values are of type int   	| sampled at 20s from each node 	|
| pX_vdd_temp (Temperature of the voltage regulator for the CPU socket X. X=0..1)        	  | measured in °C                	| values are of type int   	| sampled at 20s from each node 	|
| pcie (Temperature at the PCIExpress slots)                                             	  | measured in °C                	| values are of type float 	| sampled at 20s from each node 	|
| psX_input_power (Power consumption at the input of power supply X. X=0..1)             	  | measured in Watts             	| values are of type int   	| sampled at 20s from each node 	|
| psX_input_voltag (Voltage at the input of power supply X. X=0..1)                      	  | measured in Volts             	| values are of type int   	| sampled at 20s from each node 	|
| psX_output_curre (Current at the output of power supply X. X=0..1)                     	  | measured in Amps              	| values are of type int   	| sampled at 20s from each node 	|
| psX_output_volta (Voltage at the output of power supply X. X=0..1)                     	  | measured in Volts             	| values are of type float 	| sampled at 20s from each node 	|
| total_power (Total node power consumption)                                             	 | measured in Watts             	| values are of type int   	| sampled at 20s from each node 	|

2. SURF's LISA Cluster dataset consists of various metrics from both Prometheus and SLURM as described below:

| ID 	| Prometheus Metrics                              	 | Description                                                                                                       	| Unit        	| Datatype  	|
|----	|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------	|-------------	|-----------	|
| 1  	| id                                   	            | Measurement ID                                                                                                    	| -           	| int       	|
| 2  	| timestamp                            	            | Time of the measurment, every 30 seconds                                                                          	| -           	| datetime  	|
| 3  	| up                                   	            | the node is up or not                                                                                             	| -           	| int       	|
| 4  	| node                                 	            | The number of rack and node                                                                                       	| -           	| string    	|
| 5  	| node_arp_entries                     	            | ARP entries by device                                                                                             	| Aggregates  	|           	|
| 6  	| node_boot_time_seconds               	            | Node boot time, in unixtime                                                                                       	| Aggregates  	| timestamp 	|
| 7  	| node_context_switches_total          	            | Total number of context switches                                                                                  	| Aggregates  	| int       	|
| 8  	| node_disk_io_now                     	            | The number of I/Os currently in progress                                                                          	|             	|           	|
| 9  	| node_disk_read_bytes_total           	            | The total number of bytes read successfully                                                                       	|             	|           	|
| 10 	| node_disk_writes_completed_total     	            | The total number of writes completed successfully                                                                 	|             	|           	|
| 11 	| node_disk_written_bytes_total        	            | The total number of bytes written successfully                                                                    	|             	|           	|
| 12 	| node_filesystem_avail_bytes          	            | Filesystem space available to non-root users in bytes                                                             	|             	| json      	|
| 13 	| node_filesystem_device_error         	            | Whether an error occurred while getting statistics for the   given device                                         	|             	|           	|
| 14 	| node_filesystem_files                	            | Filesystem total file nodes                                                                                       	|             	| json      	|
| 15 	| node_filesystem_files_free           	            | Filesystem total free file nodes                                                                                  	|             	|           	|
| 16 	| node_filesystem_free_bytes           	            | Filesystem free space in bytes                                                                                    	|             	|           	|
| 17 	| node_filesystem_size_bytes           	            | Filesystem size in bytes                                                                                          	|             	|           	|
| 18 	| node_forks_total                     	            | Total number of forks                                                                                             	|             	| json      	|
| 19 	| node_hwmon_temp_celsius              	            | Temperature of the node                                                                                           	| Celsius     	| json      	|
| 20 	| node_intr_total                      	            | Total number of interrupts serviced                                                                               	|             	|           	|
| 21 	| node_load1                           	            | 1m CPU utilization load average                                                                                   	|             	|           	|
| 22 	| node_load15                          	            | 15m CPU utilization load average                                                                                  	|             	|           	|
| 23 	| node_load5                           	            | 5m CPU utilization load average                                                                                   	|             	|           	|
| 24 	| node_memory_Active_bytes             	            | Memory                                                                                                           	|             	|           	|
| 25 	| node_memory_Dirty_bytes              	            | Memory                                                                                                           	|             	|           	|
| 26 	| node_memory_MemFree_bytes            	            | Memory                                                                                                           	|             	|           	|
| 27 	| node_memory_Percpu_bytes             	            | Memory                                                                                                           	|             	|           	|
| 28 	| node_netstat_Icmp_InErrors           	            | Statistic                                                                                                         	|             	|           	|
| 29 	| node_netstat_Icmp_InMsgs             	            | Statistic                                                                                                         	|             	|           	|
| 30 	| node_netstat_Icmp_OutMsgs            	            | Statistic                                                                                                         	|             	|           	|
| 31 	| node_netstat_Tcp_InErrs              	            | Statistic                                                                                                         	|             	|           	|
| 32 	| node_netstat_Tcp_InSegs              	            | Statistic                                                                                                         	|             	|           	|
| 33 	| node_netstat_Tcp_OutSegs             	            | Statistic                                                                                                         	|             	|           	|
| 34 	| node_netstat_Tcp_RetransSegs         	            | Statistic                                                                                                         	|             	|           	|
| 35 	| node_netstat_Udp_InDatagrams         	            | Statistic                                                                                                         	|             	|           	|
| 36 	| node_netstat_Udp_InErrors            	            | Statistic                                                                                                         	|             	|           	|
| 37 	| node_netstat_Udp_OutDatagrams        	            | Statistic                                                                                                         	|             	|           	|
| 38 	| node_network_receive_bytes_total     	            | Network                                                                                                           	|             	|           	|
| 39 	| node_network_receive_drop_total      	            | Network                                                                                                           	|             	|           	|
| 40 	| node_network_receive_multicast_total 	            | Network                                                                                                           	|             	|           	|
| 41 	| node_network_receive_packets_total   	            | Network                                                                                                           	|             	|           	|
| 42 	| node_network_transmit_bytes_total    	            | Network                                                                                                           	|             	|           	|
| 43 	| node_network_transmit_packets_total  	            | Network                                                                                                           	|             	|           	|
| 44 	| node_procs_blocked                   	            | Number of processes blocked waiting for I/O to complete                                                           	|             	|           	|
| 45 	| node_procs_running                   	            | Number of processes in runnable state                                                                             	|             	|           	|
| 46 	| node_rapl_package_joules_total       	            |                                                                                                                   	|             	|           	|
| 47 	| node_thermal_zone_temp               	            | The thermal zone temperature of the node                                                                          	| Celsius     	|           	|
| 48 	| node_time_seconds                    	            | System time in seconds since epoch (1970)                                                                         	|             	|           	|
| 49 	| node_udp_queues                      	            | Number of allocated memory in the kernel for UDP datagrams in   bytes.                                            	| Aggregates  	|           	|
| 50 	| nvidia_gpu_duty_cycle                	            | Percent of time over the past   sample period during which one or more kernels were executing on the GPU   device 	|             	|           	|
| 51 	| nvidia_gpu_fanspeed_percent          	            | Fanspeed of the GPU device as a percent of its maximum                                                            	|             	|           	|
| 52 	| nvidia_gpu_memory_used_bytes         	            | Memory used by the GPU device in bytes                                                                            	| Bytes       	|           	|
| 53 	| nvidia_gpu_power_usage_milliwatts    	            | Power usage of the GPU device in milliwatts                                                                       	| Milliwattes 	|           	|
| 54 	| nvidia_gpu_temperature_celsius       	            | Temperature of the GPU device in celsius                                                                          	| Celsius     	|           	|
| 55 	| surfsara_ambient_temp                	            | Temprature of the datacenter                                                                                      	|             	|           	|
| 56 	| surfsara_power_usage                 	            | Power usage for the node                                                                                          	|             	|           	|

| ID 	| SLURM Metrics      	 | Description                              	| Datatype  	|
|----	|----------------------|------------------------------------------	|-----------	|
| 1  	| id           	       | Job ID                                   	| int       	|
| 2  	| start_date   	       | Start date of job                        	| datetime  	|
| 3  	| end_date     	       | End date of job                          	| datetime  	|
| 4  	| node         	       | Rack and node of the job, maybe multiple 	| string    	|
| 5  	| nodetypes    	       | Type of node                             	| string    	|
| 6  	| numnodes     	       | Number of nodes used for the job         	| int       	|
| 7  	| numcores     	       | Number of cores used for the job         	| int       	|
| 8  	| sharednode   	       |                                          	|           	|
| 9  	| submit       	       | Submit time of job                       	| timestamp 	|
| 10 	| start        	       | Start time of job                        	| timestamp 	|
| 11 	| end          	       | End time of job                          	| timestamp 	|
| 12 	| state        	       | End state of job                         	| string    	|
| 13 	| exitcode     	       | Exit code of job                         	|           	|
| 14 	| researvation 	       |                                          	|           	|
| 15 	| partprepaid  	       |                                          	|           	|

### References
<a id="1">[1]</a>
Chunhua Liao, Pei-Hung Lin, Gaurav Verma, Tristan Vanderbruggen, Murali Emani, Zifan Nan, Xipeng Shen, HPC Ontology: Towards a Unified Ontology for Managing Training Datasets and AI Models for High-Performance Computing, 2021 IEEE/ACM Workshop on Machine Learning in High Performance Computing Environments (MLHPC) (LLNL-CONF-826494)