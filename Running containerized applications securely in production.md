
[Running containerized applications securely in production](http://conferences.oreilly.com/software-architecture/engineering-business-ca/public/schedule/detail/53884)

Giuseppe de Candia (Midokura) : MidoNet : MidoNet : MidoKura



A recent study by New Relic shows that 46% of deployed containers run for one hour and 27% run for about five minutes—talk about short lived. In such a fast-paced, disposable computing environment, cloud operators have a difficult time dealing with workloads and keeping the container environment from turning into unmanageable chaos.

Today, more and more applications are being packaged into containers and deployed in microservices architecture. Containerization and microservices go in hand in hand. When applications are scaled out across multiple host systems to keep up with growing demands, the ability to manage each host system and abstract away the complexity of the underlying platform becomes attractive. At a macro level, being able to provide a seamless network for multicloud (say on-premises private with a public cloud) becomes imperative.

Cloud operators must consider how to schedule containers to prevent resource contention, how to implement container isolation to ensure security containment (in case of a breach), what it means to network containers together, what it means for provisioning, load balancing, and availability, and how to perform analysis and troubleshooting of containers in spite of the short life span.

However, the downside of networking in microservices architecture is that it often creates more components to manage and more endpoints to secure. Thus, keeping configurations consistent and maintaining security policies becomes even more challenging than it already is.

This is where advanced schedulers and network virtualization come into play. Advanced scheduling technologies, such as Kubernetes, allow much more control over the containers running on the infrastructure. Containers can be labeled, grouped, and given their own subnet for communication.

Giuseppe de Candia explains how to take the chaos out of these short-lived computing engines and the security implications to consider along the way.



Topics include:

- How advanced scheduling, container orchestration, and open source network virtualization work together to provide the automation for networking containers, load balancing, and making the network highly available
- How labels and security groups can provide fine-grain control that allows cloud operators to implement their own tenant-level, protocol-level, port-level security on the containers
- How advanced analytics tools, such as Elasticsearch and Logstash, can provide context on what the containers are actually doing and troubleshoot application performance issues without having to track down the container or identify the host or security policies that were applied to them




**Overview: Networking Aspects of Security**

- Understand ops and monitoring best practices and gain exposure to advanced analytics tools




Terminology Level-Set:

Pods + Containers : Interchangeable : Any unit with a network interface



Hosts, Minions, and Agents:

Host: Virtual platform

Minion: Controlled by some central platform

Agents: Turn a host into a minion



IP-per-Container model : Fixes horizontal security flaws + port mapping (managing)



Port Scanning + IP Range Scanning



**12 Factor Applications** (Design Principles) : [https://12factor.net/](https://12factor.net/)



**Software-Defined Networking (SDN) :**[https://www.opennetworking.org/sdn-resources/sdn-definition](https://www.opennetworking.org/sdn-resources/sdn-definition)



Layer 4-7 Network Services: [http://whatis.techtarget.com/definition/Layer-4-7-Layer-4-through-Layer-7-services](http://whatis.techtarget.com/definition/Layer-4-7-Layer-4-through-Layer-7-services)



Network Layers Explained: [http://searchnetworking.techtarget.com/answer/Network-layers-explained](http://searchnetworking.techtarget.com/answer/Network-layers-explained)



Network Layers:

- Application layers (the upper layers)
    - 7 - Application layer
    - 6 - Presentation layer
    - 5 - Session layer
- Data transport layers (the lower layers)
    - 4 - Transport layer
    - 3 - Network layer
    - 2 - Data link layer
    - 1 - Physical layer





