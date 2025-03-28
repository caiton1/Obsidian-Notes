## Enhanced networking
- EC2 enhanced networking (SR-IOV)
	- higher bandwidth, higher PPS, lower latency
	- ENA: elastic network adapter, up to 100 GBbs
	- Intel 82599 VF up to 10 Gbps - Legacy
	- Works for newer EC2 instances
- Elastic Fabric Adapter (EFA)
	- Improved ENA for HPC, only works for linux
	- great for internode communication in tightly coupled workloads
	- 