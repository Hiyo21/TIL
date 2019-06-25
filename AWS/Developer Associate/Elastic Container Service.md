# ECS (Elastic Container Service)

### ECS

- docker-compatible container service provided by AWS. Allows for easy and fast container deployment!
- Container Orchestration. Sorta like Kubernetes?

### ECS Usages

- Frequently used in distributed Applications. Microservices!
- Batch and ETL jobs
  - Run different versions of the same job or multiple jobs on the same cluster
  - Share cluster capacities
- CI/CD
  - using Docker's image versioning, can use containers
  
### AWS Fargate

- a way to use containers as the fundamental application building blocks while AWS manages EC2 for me.

### Components

#### Dockerfile

- definition for what goes inside a given Docker container

#### Docker Image

- using Dockerfile, a container includes all the software, code, libraries defined in Dockerfile

#### Container registry

- repo where container / docker images are stored and accessed
- can be accessed via ECR (Elastic Container Registry) service
- DockerHub and the like
- Self-hosted registry

#### ECS Task Definition

- JSON string that contains the "blueprint" for the application
  - Which container / docker image to use
  - The repository image is in
  - Which ports should be open
  - Which data volumes should be used

#### Docker

- Container service
- Highly portable, customizable, reliable (when made properly)
- Quickly deploy and scale your application
- Save money by improving resource utilization
- Docker supports multiple containers per EC2 instance
- IMPORTANT : Each container should have one concern only!! Decoupled, horizontally scalable, reusuable
- You want your docker container to be as simple as possible

### IAM Roles for ECS Tasks
