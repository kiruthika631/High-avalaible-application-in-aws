# High-avalaible-application-in-aws
ELB &amp; ASG
Ensuring high availability for applications is a critical requirement in today's business environment. AWS provides a robust set of tools and services to achieve high availability, specifically through the use of Elastic Load Balancing (ELB) and Auto Scaling Groups (ASG). These services work in tandem to distribute traffic evenly across multiple instances and automatically adjust the number of instances based on demand, ensuring your application remains responsive and available.
Key Components
Elastic Load Balancing (ELB)

Purpose: ELB automatically distributes incoming application traffic across multiple targets, such as Amazon EC2 instances, containers, and IP addresses, in one or more Availability Zones.
Types of ELB:
Application Load Balancer (ALB): Best suited for HTTP and HTTPS traffic, provides advanced routing and load balancing.
Network Load Balancer (NLB): Best suited for TCP, UDP, and TLS traffic where extreme performance is required.
Classic Load Balancer (CLB): Provides basic load balancing across multiple Amazon EC2 instances and operates at both the request and connection levels.
Features:
Health Checks: Monitors the health of registered targets and ensures traffic is only sent to healthy instances.
SSL Termination: Offloads SSL decryption/encryption, reducing the burden on application instances.
Sticky Sessions: Ensures that user sessions are consistently routed to the same instance.
Auto Scaling Groups (ASG)

Purpose: ASG automatically adjusts the number of Amazon EC2 instances in response to demand, scaling out during high demand to maintain performance and scaling in during low demand to reduce costs.
Components:
Launch Configuration/Template: Defines the EC2 instance type, Amazon Machine Image (AMI), key pairs, security groups, and other configurations.
Scaling Policies: Determine when and how the ASG should scale in or out based on specified conditions or metrics (e.g., CPU utilization, network traffic).
Health Checks: Ensures that only healthy instances are retained in the group by terminating and replacing unhealthy ones.
Benefits:
Cost Efficiency: Automatically scales the number of instances to match the demand, optimizing resource usage.
Fault Tolerance: Distributes instances across multiple Availability Zones to protect against failure in a single zone.
Implementation Steps
Design the Architecture

Define the target application requirements and choose the appropriate type of load balancer (ALB, NLB, or CLB).
Identify the critical metrics that will trigger scaling events (e.g., CPU utilization, memory usage, request count).
Set Up ELB

Create Load Balancer: Choose the load balancer type based on the application’s needs.
Configure Listeners: Define how incoming traffic should be routed (e.g., HTTP, HTTPS).
Register Targets: Add the Amazon EC2 instances, IP addresses, or Lambda functions that will receive traffic.
Set Up Health Checks: Configure health checks to monitor the health and performance of the targets.
Set Up ASG

Create Launch Configuration/Template: Define the settings for the instances that will be launched.
Define Auto Scaling Policies: Set up scaling policies based on key performance metrics.
Distribute Across Availability Zones: Ensure the ASG is configured to launch instances across multiple Availability Zones for fault tolerance.
Monitor and Adjust: Continuously monitor the performance and adjust policies as needed to optimize performance and cost.
Benefits and Use Cases
Increased Uptime: Ensures continuous availability by distributing traffic and automatically scaling instances.
Scalability: Handles varying traffic loads efficiently by scaling resources up or down.
Cost Optimization: Matches resource allocation to demand, avoiding over-provisioning.
Enhanced Performance: Routes traffic to the most responsive and healthy instances, improving application performance.
Disaster Recovery: Distributes instances across multiple Availability Zones, providing redundancy and fault tolerance.
