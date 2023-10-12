
**Microservices Workshop**



Jenkins / Snap / Go CD / Terraform : [https://www.terraform.io/](https://www.terraform.io/) / AWS CloudFormation (Service)



[https://www.terraform.io/docs/providers/openstack/index.html](https://www.terraform.io/docs/providers/openstack/index.html)



[https://aws.amazon.com/cloudformation/](https://aws.amazon.com/cloudformation/)







*Teams continuously deliver new versions of software to production by decreasing the cycle time between an idea and usable software through the automation of the entire delivery system: build, deployment, test, and release.*

[DZone Refcardz: Continuous Delivery](http://refcardz.dzone.com/refcardz/continuous-delivery-patterns)



- Continuous Delivery (CD) takes Agile and Continuous Integration further by enabling frequent, automated, repeatable, low-risk delivery into Production ("the last mile")
- The CD pipeline is a key construct used to automate the delivery process
- Software is always in a releaseable state - each commit is a release candidate until proven otherwise
- Demonstrates real progress - no delayed integrations; visibility
- Exposes bottlenecks and other inefficiencies
- Provides rapid feedback at all stages of the delivery process
- Fits well into distributed team structures










**Good Refs:**

[Continuous Delivery (Book)](http://www.amazon.com/dp/0321601912), Jez Humble and David Farley

[DZone Refcardz: Continuous Delivery](http://refcardz.dzone.com/refcardz/continuous-delivery-patterns)

[Implementing Continuous Delivery (ThoughtWorks)](http://info.thoughtworks.com/putting-continuous-delivery-into-practice-slideshare.html?aliId=5510306) - Slide series



**FYI:**

vagrant destroy

vagrant up

vagrant ssh

./up.sh

docker ps



**Module1 ReadMe:**

[file:///Users/pvarga/projects/microservicesworkshop/workshop/workshop/workshop-dist/topics/finish/module1/README.html](file:///Users/pvarga/projects/microservicesworkshop/workshop/workshop/workshop-dist/topics/finish/module1/README.html)





**CI/CD Tips:**

- Use CD Pipelines to automate your build process and provide feedback on production readiness of software
- Model your build process as a series of stages for improved feedback
- Provide scripts for building, testing, packaging and deploying your apps:
    - Store these with your app code
    - Call them from your CI/CD tool
- Build artifacts once and use them in downstream stages / pipelines
- Always tag your build artifacts with a build number
- Extend your CD pipeline to automate deployment into your environments
- Monolithic apps can be easy to build and deploy as they have less moving parts






**Module 2:**

[file:///Users/pvarga/projects/microservicesworkshop/workshop/workshop/workshop-dist/topics/finish/module2/README.html](file:///Users/pvarga/projects/microservicesworkshop/workshop/workshop/workshop-dist/topics/finish/module2/README.html)





**DOCKER OVERVIEW**

*"Docker containers wrap a piece of software in a complete filesystem that contains everything needed to run... This guarantees that the software will always run the same, regardless of its environment."*([docker.com/what-docker](https://www.docker.com/what-docker))



**Characteristics:**

1. Lightweight virtualisation
2. Built on open standards (Portability!)
3. Resource isolation at the kernel
4. Thriving ecosystem - adoption and competition






**DOCKER REFERENCES**

- [The Docker Book (eBook)](http://www.dockerbook.com/), James Turnbull
- [Introduction to Docker (Video)](https://www.youtube.com/watch?v=Q5POuMHxW-0)[- Solomon Hykes](http://www.dockerbook.com/)
- [Docker User Guide](https://docs.docker.com/userguide/)[- Getting Started](http://www.dockerbook.com/)
- [Docker Command Line](http://docs.docker.com/reference/commandline/cli/) - Command-line reference
- [Dockerfile Reference](https://docs.docker.com/reference/builder/) - Building Docker images






**Tips:**

- It's ok to start with a monolith then extract services once you understand your business domain and bounded contexts
- Keep your Docker images small
- Don't use Docker containers like full blown VMs - Run only 1 process in each Docker container
- Use Docker Networking to communicate between containers (on the same host)
- Bounded Context helps you define your microservices






**Module3:**

[file:///Users/pvarga/projects/microservicesworkshop/workshop/workshop/workshop-dist/topics/finish/module3/README.html](file:///Users/pvarga/projects/microservicesworkshop/workshop/workshop/workshop-dist/topics/finish/module3/README.html)





**References:**

- [What are Consumer Driven Contracts?](http://martinfowler.com/articles/consumerDrivenContracts.html)
- [Why use Consumer Driven Contracts?](http://www.slideshare.net/ThoughtWorks/sam-newman-deployingandtestingmicroservices)
- [Who is using CDCs?](http://www.slideshare.net/bethesque/pact-39214472)
- [Interested in using or extending Pact?](https://github.com/realestate-com-au/pact)




*[CDC] imbues providers with insight into their consumer obligations, and focuses service evolution around the delivery of the key business functionality demanded by consumers.* ([MartinFowler.com](http://martinfowler.com/articles/consumerDrivenContracts.html))



**Consumer Driven Contracts : Characteristics:**

1. Encourages independently evolving services
2. Share contracts, not types
3. Reduce reliance on end-to-end integration testing
4. CDCs are a codified set of discussions about how a service API should look
5. Failures are a trigger for a conversation






**CDC REFERENCES**

- Chapter 7 - [Building Microservices (Book)](http://shop.oreilly.com/product/0636920033158.do), Sam Newman
- [Consumer-Driven Contracts: A Service Evolution Pattern (Article)](http://martinfowler.com/articles/consumerDrivenContracts.html), Ian Robinson
- [Pacts to the Rescue (Slides)](http://www.slideshare.net/bethesque/pact-39214472), Beth Skurrie
- [realestate-com-au/pact (Github repo)](https://github.com/realestate-com-au/pact)






**TIPS AND ADVICE**

1. Use CDCs to reduce the reliance of heavy end-to-end or large-scale integration testing
2. Pact is a great tool for implementing CDCs in Ruby, .NET, or JVM languages
3. Have consumer CI builds generate pact files as artifacts on every check-in
4. Have service providers consume pact file artifacts on every provider CI build
5. Avoid coupling service provider pipelines directly to consumer pipelines
6. Use an external artifact store or the [Pact Broker](https://github.com/bethesque/pact_broker)






**Presentation Summary:** [file:///Users/pvarga/Projects/MicroServicesWorkshop2/slides/slides/index.html](file:///Users/pvarga/Projects/MicroServicesWorkshop/slides/slides/index.html)





—————————



**Previous “Junky” Notes:**



Micro services Hands on Workshop



Continuously Delivering Microservices



pvarga\OreillyConf\MicroSvcs



BTD Microservices using Docker



Slide Deck:

[file:///Users/pvarga/OreillyConf/MicroSvcs/slides/index.html](file:///Users/pvarga/OreillyConf/MicroSvcs/slides/index.html)





ls -lart



module1:

[http://localhost:8153/go/home](http://localhost:8153/go/home)

[http://localhost:8090/](http://localhost:8090/)   (not 8080 as in the slides)





Do this challenge:

[file:///Users/pvarga/OreillyConf/MicroSvcs/slides/index.html#/30Module1](file:///Users/pvarga/OreillyConf/MicroSvcs/slides/index.html#/30Module1)



Learn more about VAGRANT vms



Thought works: GO-CD



docker ps &gt; check running containers



Learn about Docker:

[file:///Users/pvarga/OreillyConf/MicroSvcs/slides/index.html#/57](file:///Users/pvarga/OreillyConf/MicroSvcs/slides/index.html#/57)





Docker Exercise:

[file:///Users/pvarga/OreillyConf/MicroSvcs/tw-microservices-workshop/workshop-dist/topics/finish/module2/README.html](file:///Users/pvarga/OreillyConf/MicroSvcs/tw-microservices-workshop/workshop-dist/topics/finish/module2/README.html)





Consumer Driven Contracts:

[file:///Users/pvarga/OreillyConf/MicroSvcs/slides/index.html](file:///Users/pvarga/OreillyConf/MicroSvcs/slides/index.html)



[file:///Users/pvarga/OreillyConf/MicroSvcs/tw-microservices-workshop/workshop-dist/topics/finish/module3/README.html](file:///Users/pvarga/OreillyConf/MicroSvcs/tw-microservices-workshop/workshop-dist/topics/finish/module3/README.html)



[http://localhost:8153/go/pipelines](http://localhost:8153/go/pipelines)



[http://localhost:8090/](http://localhost:8090/)
