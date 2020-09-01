# ELB - Elastic Load Balancer

* Supported services
  * EC2
  * ECS
  * Auto Scaling
  * CloudWatch
  * Rout 53

## Categories
* Sender initiated
  * Sender locates best target
* Receiver initiated
  * Receiver selects best target

## Load balancer concepts
### Static load balancing
* Multi-tier application
  * Specific actions are assigned to specific servers/resources
  * Actions always processed on assigned target
  * No scalability

### Dynamic load balancing
* True load balancing
  * Actions dynamically assigned
  * Scalability is provided
* This is used by AWS ELB
