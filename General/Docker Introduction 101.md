
**DOCKER OVERVIEW**

*"Docker containers wrap a piece of software in a complete filesystem that contains everything needed to run... This guarantees that the software will always run the same, regardless of its environment."*([docker.com/what-docker](https://www.docker.com/what-docker))

<ac:image><ri:attachment ri:filename="image2017-1-30 16:33:52.png"></ri:attachment></ac:image>

**Characteristics:**

1. Lightweight virtualization
2. Built on open standards (Portability!)
3. Resource isolation at the kernel
4. Thriving ecosystem - adoption and competition




@QL : <ac:link><ri:page ri:content-title="Docker Infrastructure Architecture" ri:space-key="Docker"></ri:page></ac:link>



**DOCKER REFERENCES**

- [The Docker Book (eBook)](http://www.dockerbook.com/), James Turnbull
- [Introduction to Docker (Video)](https://www.youtube.com/watch?v=Q5POuMHxW-0)[- Solomon Hykes](http://www.dockerbook.com/)
- [Docker User Guide](https://docs.docker.com/userguide/)[- Getting Started](http://www.dockerbook.com/)
- [Docker Command Line](http://docs.docker.com/reference/commandline/cli/) - Command-line reference
- [Dockerfile Reference](https://docs.docker.com/reference/builder/) - Building Docker images
- Kubernetes Getting Started: [https://blog.jetstack.io/blog/k8s-getting-started-part2/](https://blog.jetstack.io/blog/k8s-getting-started-part2/)
- Tutorial Kubernetes: [https://rominirani.com/tutorial-getting-started-with-kubernetes-on-your-windows-laptop-with-minikube-3269b54a226#.v9wqz27an](https://rominirani.com/tutorial-getting-started-with-kubernetes-on-your-windows-laptop-with-minikube-3269b54a226#.v9wqz27an)
- Kubernetes: [https://www.youtube.com/watch?v=\_vHTaIJm9uY](https://www.youtube.com/watch?v=_vHTaIJm9uY)
- Comparing Container Orchestration: [https://insights.hpe.com/articles/the-basics-explaining-kubernetes-mesosphere-and-docker-swarm-1702.html?jumpid=em\_dmqugav5kp\_aid-510204404](https://insights.hpe.com/articles/the-basics-explaining-kubernetes-mesosphere-and-docker-swarm-1702.html?jumpid=em_dmqugav5kp_aid-510204404)




**Tips:**

- It's ok to start with a monolith then extract services once you understand your business domain and bounded contexts
- Keep your Docker images small
- Don't use Docker containers like full blown VMs - Run only 1 process in each Docker container
- Use Docker Networking to communicate between containers (on the same host) (as an alternative to legacy links for communicating between containers)
- Bounded Context helps you define your microservices




## [Containers](https://en.wikipedia.org/wiki/Operating-system-level_virtualization):

General Info / Reading: [https://blog.risingstack.com/operating-system-containers-vs-application-containers/](https://blog.risingstack.com/operating-system-containers-vs-application-containers/)

1. Docker: [https://www.docker.com/](https://www.docker.com/)
2. Docker Getting Started (with a VM): [https://docs.docker.com/machine/get-started/](https://docs.docker.com/machine/get-started/)




[Container Orchestration](http://thenewstack.io/containers-container-orchestration/) (3 competing technologies):

1. Docker Swarm : [https://docs.docker.com/swarm/](https://docs.docker.com/swarm/)
2. Mesos [http://mesos.apache.org/](http://mesos.apache.org/)
3. Kubernetes : [http://kubernetes.io/](http://kubernetes.io/) (I LIKE THIS ONE, PERSONALLY)


\*\* Mesosphere : [https://mesosphere.com/](https://mesosphere.com/) (another thing to consider)







**Docker: Introduction 101**

[http://conferences.oreilly.com/software-architecture/engineering-business-ca/public/schedule/detail/53806](http://conferences.oreilly.com/software-architecture/engineering-business-ca/public/schedule/detail/53806)

[file:///Users/pvarga/Projects/DockerStuff/usb-stick/Tutorial.html](file:///Users/pvarga/Projects/DockerStuff/usb-stick/Tutorial.html)

[file:///Users/pvarga/Projects/DockerStuff/usb-stick/slides/index.html#/](file:///Users/pvarga/Projects/DockerStuff/usb-stick/slides/index.html#/)

[file:///Users/pvarga/Projects/DockerStuff/usb-stick/exercises/01-intro/README.html](file:///Users/pvarga/Projects/DockerStuff/usb-stick/exercises/01-intro/README.html)

[https://docs.docker.com/engine/reference/commandline/](https://docs.docker.com/engine/reference/commandline/)



**Workshop #1 References:**

- Original Instavote app: [https://github.com/docker/example-voting-app](https://github.com/docker/example-voting-app)
- Postgresl image: [https://hub.docker.com/\_/postgres/](https://hub.docker.com/_/postgres/)
- Redis image: [https://hub.docker.com/\_/redis/](https://hub.docker.com/_/redis/)
- Docker Compose: [https://docs.docker.com/compose/](https://docs.docker.com/compose/)
- Compose file reference: [https://docs.docker.com/compose/compose-file/](https://docs.docker.com/compose/compose-file/)






**CHALLENGES WITH MODERN ARCHITECTURES**

- Multiple tech stacks
- Lots of moving parts
- Complex infrastructure
- Phoenix deployment
- Increased release frequency
- Teams on-boarding




**Containers for shipping applications:**

- Encapsulated
- Portable
- Run on any hardware
- Run consistently






**WHAT IS A CONTAINER?**

Collection of normal processes

- Running in isolation (process and resource isolation)
- Running in a virtualized system
    - Shared parts of the operating system are read only
    - Shared OS kernel for all system calls


Each container’s processes are visible on the host





**HOW DO CONTAINERS RUN?**

Variety of container engines

- Low-level engine or full system engine
- Example container runtimes include: LXC, rkt, Docker, OpenVZ
- Standards around containers:
    - [Open Containers Initiative](https://www.opencontainers.org/)
    - [App Container spec](https://github.com/appc/spec)




<ac:image ac:height="250"><ri:attachment ri:filename="image2017-1-30 16:33:33.png"></ri:attachment></ac:image>



More Info / Learning : [CoreOS](https://coreos.com/rkt/docs/latest/rkt-vs-other-projects.html) / [Docker blog](https://blog.docker.com/2016/04/docker-engine-1-11-runc/) / [Docker](https://www.docker.com/products/docker-engine) /



Read about some [best-practices for writing Dockerfiles](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)





**DOCKER AND CONTAINERS**

Docker is a tool that helps ...

- To build container images
    - Images are portable across OS
    - Images are system **packages of your application**
- To run / links containers together




<ac:image ac:height="250"><ri:attachment ri:filename="image2017-1-30 16:34:22.png"></ri:attachment></ac:image>

Source:[Docker blog](https://blog.docker.com/2016/04/docker-engine-1-11-runc/)



**CLI Help:** docker-machine



**Docker Engine Supported OS**

<ac:image ac:height="150"><ri:attachment ri:filename="image2017-1-30 16:35:9.png"></ri:attachment></ac:image>



- Windows Server 2016 / Windows 10
    - Container [Windows Server Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) ([Server Core Image](https://github.com/Microsoft/Virtualization-Documentation/tree/master/windows-container-samples/windowsservercore))
    - Hyper-V ([Nano Server Image](https://github.com/Microsoft/Virtualization-Documentation/tree/master/windows-container-samples/nanoserver))
- Arch Linux, CentOS, Debian, Fedora, Gentoo, Oracle Linux, Red Hat Enterprise Linux, openSUSE and SUSE Linux Enterprise, Ubuntu




<ac:image ac:height="250"><ri:attachment ri:filename="image2017-1-30 16:39:51.png"></ri:attachment></ac:image>



**Docker Evolutions:**

- Docker Swarm
- Docker for Mac: native support with [xhyve](https://github.com/mist64/xhyve)
- Docker for Windows: support for Windows containers & Hyper-V
- Docker Datacenter / enterprise products
    - [Commercially Supported Docker Engine](https://docs.docker.com/cs-engine/release-notes/release-notes/)
    - Docker Trusted Registry (DTR)




**DOCKER IMAGES**

- **Images:**
    - ... read-only templates that are used to create containers
    - ... constructed from layered filesystems
    - ... each layer adds to or replaces part of the filesystem below it
- **Images typically contain:**
    - ... a minimal OS distribution (lightweight OS : [https://busybox.net](https://busybox.net) ~4MB \*or\* Alpine, SCRATCH)
    - ... dependencies
    - ... a single application or service
- **You can find images in public registries:**
    - ... on [Docker Hub](https://hub.docker.com/) / [Docker Store](https://store.docker.com/)
- **You can even create your own images!**




**Docker Build: Creating Images:**

<ac:image ac:height="400"><ri:attachment ri:filename="image2017-1-30 17:6:42.png"></ri:attachment></ac:image>





**Building Images with a Dockerfile:**

- Build Docker images using a Dockerfile and the **docker** **build** command
- Create a **Dockerfile**:
    - FROM debian:8
    - MAINTAINER John Citizen
    - RUN apt-get update && \
    - apt-get install -y nginx
    - EXPOSE 80
    - CMD ["nginx", "-g", "daemon off;"]
- Build the image:
    - $ docker build -t nginx-demo:1.0.0 . # Where `.` is the directory containing the `Dockerfile`
- List your images:

    - $ docker images
    - REPOSITORY TAG IMAGE ID CREATED SIZE
    - nginx-demo 1.0.0 f37c98ca1a29 36 minutes ago 196.4 MB




**Image Produced From Docker Build:**

<ac:image ac:height="250"><ri:attachment ri:filename="image2017-1-30 17:11:39.png"></ri:attachment></ac:image>

**In Replay:**

<ac:image ac:height="250"><ri:attachment ri:filename="image2017-1-30 17:12:30.png"></ri:attachment></ac:image>



<ac:image ac:height="250"><ri:attachment ri:filename="image2017-1-30 17:12:54.png"></ri:attachment></ac:image>

<ac:image ac:height="250"><ri:attachment ri:filename="image2017-1-30 17:13:31.png"></ri:attachment></ac:image>

<ac:image ac:height="250"><ri:attachment ri:filename="image2017-1-30 17:13:51.png"></ri:attachment></ac:image>

<ac:image ac:height="400"><ri:attachment ri:filename="image2017-1-30 17:14:44.png"></ri:attachment></ac:image>









**DOCKER REGISTRIES : INTRODUCTION**

- The artifact repository for images is called a Docker Registry
- You can find and retrieve images with **docker search**(\*) and **docker pull**, respectively
- You can publish your own images with **docker push**


(\*) docker search only searches the Docker Hub/Store but you can still search via the registry HTTP API





**DOCKER REGISTRIES : ROAD TO PRODUCTION**

- Upgrade your private registry in version 2 (for ease of use / combination with Docker Hub/Store)
- 1 registry per environment: dev, staging, production
- Think about data backup / disaster recovery
- Think about caching / mirroring (Registry Proxy Cache)
- Think about high-availability
- Run the Docker garbage collector to reduce disk usage






**DOCKER REGISTRIES: OPTIONS**

- [**Docker Hub**](https://hub.docker.com/): The default public registry used by Docker for public and private repositories
- [**Docker Store**](https://blog.docker.com/2016/06/docker-store/): A new marketplace for trusted and validated dockerized software – free, open source, and commercial
- [Other options include:](https://hub.docker.com/)[Gitlab Container Registry](https://docs.gitlab.com/ce/container_registry/README.html), [Docker Registry 2.x](https://docs.docker.com/registry/), [Docker Trusted Registry](https://docs.docker.com/docker-trusted-registry/), [Artifactory](https://www.jfrog.com/confluence/display/RTF/Docker+Repositories), [Nexus](https://books.sonatype.com/nexus-book/3.0/reference/docker.html), [Docker Container Registry](https://cloud.google.com/tools/container-registry/), [Amazon EC2 Container Registry (ECR)](https://aws.amazon.com/ecr/) [Google Container Registry](https://cloud.google.com/container-registry/) and [Quay.io](https://quay.io/)




**Docker Push: Publishing Images:**

<ac:image ac:height="250"><ri:attachment ri:filename="image2017-1-30 17:16:17.png"></ri:attachment></ac:image>



**PUBLISHING IMAGES TO A REGISTRY**

- Publishing is done via the **docker push** command
- However, Docker would attempt to push our images to the Docker Hub/Store
- To publish to our own registry we need to ***tag*** the image with the registry server location (in our case **registry.local:5000**)
    - $ docker tag nginx-demo:1.0.0 registry.local:5000/nginx-demo:1.0.0
- Now we can push the Docker image to the correct registry:
    - $ docker push registry.local:5000/nginx-demo:1.0.0
- We can see images in our registry at the HTTP API endpoint:[https://registry.local:5000/v2/\_catalog](https://192.168.99.100:5000/v2/_catalog)




**Docker Run: Deploying Images**

<ac:image ac:height="250"><ri:attachment ri:filename="image2017-1-30 17:17:37.png"></ri:attachment></ac:image>



**RUNNING DOCKER CONTAINERS**

- Containers consist of an operating system, user-added files, meta-data, and an executing process
- Containers add a writeable layer on top of an image (using a union file system) in which your application can then run and make changes
- Use the docker run command to launch a container:
- docker run --detach --publish 8080:80 registry.local:5000/nginx-demo:1.0.0


There are many [run options](http://docs.docker.com/engine/reference/run/) available to configure your container:

--detach means run in the background

--publish maps a host port to the container port

the last argument is the image to run

(registry.local:5000/nginx-demo:1.0.0)



**Docker Containers:**

<ac:image ac:height="400"><ri:attachment ri:filename="image2017-1-30 17:19:4.png"></ri:attachment></ac:image>



**DOCKER COMPOSE**

- [Compose](https://docs.docker.com/compose/) is a tool for defining and launching your multi-container application stacks
- You define your application stack in a file typically named:docker-compose.yml
- [docker-compose](https://docs.docker.com/compose/install/) is a separate tool to the docker CLI:


You will already have docker-compose on your laptops as part of the **DockerToolbox** installation
 
 Image source: [https://blog.docker.com/2015/11/docker-1-9-production-ready-swarm-multi-host-networking/](https://blog.docker.com/2015/11/docker-1-9-production-ready-swarm-multi-host-networking/)



**Define an application stack file (**[**docker-compose.yml**](https://docs.docker.com/compose/compose-file/)**):**

version: "2"

services:

vote:

image: registry.local:5000/vote

ports:

- "9000:80"

redis:

image: registry.local:5000/redis:alpine

worker:

image: registry.local:5000/worker

db:

image: registry.local:5000/postgres:9.4

result:

image: registry.local:5000/result

ports:

- "9001:80"



**Spin up this application stack:**

$ docker-compose up -d



**We can do**[**other things**](https://docs.docker.com/compose/reference/overview/)**with our stack too:**

$ docker-compose logs  # View container output logs

$ docker-compose kill  # Terminate all containers

$ docker-compose down  # Remove containers, networks, images, and volumes





**DEPLOYMENTS VIA COMPOSE TO PRODUCTION?**

- Docker Compose is a useful tool for development purposes but not a good choice for production deployments
- It [does not directly support working with the new Docker swarm mode](http://stackoverflow.com/questions/38353959/docker-compose-with-docker-1-12-swarm-mode)
- It requires legacy Docker Swarm to deploy into a multi-host environment -- which lacks many features (e.g. services, desired state)
- It handles services as a client-side concept not a server-side concept (as in swarm-mode)
- You might want to manage your containers differently, e.g. using the **systemd** init system






**Exercise #2: Docker CLI + Basics**

[file:///Users/pvarga/Projects/DockerStuff/usb-stick/exercises/02-basics/README.html](file:///Users/pvarga/Projects/DockerStuff/usb-stick/exercises/02-basics/README.html)



### **Review Docker CI/CD Lifecycle**

**Build &gt; Publish &gt; Deploy/Run**

<ac:image ac:height="400"><ri:attachment ri:filename="image2017-1-30 17:20:45.png"></ri:attachment></ac:image>





**CLUSTERING: WHY IS IT REQUIRED?**

- Fault tolerance and high availability
- Need for dynamic application scaling
- Single host capacity is usually insufficient
- Distributed systems: Databases, Queues/workers
- Server costs: High density server / workloads optimization
- Intelligent deployment orchestration - Based on host resources






**CLUSTERING : FOR PRODUCTION**

- A real-world production environment does not usually consist of a single host running the application and services






**CLUSTER CONCEPTS**

- Dynamic load balancing
- Service discovery
- Desired state
- Self healing
- Auto scaling
- Automated host provisioning








**LOAD BALANCING & SERVICE DISCOVER:**

**APPLICATION INSTANCES AND LOCATIONS ARE NOT STATIC**

- **Service registry / inventory**
    - Discover/register all available services of the cluster
    - Dynamically reconfigure load balancer(s)
- **Load balancer**
    - Route every request to a registered service
    - Critical component (Design for high availability)
- **Tools**
    - Service discovery: Consul + Registrator, Etcd, Kubernetes proxy
    - Load balancer/Reverse proxy: Traefik, Nginx, HAProxy






**DESIRED STATE: BASED ON THE RECONCILIATION MODEL**

- Concept similar to CM tools: Chef/Puppet/Ansible
    - Configuration described the desired state of infrastructure
    - Cluster manager guarantees the desired state
- **For example:**
    - Desired state:
    - *"I want at least 2 instances of my frontend service to be running"*
    - If one of the frontend containers goes down, the cluster manager creates a new one






**SELF HEALING: DESIGN FOR FAILURE**

- **Service health**
    - Failure detection and automated remediation based on [service healthchecks](https://docs.docker.com/engine/reference/builder/#/healthcheck)
    - Cluster manager checks if each service is healthy
        - If yes, nothing to be done
        - If not, different healing mechanisms: Service relocation / restart / replication / auto-scaling
- **Host health**
    - How long does it take to run?
        - $ docker -H tcp://[host]:2376 info
    - ...If longer than a few seconds then daemon maybe dead
    - ...How will you automatically spin up a new, replacement node?








**AUTO SCALING: HOST LEVEL**

- **Scaling up/down:**
    - Up: CPU utilisation on a node / the cluster exceeds 80% for 15 mins
    - Down: Memory utilisation on a node / the cluster is under 40% for 15 mins
- **Tightly coupled with infrastructure**
    - Openstack Heat
    - AWS Cloud Formation / Cloudwatch alarms and triggers
    - HashiCorp Terraform




**You’ll need experimentation to adapt it to your applications!**







**AUTO SCALING: CONTAINER LEVEL**

- **Tightly coupled with orchestration tool:**
    - [Mesos](https://mesosphere.com/blog/2015/10/06/visualizing-50000-live-containers-how-we-built-our-mesoscon-15-demo/) (\*\* for large clusters)
    - [Kubernetes](http://blog.kubernetes.io/2016/07/autoscaling-in-kubernetes.html)[(\*\* for large clusters)](https://mesosphere.com/blog/2015/10/06/visualizing-50000-live-containers-how-we-built-our-mesoscon-15-demo/)
    - [Swarm / Universal Control Plane](https://blog.docker.com/2015/02/scaling-docker-with-swarm/)
    - [AWS ECS](https://aws.amazon.com/ecs/)








**AUTOMATED CONTAINER PROVISIONING: KUBERNETES - POD DEFINITION / REPLICATION CONTROLLER**

apiVersion: v1

kind: ReplicationController

metadata:

name: busmeme-rc

labels:

name: web

spec:

replicas: 2 # tells deployment to run 2 pods matching the template

selector:

name: web

template: # create pods using pod definition in this template

metadata:

labels:

name: web

spec:

containers:

- image: mongo

name: mongo

ports:

- name: mongo

containerPort: 27017

hostPort: 27017

volumeMounts:

- name: mongo-persistent-storage

mountPath: /data/db

- image: minillinim/busmemegenerator

name: web

ports:

- containerPort: 3000

env:

- name: NODE\_ENV

value: "production"

- name: PORT

value: "3000"

- name: BM\_MONGODB\_URI

value: "[mongodb://localhost/app-toto](mongodb://localhost/app-toto)"

volumes:

- name: mongo-persistent-storage

hostPath:

path: /data/db





**AUTOMATED CONTAINER PROVISIONING - DAB EXAMPLE:**

**DISTRIBUTED APPLICATION BUNDLE (EXPERIMENTAL)**

- Dockerfile -&gt; Image -&gt; Container
- Docker Compose -&gt; [Distributed Application Bundle](https://docs.docker.com/compose/bundles/) -&gt; Docker Stack






**Exercise #3A : Advanced Clustering**

[file:///Users/pvarga/Projects/DockerStuff/usb-stick/exercises/03-advanced-clustering/README.html](file:///Users/pvarga/Projects/DockerStuff/usb-stick/exercises/03-advanced-clustering/README.html)







**Exercise #3B : Advanced Logging**

[file:///Users/pvarga/Projects/DockerStuff/usb-stick/exercises/03-advanced-logging/README.html](file:///Users/pvarga/Projects/DockerStuff/usb-stick/exercises/03-advanced-logging/README.html)



**Voting App URL:**

[http://192.168.99.100:9000/](http://192.168.99.100:9000/)



**docker-compose** logs -f worker



**docker-machine** ssh manager1 "rm -rf /tmp/fluentd; mkdir -p /tmp/fluentd"



**docker** service create \

--name fluentd \

--replicas 1 \

--user 1000 \

--publish 24224:24224 \

--mount "type=bind,src=/tmp/fluentd,dst=/fluentd/log" \

--constraint "node.hostname == manager1" \

registry.local:5000/fluent/fluentd:v0.12.29



**docker** service ps fluentd



In a production environment you should be running a Fluentd instance on each Docker host and forwarding logs to another server not storing them on the same Docker host. You can ship logs to a logging solution such as syslog, Graylog, Splunk, ELK, Amazon Cloud Watch Logs, etc for analysis and retention.



**docker** network ls :: list all network nodes

**docker**-machine ls :: list all machines running

**docker** service ls :: list of services



// Cleanup

**docker-compose** down :: kills all network services

**docker** service rm fluentd :: remove the fluentd logger





**FluentD** **References**

- [Fluentd Quickstart](http://docs.fluentd.org/articles/quickstart) -- Official Fluentd Quickstart Guide
- [Configure logging drivers](https://docs.docker.com/engine/admin/logging/overview/) -- reference information on using Docker's logging drivers (see: [Fluentd options](https://docs.docker.com/engine/admin/logging/overview/#/fluentd-options))
- [Fluentd docker image](https://github.com/fluent/fluentd-docker-image)
- [Getting Data From Json Into Elasticsearch Using Fluentd](http://docs.fluentd.org/articles/recipe-json-to-elasticsearch)






**LOGGING: WHY IS IT IMPORTANT?**

- Ephemeral nature of containers implies loss of context: where/for how long/which containers are running?
- Log correlation between containers
- Need for live analysis
- Retention of information in case of catastrophic events






**CENTRALISED LOGGING: ANALYZE CLUSTER-WIDE ISSUES**

- Docker daemon logs
- Centralized and remote containers logging
- Containers lifecycle / Exit signals
- Health check / Restart policies






**CONTAINER LOGS: Log correlation / log content is important**

- Timestamp with time zone (Ideally UTC)
- Docker host FQDN/IP
- Container ID
- Image name and tag








**LOGGING STRATEGIES: Depends on OS / existing log strategy / centralized logging solution**

- Default logging driver: json-file
- Other options: journald, fluentd, splunk, awslogs
- Log collectors as containers and host log forwarding: logspout, sumologic








**Exercise #3C : Advanced Monitoring**

[file:///Users/pvarga/Projects/DockerStuff/usb-stick/exercises/03-advanced-monitoring/README.html](file:///Users/pvarga/Projects/DockerStuff/usb-stick/exercises/03-advanced-monitoring/README.html)





**MONITOR PROCESS / RESOURCES USAGE**

**Some useful tools to monitor containers:**

- [cAdvisor](https://github.com/google/cadvisor)
- [sysdig](https://sysdig.com/)
- [collectd-docker](https://github.com/bobrik/collectd-docker)
- [systemd-cgtop](https://www.freedesktop.org/software/systemd/man/systemd-cgtop.html)




$ docker top

$ docker stats



**Control groups**

Resources isolation with cgroups: CPU, Memory, Block I/O, Network, Devices



**Namespaces**

Processes isolation with namespaces



Limit the resource visibility

Processes with their own view of the system

- **pid:** Each PID namespace has its own numbering (parent PID 1)
- **net:** Define network interfaces / rules
- **mnt:** Provide its own rootfs (~chroot)
- **user:** Map processes GID/UID to host GID/UID
- **uts:** Hostname and NIS domain name
- **ipc:** System V IPC, POSIX message queues








**Networking:**

[file:///Users/pvarga/Projects/DockerStuff/usb-stick/slides/index.html#/part-3-networking](file:///Users/pvarga/Projects/DockerStuff/usb-stick/slides/index.html#/part-3-networking)



**Docker uses virtual networks & software defined networking to:**

Connect containers together

Connect containers to a host

Connect containers on a multi host env (overlay networks)



$ docker network ls

$ docker network [create|rm|inspect|connect|disconnect] [NETWORK]

$ docker run --network=[NETWORK]







**DOCKER DEFAULT NETWORKS**

- **None:** Disable container networking
- **Host:** Containers IP config == Host IP config, public/direct network exposure
- **Bridge(docker0):** Virtual ethernet bridge that connects to containers eth0 interfaces








**MULTI HOST NETWORKS**

**Container-to-container communication across multiple hosts**

- Grouping containers by subnet
- Better network isolation of containers
- Relies on overlay traffic encapsulation (tunneling)
    - docker network create --subnet=10.0.1.0/24
- **Examples:** Flannel for Kubernetes, Swarm mode / overlay driver








**DOCKER SECURITY!**

[file:///Users/pvarga/Projects/DockerStuff/usb-stick/slides/index.html#/part-3-security](file:///Users/pvarga/Projects/DockerStuff/usb-stick/slides/index.html#/part-3-security)



**SECURITY ASPECTS**

Containers reduce attack surfaces and isolate applications to only the required components, interfaces, libraries and network connections



- [Docker Security Bench](https://github.com/docker/docker-bench-security) : script to help you compare against best practices
    - The Docker Bench for Security is a script that checks for dozens of common best-practices around deploying Docker containers in production. [https://dockerbench.com](https://dockerbench.com/)






**SECURITY LEVELS**

- Docker daemon configuration
- Docker registry
- Images
- Container-to-host security
- Container-to-container security
- Container security
- Secrets management






**DOCKER DAEMON SECURITY**

**Mitigate container breakouts**

- Host machine should run only the essential services
- Disable default inter-container communication
    - daemon docker  --icc=false
- [Daemon user namespace options](https://docs.docker.com/engine/reference/commandline/dockerd/#daemon-user-namespace-options)
- User Namespaces (&gt;1.10) allows the root user in a container to be mapped to a non uid-0 user outside the container






**DOCKER REGISTRY SECURITY**

- Do not use insecure registries
- Use TLS/SSL communication with Docker clients
- Enterprise-class authentication: AD/LDAP support
- Role based access control: Who is able to pull or push images?
- Tools on top of Docker registry:
    - SUSE Portus
    - VMWare Harbor
    - [Redhat Satellite 6](https://www.redhat.com/en/technologies/management/satellite)






**IMAGE SECURITY**

- Build your own images if possible
- Use only trusted base images from the Docker Hub / Store
- Use SHASUM check, Docker Trusted Registry, or setup [Notary](https://docs.docker.com/notary/getting_started/)
- Rebuild the images to include security patches
- USER instruction to set UID to use when running the image
- Avoid large distributions (Ubuntu, CentOS) / prefer minimal distributions: Alpine, BusyBox, SCRATCH
    - Reduces attack surface
    - Less patching requirements
    - Download time decreased






**Docker Vulnerability Scanner:**

Source [Docker Hub](https://hub.docker.com/r/library/mongo/tags/latest/) (Must be logged in) — This link is broken







**CONTAINER-TO-HOST SECURITY**

- Since Docker 1.11, number of active processes running inside a container can be limited to prevent fork bombs
- This requires a linux kernel &gt;= 4.3 with CGROUP\_PIDS=y to be in the kernel configuration




$ docker run --pids-limit=64





**CONTAINER-TO-CONTAINER SECURITY**

**Least access strategy**

- Restrict incoming traffic to the right host interface
- $ docker run --detach --publish [ip]:[source-port]:[dest-port] [image]
- Mount root file-system or volumes as read-only
    - $ docker run -d --read-only [image]
 
 $ docker run -d -v /src/[webapp:/webapp:ro](http://webapp/webapp:ro) [image]




**CONTAINER SECURITY**

- Mandatory Access Control (MAC)
    - Create your own SELinux, AppArmor profiles, [Seccomp profiles](https://docs.docker.com/engine/security/seccomp/)
- Reduce kernel [capabilities](https://docs.docker.com/engine/reference/run/#/runtime-privilege-and-linux-capabilities)
- Use non privileged containers






**SECRETS MANAGEMENT**

- Do not store secrets (Tokens, Keys, Passwords) in Dockerfiles and/or images
- Do not store secrets in environment variables because they are shared by the system/docker inspect: use KV stores (Vault)
- Use secret management Key-Value stores (e.g. [Vault](https://www.vaultproject.io/), [AWS KMS](https://aws.amazon.com/kms/))








**CONTINUOUS INTEGRATION**

**Automated Build:** Build images on git repository events: push, tags



[file:///Users/pvarga/Projects/DockerStuff/usb-stick/slides/index.html#/125](file:///Users/pvarga/Projects/DockerStuff/usb-stick/slides/index.html#/125)





**CI: CONTAINER USAGE TIPS**

- Dev/prod parity: Build once, deploy everywhere
- Do not bundle dev/test dependencies in your images
    - $ docker run myprod:image sh -c "npm install --dev && npm test"
- Include project/build number in Docker image tags
    - $ docker tag imageName ${imageName}:${version}.${buildNumber}
- Use volumes to keep your test reports outside of containers available after tests
- Use volumes to cache files and reduce testing times (software dependencies are good candidates: npm, m2, composer, etc)




**CI TIPS:**

- Volumes != Persistance
- Volumes are not garbage collected
- It is ok to use same images for stateful (database) container and its corresponding data-only container
- Use load balancers (like HAProxy) to scale your services
- Put containers with sensitive data on their own host
- Ensure your services provide healthcheck endpoints so that load balancers can stop routing traffic to unhealthy instances
- Cache images whenever possible, download takes a long time








**DOCKER NEXT STEPS: ADOPTING DOCKER INTO ORG**

[**file:///Users/pvarga/Projects/DockerStuff/usb-stick/slides/index.html#/133**](file:///Users/pvarga/Projects/DockerStuff/usb-stick/slides/index.html#/133)







Also investigate:

- Ansible : [https://www.ansible.com/](https://www.ansible.com/)
- Docker can run health checks against containers
- Get log aggregation and monitoring in place early
- Only look at a cluster management once when you understand Docker and its edge-cases properly
- You may not need advanced schedulers like Mesos and Kubernetes for your Enterprise apps just yet - but it's worth understanding what they provide to know if you need them or can just get away with swarm-mode and your own scripts
- One app/service per container
- Images as build artifacts
- Immutable servers!




**CLUSTER MANAGEMENT, SCHEDULING AND ORCHESTRATION**

- [DC/OS](https://dcos.io/) (Mesos, Marathon, and more)
- [Kubernetes](http://kubernetes.io/)
- [Swarm (now](https://dcos.io/)[swarm-mode](https://docs.docker.com/engine/swarm/))
- [Nomad](https://www.nomadproject.io/)




**HOSTED CONTAINER-AS-A-SERVICE (CAAS) OFFERINGS**

[AWS ECS](https://aws.amazon.com/ecs/)

Hosted Kubernetes:
 ([Google Container Engine](https://cloud.google.com/container-engine/), [Tectonic](https://tectonic.com/), [OpenShift Online](https://www.openshift.com/))

[Docker Cloud](https://cloud.docker.com/) (formerly Tutum)

[Joyent Triton](https://www.joyent.com/)

[Heroku](https://devcenter.heroku.com/articles/container-registry-and-runtime)

[AWS Lambda](https://aws.amazon.com/lambda/details/) (Functions as a Service that run in containers)



**SELF-HOSTED CONTAINER-BASED CAAS/PAAS**

[Deis Workflow](https://deis.com/workflow/) (Kubernetes)

[Rancher](http://rancher.com/) (Kubernetes, Mesos, Swarm, Cattle)

[Docker Datacenter](https://www.docker.com/products/docker-datacenter) (On-premise, also [offered by AWS](https://aws.amazon.com/docker/docker-datacenter/))

[CloudFoundry](https://www.cloudfoundry.org/) (Pivotal, IBM, etc.)

[Red Hat Openshift Container Platform](https://www.openshift.com/container-platform/)



**SHORT-LIVED CONTAINERS!**

- Spin up containers on demand, perhaps for specific users
- Google does this all the time!
- Can be a great way to reduce resources required to run your system...
- ...and keep process/data isolated...
- ...and improve security...
- ...but you'll have to do some work yourselves to make this work!
- Unless you can use something for this purpose, like...
- ...[AWS Lambda](https://aws.amazon.com/lambda/) (or [Azure Functions](https://azure.microsoft.com/en-us/services/functions/), [Google Cloud Functions](https://cloud.google.com/functions/))
- ...aka "[Serverless](http://martinfowler.com/articles/serverless.html)" computing
- First-class Docker support on Windows Server with [Windows Server Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview)




**STORAGE**

[*"Storage is hard" \[1\]*](https://www.youtube.com/watch?v=X_q2l8hotAc)...but, still a lot [going on](https://docs.docker.com/v1.9/engine/extend/plugins/) in this area.



**SELECTION OF VOLUME PLUGINS**

1. [Flocker](https://clusterhq.com/flocker/introduction/) (ClusterHQ):Volume portability, supports many backends
2. [netappdvp](https://github.com/NetApp/netappdvp) (NetApp): iSCSI/NFS on NetApp storage
3. [blockbridge-docker-volume](https://github.com/blockbridge/blockbridge-docker-volume) (Blockbridge): Vendor-specific
4. [Netshare](http://netshare.containx.io/) (ContainX): NFS, AWS EFS & Samba/CIFS
5. [REX-Ray](http://rexray.readthedocs.io/en/stable/) (EMC): AWS EBS, GCE, Cinder, EMC, VirtualBox
6. [Contiv Storage \[2\]](http://contiv.github.io/#storage-hdr)[(Cisco): Ceph, NFS](https://github.com/NetApp/netappdvp)
7. [Convoy](https://github.com/rancher/convoy) (Rancher): Volume backup/restore, snapshot, migration
8. [Open Storage](https://github.com/libopenstorage/openstorage): Stateful services in multi-host Docker environment






**NETWORKING:** **OVERLAYS**

1. [Weave Net](https://www.weave.works/products/weave-net/): Network plugin supporting VXLAN, Service Discovery (DNS), Encrypted traffic (IPSec), Load Balancing
2. [libnetwork](https://github.com/docker/libnetwork/blob/master/docs/design.md): Core Docker library supporting driver / plugin model (built-in Overlay needs external KV-store)
3. [Swarm Mode Overlay](http://collabnix.com/archives/1391): New in Docker Engine 1.12




**NETWORKING: ALTERNATIVES**

1. [Calico](https://www.projectcalico.org/): Can be deployed without encapsulation or overlays to provide high performance at massive scales
2. [Contiv Networking](http://contiv.github.io/documents/networking/): Pluggable networking alternative to built-in Docker, Kubernetes, Mesos, and Nomad ecosystems






**UNIKERNELS!**

- Allows you to build specific purpose kernels for a given process
- Promise to be even leaner than containers...
- And provide better isolation, as the kernels are separate
- Could provide the speed/lightweight nature of containers, with the improved separation of VMs
- But tooling in this space is where it was for containers several years ago, although...



