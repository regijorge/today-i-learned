# EC2 - Elastic Compute Cloud

* EC2 Service is a hosting service for virtual machines
* A EC2 instance is a virtual machine


## Categories

### General Purpose
* T2, M5, M4 and M3
* Provides a balance between memory and network resources
* T2 provides burst performance
  * Credits accrue during idle times
  * Credits used to burst performance
* M5, M4, M3 have no burst option (nice for development and staging)

### Compute optimized
* C5, C4 and C3
* Useful for CPU intensive applications
  * Media coding
  * Intense batch jobs
  * Many concurrent users accessing
  * Gaming servers
  * Anything compute intensive

### Memory optimized
* X1e, X4, R4 and R3
* Useful for hight memory requirements
  * Processing large datasets
  * In memory databases
  * Big Data processing

### Storage optimized
* H1, I3, D2
* Useful for high sequential read/writes to local storage
  * Relational databases
  * Data warehousing
  * Image storage and processing

### Advanced computing
* P3, P2, G3 and F1
* Useful for specialty hardware compute requirements
  * Graphic Processing Unit (GPU)
  * Field-Programmable Gateway Array (FPGA)


## Pricing Categories

### On-demand
* Charged for used time at a flat rate
* Billed in 60 second increments rounded up

### Reserved
* Hours
* Reserve used miminum 1 year
* Can be less expenssive than On-demand

### Spot
* Bid on unused compute time
* Up to 90% discount over On-demand

## Security groups
* Limited to 5 per instance
* Can layer security groups
*