#   Application Deployment Models

&nbsp;

The concept of cloud has wormed its way into almost every facet of modern life.  It has become central to how we interact with our friends, buy things, watch TV and movies, and run our businesses.  So what is it really?  Well, what is a very subjective question that has to take into account your own personal perspective.  If you asked five people what cloud if, you would probably get eight different answers.  Nearly half of all business meetings about cloud, when it was in its infancy, were spent on determining what it was and how it could be used.  Is it a service?  Is it a product?  Is it something magical that will solve all business problems?

&nbsp;

The biggest issue with this line of thinking is trying to call cloud a "thing" in the first place.  The key value of cloud is that it gives you a new way of operating IT - allowing it to be fast, agile, and able to align better to the goals of the business.  From this perspective, cloud can help transform manual and inefficient processes into something the business can use as a competitive advantage and a way to better serve customers.  The strength of cloud is realized in the speed and agility it affords as an operational model to get applications deployed and providing value more quickly.  Cloud fundamentally changed howe we think about building and operationalizing applications.

&nbsp;

Today Amazon, Google, Microsoft, Cisco, and others offer cloud services.  Many startups are building their applications and services completely in the cloud.  Uber, for example, has completely transformed the transportation industry through a cloud-based application that allows us to easily find someone willing to pick us up and take us where we want to go.  Square has transformed credit card processing by allowing anyone with a smartphone and an inexpensive hardware add-on to take credit card payments.  The growth of cloud services like these will continue at a steady pace, forcing businesses to rethink how they engage with their customers and operate business-critical services.

&nbsp;

#   NIST Definition

&nbsp;

To define cloud, we need a common taxonomy, and for that we can turn to the ***National Institute of Standards nad Technology (NIST)***, a U.S. government agency responsible for standardizing weights, measurements, and technology standards and practices.  NIST ***Special Publication (SP)*** 800-145 was written to solve the "what is cloud" dilemma.  While SP 800-145 is a rather short document, it hits on the major aspects of cloud and is therefore useful as a framework for understanding application deployment options and prepping for the 200-901 DevNet Associate DEVASC exam.  ***In SP 800-145, NIST defines cloud through three primary lenses: essentially characteristics, service models, and deployment models (see Figure 13-1).***

&nbsp;

>   ***`Key Topic`***

&nbsp;

**Figure 13-1** *NIST Cloud Computing Definition*

![Figure 13-1 NIST Cloud Computing Definition](assets/images/Figure%2013-1%20NIST%20Cloud%20Computing%20Definition.jpeg)

&nbsp;

##  Essential Characteristics

&nbsp;

According to SP 800-145, the essential characteristics describe the core requirements of any cloud and are the differentiators that determine whether a service can be classified as being a cloud offering.  SP 800-145 defines the essential characteristics as follows:

-   **Broad network access**:  Services are available over the network and accessed via standard protocols and communications technologies on any type of client device (mobile phone, tablet, desktop, and so on).
-   **Rapid elasticity**:  Capacity can be automatically provisioned and decommissioned to scale the service to demand.
-   **Measure service**:  Cloud systems measure resource utilization (compute, storage, and network) and charge for those services accordingly.  Utilization is monitored, controlled, and reported on, allowing transparency for the service provider and customers.
-   **On-demand self-service**:  The cloud consumer can provision compute, storage, and network as needed, without human interaction, through automation or self-service portals.
-   **Resource pooling**:  The infrastructure is a common pool of resources that can serve multiple customers at the same time.  The customer does not interact with the underlying hardware, and workloads can be moved within the cloud environment based on demand without the end user knowing or needing to be involved.

&nbsp;

## Service Models

&nbsp;

The cloud service models mainly differ in terms of how much control/administration the cloud customer has to perform.  Figure 13-2 shows the following service models:

&nbsp;

**Figure 13-2** *Cloud Service Models*

![Figure 13-2 Cloud Service Models](assets/images/Figure%2013-2%20Cloud%20Service%20Models.jpeg)

&nbsp;

-   **Software as a service (SaaS)**:  A service provider hosts, manages, and controls an application and offers it to the customer to use.  The customer does not interact at all with the underlying infrastructure, operating system, storage, or network.  There may be some customization capabilities, but they are usually limited to application-specific configuration.  What you see is what you get.
-   **Platform as a Service (PaaS)**:   A PaaS provider supplies a fully integrated service/software suite, and customers can deploy their application on top of this suite with a predefined set of application programming interfaces, libraries, software development kits, and/or other tools and services.  Customers can program the application in any way they choose and can customize it directly to their own workflow as long as the customization is within the parameters of the service provider's offering.  Customers do not have to worry about integration of the underlying infrastructure components and in the case of a managed PaaS service, have no management responsibilities for the underlying infrastructure.
-   **Infrastructure as a service (IaaS)**: A provider enables the customer to provision compute, storage, and networking to run any combination of software and operating systems.  While customers have no control of the underlying infrastructure hardware platform, they have full control over the software and service they deploy within the cloud service.  The customer is also responsible for the maintenance of the software they deploy, including patching and upgrading.

&nbsp;

#  Application Deployment Options

&nbsp;

Cloud can be deployed in a number of ways.  The deployment model chosen depends on whether you want to own your own infrastructure, rent your infrastructure, or have a mixture of both.  There are a multitude of reasons you might choose one option over the others.  Factors such as protecting sensitive data, economics, and speed all ned to be weighed in making choices between deployment models.

&nbsp;

>   ***`Key Topic`***

&nbsp;

##  Private Cloud

&nbsp;

A private cloud is provisioned for a single organization that may have multiple service consumers within its business units or groups (see Figure 13-3).  The organization may own the private cloud or lease it from another entity.  It also does not have to reside on the organization's premises and may be in another facility owned and operated by a third party.  The following are the key characteristics of a private cloud:

-   A private cloud has dedicated resources for a single organization.
-   Connectivity can occur through the Internet, fiber, or a private network.
-   A private cloud may be on premises or off premises.
-   Applications are deployed within a private cloud, and the organization has complete control and responsibility for their maintenance and upkeep.

&nbsp;

**Figure 13-3** *Private Cloud*

![Figure 13-3 Private Cloud](assets/images/Figure%2013-3%20Private%20Cloud.jpeg)

&nbsp;

##  Public Cloud

&nbsp;

A public cloud is provisioned for open utilization by the public at large (see Figure 13-4).  Anyone with a credit card can gain access to a public cloud offering.  A  public cloud exists solely on the premises of the cloud provider.  The key characteristics of a public cloud are as follows:

-   Resources are publicly shared.
-   A public cloud supports multiple customers.
-   Connectivity occurs through the Internet or virtual private connections.
-   Use of a public cloud is billed based on usage.
-   Applications are deployed on the infrastructure hardware and services offered by the cloud provider.  The user is responsible for security and application operations but not responsible for hardware maintenance.

&nbsp;

**Figure 13-4** *Public Cloud*

![Figure 13-4 Public Cloud](assets/images/Figure%2013-4%20Public%20Cloud.jpeg)

&nbsp;

##  Hybrid Cloud

&nbsp;

A hybrid cloud is composed of one or more cloud deployment models (private and public, for example) and is used to extend capabilities or reach and/or to augment capacity during peak demand periods (see Figure 13-5).  The key characteristics of a hybrid cloud are as follows:

-   A hybrid cloud is a combination of public and private models.
-   A hybrid cloud has on-premises and off-premise resources.
-   Orchestration between the parts of a hybrid cloud is the responsibility of the application owner. 
-   Applications are deployed in a distributed fashion, with some services and components residing on premises and others (such as client access) in the cloud provider's environment.

&nbsp;

**Figure 13-5** *Hybrid Cloud*

![Figure 13-5 Hybrid Cloud](assets/images/Figure%2013-5%20Hybrid%20Cloud.jpeg)

&nbsp;

##  Community Cloud

&nbsp;

A community cloud, as shown in Figure 13-6, is unique in that it is provisioned for the sole utilization of a specific community of customers, such as a school district or multiple government agencies.  Basically any group of entities that have a common policy, security, compliance, or mission can join together and implement a community cloud.  The key characteristics are as follows:

-   A community cloud is a collaborative cloud effort that shares infrastructure between several similar organizations with common needs.
-   A community cloud can be owned, managed, and operated by one or more members of the community or a third party.
-   A community cloud may reside on premises or off premises.
-   Applications are deployed in a shared fashion and operated by the community for the use of all community members.  This can be similar to a hybrid model but with a focus on resource sharing.

&nbsp;

**Figure 13-6** *Community Cloud*

![Figure 13-6 Community Cloud](assets/images/Figure%2013-6%20Community%20Cloud.jpeg)

&nbsp;

##  Edge and Fog Computing

&nbsp;

With the increase in IoT applications, devices, and sensors, the various deployment models covered so far are just not up to the task of handling the sheer volume of data being created and needing to be processed.  Self-driving cars, robotics, computer video processing, and many other use cases can produce gigabytes of data in real time.  This sea of data cannot be consumed and processed by a centralized cloud application, given the cost of transporting the data and the latency involved in receiving information back to do anything with it.  Your self-driving car would run into a ditch before a cloud service could detect and respond.

&nbsp;

>   ***`Key Topic`***

&nbsp;

These constraints required engineers to think differently about use cases requiring intelligence at the edge.  A new class of application deployment was created, called fog computing (because fog is basically a cloud on the ground).  The idea behind fog is to leverage the scale and capabilities of cloud models to handle the control and deployment of applications at the edge.  With edge computing, you let local processing of data occur closer to the actual sensors and devices where it can be acted on more quickly.  Think of fog as a framework and structure that enables edge computing.  Figure 13-7 shows how edge and fog work together.

&nbsp;

**Figure 13-7** *Edge and Fog Computing*

![Figure 13-7 Edge and Fog Computing](assets/images/Figure%2013-7%20Edge%20and%20Fog%20Computing.jpeg)

&nbsp;

#   Application Deployment Methods

&nbsp;

What is IT's value to the business if you boil it down to the simplest aspect?  IT is charged with supporting and maintaining applications that the business relies on.  No one builds a network first and then looks for applications to stick on it.  Instead, a network is built to connect applications to employees and customers.  The importance of the application and its evolution have driven many of the advances we have seen in cloud.

&nbsp;

>   ***`Key Topic`***

&nbsp;

#   Bare-Metal Application Deployment

&nbsp;

The traditional application stack, or bare-metal, deployment is fairly well known.  It's how the vast majority of applications have been deployed over the past 40 years.  As Figure 13-8 shows, one server is devoted to the task of running a single application.  This one-to-one relationship means the application has access to all of the resources the server has available to it.  If you need more memory or CPU, however, you have to physically add new memory or a new processor, or you can transfer the application to a different server.

&nbsp;

**Figure 13-8** *Bare-Metal Application Stack*

![Figure 13-8 Bare-Metal Application Stack](assets/images/Figure%2013-8%20Bare-Metal%20Application%20Stack.jpeg)

&nbsp;

While bare-metal application deployment is an effective way to isolate applications and get consistent performance characteristics, it's very inefficient  In fact, many of these traditional server deployment models result in enormous amounts of waste in regard to power and cooling of servers when they are not under load.  It's not uncommon to find a server during non-peak hours using less than 10% of its capacity, which is not very cost-effective.

&nbsp;

Some applications, however, really need a dedicated server.  Big data applications benefit greatly from a dedicated server environment; most Hadoop clusters consist of numerous one-rack-unit servers all running in parallel.  These workloads consume 100% of the resources of the server, making them poor candidates for virtualization.

&nbsp;

#   Virtualized Applications

&nbsp;

Virtualization was created to address the problems of traditional bare-metal server deployments where the server capacity was poorly utilized.  The idea with virtualization is to build one large server and run more than one application on it.  Sounds simple, right?  Many of the techniques mentioned earlier, from the days of the mainframe, were leveraged to create an environment where the underlying server hardware could be virtualized.  The hypervisor was created to handle all of the time slicing and hardware simulation.  This made it possible to run various applications and operating systems at the same time and reap the benefit of better utilization of resources.  Figure 13-9 shows this concept.

&nbsp;

**Figure 13-9** *Virtualized Application Stack*

![Figure 13-9 Virtualized Application Stack](assets/images/Figure%2013-9%20Virtualized%20Application%20Stack.jpeg)

&nbsp;

Virtualizing hardware had other benefits, too.  The ability to make applications portable and not tied to a single server allows for mobility in the data center.  If a server needs to be worked on, you simply move the running virtual machine to another server and never need to take down the application.  You can also create common deployment packages for new virtual machines and applications; this gives administrators the ability to quickly provision a new server in a consistent and secure manner.

&nbsp;

The virtualized application is a key aspect of cloud, but *virtualization* and *cloud* are not synonymous.  A cloud environment could easily be configured to deploy a physical server as well as a virtual machine.  Conversely, just because you have a virtualized infrastructure doesn't mean you have a cloud; the big difference is in the operational model.

&nbsp;

#   Cloud-Native Applications

&nbsp;

Cloud-native, or microservice, applications represent the further intersection and evolution of virtualization and a cloud environment.  As virtualization became popular, application developers started to ask themselves why they needed a heavy operating system to run their applications.  All the patching, drivers, and configuration requirements don't go away just because oyu load a virtual machine.  All that work still needs to be done.  What if applications could be decoupled and written as simpler packages that do not need a hypervisor or full-blown operating system in order to function?  That's exactly what happened.  As figure 13-10 shows, cloud-native applications run on multiple servers in parallel with each other.

&nbsp;

**Figure 13-10** *Cloud-Native Applications*

![Figure 13-10 Cloud-Native Applications](assets/images/Figure%2013-10%20Cloud-Native%20Applications.jpeg)

&nbsp;

If a server goes bad in a cloud-native application environment, no one cares because the application is distributed across many servers in the data center, and the application was written from the beginning to handle failures and redirect work to working nodes.  If you need more capacity, you just plug in a new server, and it is added to the server pool automatically.  The infrastructure deploys the application onto the new server, and capacity has instantly increased.  If load decreases, the application can shut down unused nodes automatically to save money.  LArge-scale cloud applications such as Facebook and Twitter operate in this fashion, which is why they appear to have infinite capacity from a user perspective.

&nbsp;

#   Containerized Applications

&nbsp;

The evolution of applications to leverage microservices architectures was a very important change that provided developers with new ways to build massively scaled applications with tremendous improvements in terms of availability and fault tolerance.  Microservices made available small custom-built components, but they didn't address the need for an efficient infrastructure that could support them and their dynamic nature.  Containers because a very popular way to provide an easier way to get application components deployed in a consistent way.  Imagine being able to have all of the components and dependencies of your application loaded in an interchangeable format that you can simply hand off to operations to deploy.  This was what containers offer.  Google created Kubernetes and made it open source to provide an orchestration and automation framework that can be used to operationalize this new application deployment model.

&nbsp;

The benefits of containers are as follows:

-   Consistency for deployment automation
-   Simplified lightweight image files measured in megabytes (whereas VM files are measured in gigabytes)
-   Providing only what the app needs and nothing else
-   Ability to work the same in production as on a developer's laptop
-   Open community-built best-of-breed containers for faster innovation
-   Ability to deploy applications in seconds

&nbsp;

Deploying applications in a container decouples parts of the application.  Consider a traditional application stack like LAMP (Linux, Apache, MySQL, Perl/Python/PHP).  This was the foundation for many websites over the years.  To deploy a LAMP stack in a virtual environment, you load an operating system and application on top of a hypervisor and then repeat this process for however many virtual machines you need to support the number of users you expect.  Include a load balancer in front of these virtual machines, and you can add capacity as needed.  The problem with this design is that the virtual machines run full operating systems, replicated a number of times.  You also have to maintain the virtual machines the same as you would as if they were physical servers.  Capacity is handled manually, and you can easily run out of resources if your website receives more visitors than you planned.  Figure 13-11 shows a LAMP deployment on virtual machines.

&nbsp;

**Figure 13-11** *LAMP Stack on a Virtual Machine Infrastructure*

![Figure 13-11 LAMP Stack on a Virtual Machine Infrastructure](assets/images/Figure%2013-11%20LAMP%20Stack%20on%20a%20Virtual%20Machine%20Infrastructure.jpeg)

&nbsp;

Now consider what happens if you deploy that same application stack in a container infrastructure.  You decouple the components of the stack and deploy them separately.  So instead of everything being loaded on a single virtual machine, you break off the Apache web server and PHP code from the MySQL database.  By themselves, they are much smaller in size and resource utilization and can be scaled independently of each other.  Instead of having a gigabyte or more being taken up for an operating system and hardware virtualization of memory and other parts of virtualization, the container simply shared the kernel of the underlying operating system of the server it is running on.  The container is treated like an application and is run in an isolated space within the operating system.  Any binaries and libraries needed to run the container are prepackaged, which means you don't have to touch the container host server.  Figure 13-12 shows a containerized LAMP stack.

&nbsp;

**Figure 13-12** *Containerized LAMP Stack*

![Figure 13-12 Containerized LAMP Stack](assets/images/Figure%2013-12%20Containerized%20LAMP%20Stack.jpeg)

&nbsp;

#   Serverless

&nbsp;

Serverless is one of the silliest names in the industry.  Of course, there is a server involved!  However, this type of application deployment mechanism is intended to make it even easier to get an application up and running, and the term *serverless* conveys this idea.  You simply copy nad paste your code into a serverless instance, and the infrastructure runs your code without any further configuration.  This type of deployment is also referred to as function as a service, and it works best for applications that run periodically or that are part of batch processes.  When writing code, you create a function that you call repeatedly at different places in the code to make it more efficient.  Serverless deployment uses the same write once/use many times concept:  You write some code and then call it remotely thorough your application.

&nbsp;

Serverless applications typically execute some type of application logic but do not store data.  Your calling application is expected to handle that part of it.  For example, say you want to create a function that converts images you received to a universal size and shape.  You can then load this function into a serverless offering from AWS, and any time you received a new picture, it is sent to the function and returned in the correct format (see Figure 13-13).

&nbsp;

**Figure 13-13** *Serverless Image Resizing Example*

![Figure 13-13 Serverless Image Resizing Example](assets/images/Figure%2013-13%20Serverless%20Image%20Resizing%20Example.jpeg)

&nbsp;

The whole idea behind serverless and why a customer may want to use it is that it doesn't require dedicated hardware or resources to be set aside for these periodic processes.  The customer pays for the resources used, and then the services are shut down until needed again; this is a better cost model.  The following are some of the advantages of serverless deployment:

-   **Cost**:  Serverless can be significantly cheaper than prepaying for infrastructure that is underutilized.  The pay-as-you-go computing model means you are not charged for time your service is not being used.
-   **Scalability**:  Developers don't need to build in their own autoscaling policies or technologies.  The provider is responsible for adding more capacity on demand.
-   **Easier to use and write code for**:  Small teams of developers can use serverless deployment without needing to involve infrastructure teams or acquire advanced skills.

&nbsp;

The following are some of the disadvantages of serverless deployment:

-   Latency:  Spin-up time from idle for the function can cause significant delays that must be accounted for in application design.
-   Resource constraints:  Some workloads need more resources than the service may typically be allocated for, causing heavy charges, which may make it cheaper to dedicate infrastructure.
-   Monitoring and debugging:  There is limited visibility into the underlying infrastructure, which makes it difficult to troubleshoot performance issues with the application.  You are often limited to the tools provided by the service provider, which are likely to be proprietary.
-   Security and privacy:  Most providers are built on proprietary offerings and use shared resources.  Misconfiguration can result in compromises and data loss, just as with any other cloud service.  There are on-premises options for serverless that can give businesses more control over their data and security posture.
-   Vendor lock-in:  This is a big one.  Each provider has its own tools and frameworks, which makes it very difficult to switch providers if costs go up or if services are not working as planned.  Migration between providers is not trivial.

&nbsp;

#   DevOps

&nbsp;

Agile has dramatically changed the software development landscape by introducing a more efficient and faster way to of delivering software and value ot the business.  Much of the improvement in the development process has been focused on delivery speed.  You can have as much Agile development as you want, but if you can't get the software deployment in a timely manner, you can't take advantage of its capabilities.  Software was traditionally built and tested by developers, and if it worked on their laptops or test systems, it was pitched over the fence to IT operations for deployment.  When things did not go as smoothly as planned, a significant amount of finger-pointing would ensure.  Developers would claim that the software worked fine in testing on their laptops, so the infrastructure must be broken.  The operations team would say that the buggy and poorly written software was stressing their environment and creating all kinds of extra work.  These two groups were in need of some serious marriage counseling.

&nbsp;

Developers and operations teams often have very different expectations and metrics for success.  Developers care about function code, APIs, libraries, services, and Agile sprints.  Success to them means software works on their laptops and in testing, and they finish their latest sprints in time.  Operations, on the other hand, cares about the environment being stable, standards, templates, and not getting awakened at 2 a.m. to go fix a problem.  Success to operations means software and applications are stable, backup and restore processes work, and all systems are operating within defined thresholds.  Developers are all about creating new features and capabilities in their software; change is a constant in their world.  Operations folks are looking to maintain stability in their environment.  The two could not be further apart.

&nbsp;

If you take a calendar view of the two organizations, it becomes very apparent where the challenge is (see Figure 133-14).  How can you possibly deploy new features and capabilities added every 2 weeks as part of an Agile sprint when your operational maintenance window is only open every 6 months?

&nbsp;

**Figure 13-14** *Dev and Ops Calendars*

![Figure 13-14 Dev and Ops Calendars](assets/images/Figure%2013-14%20Dev%20and%20Ops%20Calendars.jpeg)

&nbsp;

Traditional IT service delivery is slow, manual, and often prone to errors (see Figure 13-15).  The infrastructure is a shared resource, and one change can have a ripple effect that could break other unrelated systems.  The fragile nature of the infrastructure makes it very hard to anticipate issues that can arise.  To combat this, many IT organizations create layers upon layers of approval processes.  While this sounds like a rational way to protect the business from downtime, the net effect is to slow new deployments to a crawl.  For these reasons and many others, Devops was created.

&nbsp;

**Figure 13-15** *Traditional Sequential Approach to Operations*

![](assets/images/Figure%2013-15%20Traditional%20Sequential%20Approach%20to%20Operations.jpeg)

&nbsp;

#   What is DevOps?

&nbsp;

In 2009 two employees from Flickr (an image sharing site), John Allspaw and Paul Hammond, presented a talk titled "10+ Deploys per Day: Dev and Ops Cooperation at Flickr" to a bunch of developers at the O'Reilly Velocity conference.  In this talk, Allspaw and Hammond said that he only way to build, test, and deploy software is for development and operations to be integrated together.  The shear audacity of being able to deploy new software so quickly was the carrot that fueled the launch of the DevOps concept.  Over the years since then, Devops has moved from being revered by a small group of zealots and counterculture types to being a very real and quantifiable way to operate the machinery of software creation and release.  The vast majority of companies that do software development are looking for ways to capture the efficiencies of this model to gain a competitive edge and be better able to adapt to change from customer and industry perspectives.

&nbsp;

In a nutshell, DevOps is a culture of sharing in which developers and operations folks are one unit that can rise and fall together.  It is a practical application of Lean and Agile.  The goal of DevOps is to be a real-time business enabler by removing wasted effort and bureaucracy from getting in the way of better addressing the needs of the customer.  DevOps has five guiding principles:

-   **Culture**:  For DevOps to work, organizational culture must change.  This is by far one of the most difficult aspects to embrace, but it is the single most important factor for success.  DevOps requires a culture of sharing.
-   **Automation**:  While DevOps is more than just a set of software tools, automation is the most easily identifiable benefit.  Automation techniques greatly speed up the deployment process, enable defects to be caught and corrected earlier, and eliminate the need for human intervention in repetitive tasks.
-   **Lean**:  Reducing wasted efforts and streamlining the process are the goals of Lean.  It's a management philosophy of continuous improvement and learning.
-   **Measurement**:  Unless you measure your results, you can never improve.  Success with DevOps requires the measurement of performance, process, and people metrics as often as is feasible.
-   **Sharing**:  DevOps requires a culture of feedback and sharing.  Breaking down silos and creating an inclusive shared fate environment is the ultimate goal.

&nbsp;

Figure 13-16 shows the core components of DevOps and how they are interrelated.

&nbsp;

**Figure 13-16** *DevOps*

![Figure 13-16 DevOps](assets/images/Figure%2013-16%20DevOps.jpeg)

&nbsp;

#   Putting DevOps into Practice:  The Three Ways

&nbsp;

When discussing DevOps, it's hard not to mention two very important books on the subject.  The first of these books, *The Phoenix Project*, by Gene Kim, Kevin Behr, and George Spafford, set the stage of understanding the benefits of DevOps practices through a story that builds on the experiences of the authors and contributors and shows how a fictional company moves from being almost out of business to a rising star outpacing its competition.  The interesting thing about the book is that you can find many examples of your everyday life and practices outlines in it.  While it probably won't be made into a blockbuster movie anytime soon, it is a quick read that easily shows the benefits of DevOps practices.  The second important DevOps book is *DevOps Handbook: How to Create World-Class Agility, Reliability, and SEcurity in Technology Organizations*, written by Gene Kim, Jez Humble, Patrick Debois, and John Willis.  This book is a more practical view of the subject and provides insight into the "Three Ways" of DevOps (discussed in the following section), offering a framework for implementation in your own organization.  If you want to know more about DevOps, you should certainly pick up these two books.

&nbsp;

>   ***`Key Topic`***

&nbsp;

##  First Ways:  Systems and Flow

&nbsp;

A highway system at full capacity is basically a parking lot, where no one is moving.  We have all had to spend time staring at brake lights in traffic.  For technologist, an equivalent work scenario featuring overtime and missed family dinner occurs all too commonly.  Many problems occur based of the ripple effect of not knowing how everything flows and not being able to visualize all work moving through the system.  Having a bird's-eye view of how work flows from development to production is essential to figuring out optimal ways to get to the end goal of a working application that provides value.  Many teams use kanban boards to visualize work, whether through an application like Jira or by simply putting sticky notes with the workflow on a whiteboard so that everyone can see what is being done and what needs to be done.  Using a kanban board can help a team be more rational in what it expects to accomplish in a given period of time.  Figure 13-17 shows the first way to DevOps, which is focused on systems and flow.

&nbsp;

**Figure 13-17** *First Way: Systems and Flow*

![Figure 13-17 First Way: Systems and Flow](assets/images/Figure%2013-17%20First%20Way%20Systems%20and%20Flow.jpeg)

To accomplish work goals, oyu have to reduce work units, or batches of work, so that they are more streamlined to prevent workload traffic jams.  In an Agile sprint, it is common to work on a small set of features during a two-week period to reduce how much is being worked on in a given interval of time.  This allows developers time to build the capability without being overwhelmed or pulled in multiple directions.  This also applies to the operations side, as both sides are integral to success.  Developers can't just rain app updates on their operations team without having a solid view of how each update gets deployed and the operations teams have to build a system that is able to handle the speed and agility developers need.  By having both developers and operations work together to understand where constraints are, you can optimize the system and move faster.

&nbsp;

Quality is not a bolt-on at the end of the development and deployment process.  It has to be integrated into the whole system.  Waiting for a problem to be found in Q&A will create compounded issues that can make things much worse.  The earlier you address a challenging situation, the more your overall work effort will be reduced.  This equates to saving money and time.  The whole point is to reduce wasted time on rework.

&nbsp;

You have to continually optimize the system to make it more efficient.  Nothing is ever perfect with DevOps; you are in a constant state of removing inefficiencies.  You must be able to adapt to business needs and your customers' ever-changing requirements.

&nbsp;

The following are they key characteristics of the first way:

-   Make work visible
-   Reduce batch sizes
-   Reduce intervals of work
-   Build in quality by preventing defects from being passed downstream
-   Constantly optimize for business goals

&nbsp;

##  Second Way:  Feedback Loop

&nbsp;

One of the things you will see repeatedly in DeVops is analogies to manufacturing.  Since so much of this management philosophy is derived from Lean and the Toyota Production System, concepts like defect prevention are front and center in the approach.  The idea of a feedback loop is to provide guidance and direction on what is working and what is not working.  If something isn't working, you have to make sure that it doesn't happen again so you don't end up on a hamster wheel of pain.  DeVops requires that you take feedback as the gift that it is and make corrections.  Figure 13-18 shows the second way of DevOps, which his focused on the feedback loop.

&nbsp;

**Figure 13-18** *Second Way: Feedback Loop*

![Figure 13-18 Second Way: Feedback Loop](assets/images/Figure%2013-18%20Second%20Way%20Feedback%20Loop.jpeg)

&nbsp;

The more you sample feedback, the faster you can detect issues and recover from them.  In the Toyota Production System, the manufacturing line has something called an Andon Cord, which can be pulled by anyone at any time to half the production.  This form of feedback is immediate and highly visible.  It also kicks off the process of swarming a problem until it is fixed, where everyone in the area focuses on solving the issue before the line is started.  In DevOps, this type of empowerment means that when problem with software are detected, the whole team pitches in to fix the underlying cause.

&nbsp;

Once a problem has been overcome, it is not just time to have a party; it is time to document and improve the processes that led up to the issue at hand: Learn from your mistakes so you can move on.

&nbsp;

The following are the key characteristics of the second way:

-   Amplify feedback to prevent problems from happening again
-   Enable faster detection and recovery
-   See problems as they occur and swarm them until they are fixed
-   Maximize opportunities to learn and improves

&nbsp;

##  Third Way:  Continuous Experimentation and Learning

&nbsp;

How do you foster innovation?  Create a culture of trust where your people are allowed to try new things and fail.  That doesn't mean that you are just rolling the dice on crackpot ideas; rather, it means having a dynamic and disciplined approach to experimentation and risk taking.  It's very rare that success happens on the first try.  When problems occur, avoid pointing fingers and blaming people; instead, figure out what went wrong and what could be improved to make it better.  Figure 13-19 shows the third way ofDevOps, which focuses on continuous experimentation and learning.

&nbsp;

**Figure 13-19** *Third Way: Continuous Experimentation and Learning*

![Figure 13-19 Third Way: Continuous Experimentation and Learning](assets/images/Figure%2013-19%20Third%20Way%20Continuous%20Experimentation%20and%20Learning.jpeg)

&nbsp;

DevOps talks a lot about continuous improvement and fixing issues to make the system perform better.  It's a noble goal, but when do you find time?  The simple answer is that you need to make time.  In order words, you schedule time to get people focused on improving the system and try new method and technologies.

&nbsp;

Finally, you must build a culture of sharing and learning.  A simple method to accomplish this is to create shared code repositories and get those treasure troves of information off individual laptops and available to the rest of the organization.

&nbsp;

The following are the key characteristics of the third way:

-   Conduct dynamic, disciplined experimentation and risk taking
-   Define time to fix issues and make the system better
-   When things go wrong, don't point fingers
-   Create shared code repositories

&nbsp;

#   DevOps Implementation

&nbsp;

Implementing DevOps technical practices within an organization typically involves three stages.  These stages following a natural progression that leads to a fully automated code-to-development operational model:

&nbsp;

>   ***`Key Topic`***

&nbsp;

-   **Continuous integration**:  This stage involves merging development work with the code base constantly so that automated testing can catch problems early.
-   **Continuous delivery**:  This stage involves a software package delivery mechanism for releasing code to staging for review and inspection.
-   **Continuous deployment**:  This stage relies on continuous integration and continuous delivery to automatically release code into production as soon as it is ready.

&nbsp;

A vast number of technical tools can be used to automate a DevOps environment, from commercial applications to bleeding-edge open-source projects.  You need to be aware of this DevOps tool chain if you are asked to administer a DevOps environment.  XebiaLabs is a company that specializes in DevOps and continuous delivery, and it is a great resource for understanding the various tools in a DevOps pipeline.  The company's DevOps periodic chart provides an interactive view of these tools and provides links and descriptions of the tools and technologies you might encounter (see Figure 13-20).  You can go to https://xebialabs.com/periodic-table-of-devops-tools/ to get access and download your own copy.

**Figure 13-20** *XebiaLabs Periodic Table of DevOps Tools (Source: https://xebialabs.com/periodic-table-of-devops-tools/)*

![Figure 13-20 XebiaLabs Periodic Table of DevOps Tools (Source: https://xebialabs.com/periodic-table-of-devops-tools/)](assets/images/Figure%2013-20%20XebiaLabs%20Periodic%20Table%20of%20DevOps%20Tools.jpeg)

&nbsp;

If you are not interested in the do-it-yourself nature of connecting and configuring open-source tools, you might be better off looking to a vendor that offers a platform as a service or one that will bundle your DevOps pipeline for you and also offer support with maintenance and upgrades.  Regardless of the DevOps platforms or tools you use or whether you build your own or buy them, there are some commonalities for all DevOps pipelines.  It's easiest to understand the workings of a DevOps pipelien by seeing it in action.  Figure 13-21 is a graphical representation of what happens at each step of a sample DevOps pipeline.

&nbsp;

**Figure 13-21** *DevOps Pipeline in Action*

![Figure 13-21 DevOps Pipeline in Action](assets/images/Figure%2013-21%20DevOps%20Pipeline%20in%20Action.jpeg)

&nbsp;

Here is how the pipeline works:

-   **Step 1.** The developer pulls the latest code from the version control system with Git.  This ensures that the developer has the most recent changes and is not working with an old version.
-   **Step 2.** The developer makes changes to the code, adding new features or fixing bugs.  The developer also writes test cases that will be used to automatically test the new code to software functional requirements.  The developer eventually stages the changes in Git for submission.
-   **Step 3.** The developer uses Git to push the code and tests to the version control system (for example, GitHub), synchronizing the local version with the remote code repository stored in the version control system.
-   **Step 4.** The continuous integration server, such as Jenkins, has a login that monitors GitHub for new code submissions.  When Jenkins sees a new commit, it is able to pull the latest version and starts an automated build process using the test cases.
-   **Step 5.** Jenkins kicks off the automated build of a testing environment for the new software build.  It is possible to use Python scripts, Ansible, or other infrastructure automation tools to build the testing environment as close to production as possible.
-   **Step 6.** Jenkins executes various automated testing, including unit testing, integration testing, smoking testing (stress testing), and security testing.  When all the tests are finished, the results are sent back to Jenkins for compilation.
-   **Step 7.** Jenkins sends the test results to the developer for review.  They can be sent via email, but a more modern way of alerting the developer is through a collaboration tool such as Webex Teams.  Jenkins has plug-ins for all major team management tools and allows for easy integration.  If the build fails, the developer can use links to the information on what failed and why, make changes to the code, and restart the process.
-   **Step 8.** If the build process is successful and all the tests pass, Jenkins can deploy the new code to an artifact repository (just a fancy name for the place finished software is stored).  The software is not able to be deployed in production.
-   **Step 9.** Jenkins signals the infrastructure that an updated version of software is ready.  For example, there may be a new container ready to be deployed into a Kubernetes platform.  The updated container replaces the existing containers with the new code fully tested and ready to go.  Now the application is updated with minimal (or no) disruption.

&nbsp;

The nuts and bolts of building a DevOps pipeline are beyond the scope of the 200-901 DevNet Associate DEVASC exam.  There are simply more tools than grains of sand at the beach, and luckily you are not going to be tested on all of them.  For technologists, it's easy to focus on the tools and technology, but honestly that's the easy part of DevOps.  Changing culture and implementing Lean methodologies are where many companies have struggled.  Focus on streamlining your processes and implement technologies that help accelerate your efforts.

&nbsp;

#   Docker

&nbsp;

Some of the best innovations come from reusing older technologies and bringing them forward in a new way.  That's exactly what Solomon Hykes and Sebastien Pahl did back in 2010 when they started a small platform as a service (PaaS) company called dotCloud.  They were looking for a way to make it easier to create applications and deploy them in an automated fashion into their service.  They started an internal project to explore the use of some interesting UNIX technologies that were initially developed in the 1970s to enable process isolation at the kernel level.  What would eventually become Docker started as a project to use these capabilities to grow the PaaS business.  In 2013, the world was introduced to Docker, which represented a new paradigm in application packaging and deployment that took off exponentially.  While dotCloud eventually went away, Docker has grown into the leading container platform.  Luckily for us, it was open source from the very beginning, and the container runtime itself is hosted by the Cloud Native Computing Foundation.  While there are other container runtimes, such as like Rocket and Linux Containers, none of them are as popular or as widely deployed as Docker.

&nbsp;

#   Understanding Docker

&nbsp;

Docker containers use two capabilities in the Linux kernel: namespaces, which provide isolation for running processes, and cgroups, which make it possible to place resource limits on what a process can access.  These features allow you to run a Linux system within another Linux system but without needing to use virtualization technologies to make it work.  From the host operating system's perspective, you are just running another application, but the application thinks it is the only application that is running.  Instead of needing to virtualize hardware, you just share the kernel; you don't need to load a full operating system, drivers, and memory management processes each time you want to run an application.

&nbsp;

##  Namespaces

&nbsp;

Namespaces are essential for providing isolation for containers.  Six namespaces are used for this purpose:

-   **mnt (mountpoints)**:  This namespace is used for mapping access to host operating system storage resources to the container process.
-   **pid (processes)**:  This namespace is used to create a new process ID for an application.
-   **net (networks)**:  This namespace is responsible for network access and mapping communication ports.
-   **ipc (System V IPC)**:  Inter-process communication controls how the application can access shared memory locations between applications within containers.
-   **uts (hostname)**:  This namespace controls host and domain names, allowing unique values per process.
-   **user (UIDs)**:  This namespace is used to map unique user rights to processes.

&nbsp;

Figure 13-22 shows a Linux host using namespaces to isolate three different containers.

&nbsp;

**Figure 13-22** *Linux Namespace Isolation for Containers*

![Figure 13-22 Linux Namespace Isolation for Containers](assets/images/Figure%2013-22%20Linux%20Namespace%20Isolation%20for%20containers.jpeg)

&nbsp;

##  Cgroups

&nbsp;

Cgroups, or control groups, are used to manage the resource consumption of each container process.  You can set how much CPU and RAM are allocated as well as network and storage I/O.  Each parameter can be managed to tweak what the container sees and uses.  These limits are enforced by cgroups through the native Linux scheduler and function to restrict hardware-level resources.  Figure 13-23 shows an example of a cgroup that allocates a maximum of 25% of the various hardware resources to the container host.

&nbsp;

**Figure 13-23** *Control Group in Action*

![Figure 13-23 Control Group in Action](assets/images/Figure%2013-23%20Control%20Group%20in%20Action.jpeg)

&nbsp;

##  Union File System

&nbsp;

The Union File System is a foundational building block for a container.  It is a file system service that was developed for Linux to allow different file systems to be layered on top of each other to create a combination, or union, of the various files to create a single merged representation of the contents.  If you have ever worked with photo editing software, this will probably make sense to you.  Say you want to remove someone or something from a picture (like that ex you never speak of).  You take the base picture and then add layers on top of it, and you add or remove pixels until you have a whole new picture.  If you want to remove layers you created, you simply peel them back to expose the previous image.  Every layer you add on top takes precedence over all the layers below it.  In essence, this is how a union file system works, and it is one of the main reasons such a file system is so efficient at storage.  Each layer includes only what is new and nothing is duplicated from a previous layer.  The layers are read-only, which means they are locked in place.  There is a read/write layer that sits on top of that so that you can use it to interact with the file system, but nothing you do will be maintained unless you save your changes.  If you want ot make your changes permanent, you have to put another layer on top of the union file system.  This is called a copy-on-write operation.  Figure 13-24 shows an example of a container image and its layers.

&nbsp;

**Figure 13-24** *Container Image Layers Using a Union File System*

![Figure 13-24 Container Image Layers Using a Union File System](assets/images/Figure%2013-24%20Container%20Image%20Layers%20Using%20a%20Union%20File%20System.jpeg)

&nbsp;

This read-only aspect of a container is crucial to understand.  You may also hear the term *immutable* used to describe the container file system; it simply means unchanging over time.  In other words, a container doesn't get patched; rather, it gets re-created with new layers added.  In Figure 13-24 you can see an Ubuntu Linux base image layer that has OpenSSL added on top of it via another layer.  Above that is the Apache web server.  Think of these layers as simply running the **apt-get** command and adding a new software package.  What happens if you need to update the OpenSSL layer because of a vulnerability?  You simply rebuild the container with the latest version of software.  There is no patching with a container; you destroy the old one and re-create a new one with updated code.  Later on in this section, you will learn how this works through a Dockerfile, which is how Docker builds container images.

&nbsp;

#  Docker Architecture

&nbsp;

Just like your engine in a car, the Docker Engine is the central component of the Docker architecture.  Docker is a client/server application that installs on top of a Linux, Mac, or Windows operating system and provides all the tools to manage a container environment.  It consists of the Docker daemon and the Docker client.  Docker allows you to package up an application with all of its dependent parts (binaries, libraries, and code) into a standardized package for software development.

&nbsp;

>   ***`Key Topic`***

&nbsp;

The Docker architecture consists of three primary parts: the client, the Docker host, and the docker registry (see Figure 13-25).

&nbsp;

**Figure 13-25** *Docker Architecture*

![Figure 13-25 Docker Architecture](assets/images/Figure%2013-25%20Docker%20Architecture.jpeg)

&nbsp;

The Docker client is a command-line utility (run with the **docker** command) that talks to the REST API of the Docker daemon so that the administrator can issue commands for the operations and management of Docker containers.  The client can communicate to a local or remote docker instance.

&nbsp;

The Docker host is where the Docker daemon resides.  The Docker daemon (**dockerd**) is a service that runs on the host operating system and interfaces with the operating system kernel to allow containers to function.  The client communicates with the Docker daemon through the REST API.  The Docker host houses running containers and also interfaces with the registry to pull container images housed there.  When containers are launched, the daemon looks in its local images, and if the appropriate image is there, it launches the container; if the image is not there, the daemon asks the registry for the image file and then stores it locally.

&nbsp;

The registry is a place to store container images; it is also known as the repository for the container infrastructure.  You can pull images from a registry to run or push new images you create yourself to the registry for storage.  Then other hosts in your container environment can make use of your new container image.  A registry can be private, for the sole use of a single organization, or public, as in the case of Docker Hub.

&nbsp;

#   Using Docker

&nbsp;

The best way to get familiar with Docker is to use it.  Download the appropriate version of Docker for your computer and launch its container.  It is available for both macOS, Windows, and Linux allowing you to install the Docker engine and command-line tools directly on your local machine.

&nbsp;

>   ***`Key Topic`***

&nbsp;

>   **Note**
>   <br>
>   As of version1.13, Docker has changed the command line to include a more logical grouping for people just getting started.  If you are familiar with the old-style command line, fear not, those commands still work.  The additions of the management command syntax just add a hierarchy that will differentiate what you are working on instead of everything being lumped together.  This book uses the new Docker command structure.  If you were to get a question on the exam that uses the old command line, you could simply omit the first command after**docker**.  For example, the command **docker container ps** would be shortened to **docker ps**.

&nbsp;

>   `***Key Topic`***

&nbsp;

The command **docker** runs the client process, which communicates to the Docker daemon.  When you type **docker** and press Enter, you see a long list of available commands.  Example 13-1 displays a shortened version of this list.

&nbsp;

**Example 13-1** *Docker Command List*

```
$ docker

Usage: docker [OPTIONS] COMMAND

A self-sufficient runtime for containers
<cut for brevity>
Management Commands:
  builder     Manage builds
  checkpoint  Manage checkpoints
  config      Manage Docker configs
  container   Manage containers
  context     Manage contexts
  image       Manage images
  network     Manage networks
  node        Manage Swarm nodes
  plugin      Manage plugins
  secret      Manage Docker secrets
  service     Manage services
  stack       Manage Docker stacks
  swarm       Manage Swarm
  system      Manage Docker
  trust       Manage trust on Docker images
  volume      Manage volumes
<cut for brevity>

Run 'docker COMMAND --help' for more information on a command.
```

&nbsp;

In example 13-1, notice the list of management commands.  These represent the new hierarchy into which Docker groups subcommands.  For commands that operate on containers, you can enter **docker container** and then the operation you wish to perform.  At any time, you can type **--help** to get more details on what commands are available, as shown in Example 13-2.

&nbsp;

Example 13-2 Docker Container Help

```
$ docker container --help

Usage: docker container COMMAND

Manage containers

Commands:
  attach      Attach local standard input, output, and error streams to a running
              container
 commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  exec        Run a command in a running container
  export      Export a container's filesystem as a tar archive
  inspect     Display detailed information on one or more containers
  kill        Kill one or more running containers
  logs        Fetch the logs of a container
  ls          List containers
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  prune       Remove all stopped containers
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  run         Run a command in a new container
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  wait        Block until one or more containers stop, then print their exit codes
```

&nbsp;

You can run the command **docker container** *COMMAND* **--help** for more information on a command.

&nbsp;

For the purpose of the 200-901 DevNet Associate DEVASC exam, you are expected to know how to use Docker images in a local developer environment.  This means you are not expected to be an expert on all things Docker, but you need to know how to build, launch, and manager containers on your local machine.  The management commands you will use the most for launching and working with Docker are within the **container** and **image** categories.  If you are working with a container image, you use the command under **image**, and if you want to run or stop a container, you use the commands under **container**.  As long as you know what you want to work on, mapping it to the command is fairly straightforward.

&nbsp;

##  Working with Containers

&nbsp;

When working with containers, the key commands are as follows:

-   **create**:  Create a container from an image.
-   **start**:  Start an existing container.
-   **run**:  Create a new container and start it.
-   **ls**:  List running containers.
-   **inspect**:  Get detailed information regarding the container.
-   **logs**:  Print run logs from the container's execution.
-   **stop**:  Gracefully stop running the container.
-   **kill**:  Stop the main process in the container abruptly.
-   **rm**:  Delete a stopped container.

&nbsp;

There are a few ways to launch a container.  You may have noticed that the **create**, **start**, and **run** commands seem very similar.  The **create** command is used to instantiate a container from an image but does not start the container.  Think of it as preloading a container that you can run later.  The **start** command starts up the loaded container and allows it to execute.  The **run** command, on the other hand, creates and starts the container as a single command.  Example 13-3 provides a quick example of how to launch a sample container with the **run** command.

&nbsp;

**Example 13-3** *Docker Hello World*

```
$ docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
1b930d010525: Pull complete
Digest: sha256:4df8ca8a7e309c256d60d7971ea14c27672fc0d10c5f303856d7bc48f8cc17ff
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```

&nbsp;

In example 13-3, Docker looks for the container image hello-world and can't find it in the local image store.  Since it has never downloaded it before, it defaults to the Docker Hub registry, does a lookup, finds the image, and then downloads (or pulls, in Docker speak) the latest one.  It then starts the container and prints to the console a message saying that the Docker installation is working as expect.  since you have a container that has been executed, you can use the subcommand **ls** to see what is running:

```
$ docker container ls

CONTAINER ID  IMAGE       COMMAND   CREATED            STATUS   PORTS   NAMES
```

&nbsp;

Unfortunately, you don't see any active containers.  That is because the one that was launched ran, printed the message, and then ended.  To see the containers that have been run but are now stopped, you have to add the **-a** flag to **ls**:

```
$ docker container ls -a

CONTAINER ID  IMAGE        COMMAND   CREATED            STATUS   PORTS   NAMES

bac0c2a2cca8  hello-world  "/hello"  43 minutes ago     Exited(0) 43 minutes ago
```

&nbsp;

Now you can see the container ID, the image name, the command that was issued, and its current status, which in this case is exited.  You also see any ports or names that were assigned to the container.

&nbsp;

>   **Note**
>   <br>
>   The older syntax for Docker used the **ps** command instead of **ls** (for example, **docker ps -a**).  You can still type **docker container ps -a** and get exactly the same output as the previous example, even though the **ps** command doesn't appear in the menu.  This is for legacy compatibility.

&nbsp;

Launching a container and interacting with it requires a few more commands.  Example 13-4 runs an Ubuntu container image (**ubuntu**) in interactive mode and connects the local terminal to the containers terminal and launches the bash shell (**bash**).  (The options **-i** and **-t** can be presented separately or together, as **-it**.)

&nbsp;

**Example 13-4** ***docker run outpu**t Command*

```
$ docker container run -it ubuntu bash
Unable to find image 'ubuntu:latest' locally
latest: Pulling from library/ubuntu
7ddbc47eeb70: Pull complete
c1bbdc448b72: Pull complete
8c3b70e39044: Pull complete
45d437916d57: Pull complete
Digest: sha256:6e9f67fa63b0323e9a1e587fd71c561ba48a034504fb804fd26fd8800039835d
Status: Downloaded newer image for ubuntu:latest
root@a583eac3cadb:/#
```

&nbsp;

Since this container hasn't been loaded locally before, Docker pulls the image from Docker Hub, layer by layer.  It executes a Dockerfile hosted on the repository and pulls the very latest version of a base Ubuntu container.  Once it is pulled down, the container is started, and the bash shell is executed.  The terminal now shows that you are connected to the container as root (in the container's namespace).  If you execute the bash **ps** command, you can see that there are only two things: the bash shell and the **ps** command that you just ran.  This highlights the container's isolation from the host OS:

```
root@a583eac3cadb:/# ps
  PID TTY          TIME CMD
    1 pts/0    00:00:00 bash
   11 pts/0    00:00:00 ps
```

&nbsp;

To disconnect from the container, you can type **exit**, but that would stop the container.  ***If you want to leave it running, you can hold down Ctrl and press P and then while still holding Ctrl press Q.  This sequence drops you back to the host OS and leaves the container running.***  From the host OS, you can type **docker container ls** to see that your container is actively running.

```
$ docker container ls

CONTAINER ID  IMAGE   COMMAND CREATED            STATUS           PORTS  NAMES

a583eac3cadb  ubuntu  "bash"  About a minute ago  Up About a minute       musing_bartik
```

&nbsp;

If you want to reconnect to the container, you can just use the container ID or the assigned name to attach to the container and interact with it again:

```
$ docker container attach a583eac3cadb

root@a583eac3cadb:/#
```

&nbsp;

The **inspect** and **logs** commands are two very useful commands for troubleshooting a container.  **inspect** generates a ton of information - pretty much everything to do with the creation of your container, such as network and runtime environment, mappings, and so on (as shown in Example 13-5).  Be warned: Reading the output is like reading a container's DNA.

&nbsp;

**Example 13-5** ***docker container inspect** Command*

```
$ docker container inspect a583eac3cadb
[
    {
        "Id": "a583eac3cadbafca855bec9b57901e1325659f76b37705922db67ebf22fdd925",
        "Created": "2019-11-27T23:35:12.537810374Z",
        "Path": "bash",
        "Args": [],
        "State": {
            "Status": "exited",
            "Running": false,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 0,
            "ExitCode": 127,
            "Error": "",
            "StartedAt": "2019-11-27T23:35:13.185535918Z",
            "FinishedAt": "2019-11-27T23:53:15.898516767Z"
        },
        "Image": "sha256:775349758637aff77bf85e2ff0597e86e3e859183ef0baba8b3e8fc8d3c
        ba51c",
        "ResolvConfPath": "/var/lib/docker/containers/a583eac3cadbafca
855bec9b57901e1325659f76b37705922db67ebf22fdd925/resolv.conf"
<cut for brevity>
```

&nbsp;

The **logs** command details everything the container recorded as output and is super helpful for catching error messages:

```
$ docker container logs a583eac3cadb
root@a583eac3cadb:/# ps
  PID TTY          TIME CMD
    1 pts/0    00:00:00 bash
   11 pts/0    00:00:00 ps
root@a583eac3cadb:/# uname
Linux
```

&nbsp;

Now that you know the basics on launching a container, the next step is to make it accessible to the rest of the world.  To do this, you can start by pulling an nginx web server container and assigning it ports to use with the **-p** flag.  This flag requires that you map the container port to a free port on the Docker host.  If you don't assign one to your local host, Docker will pick a random port above 32700.  In addition, you want to make your nginx container stay running in the background instead of just quitting after you launch it.  By using the **-d** flag, you can detach the container and leave it running in the background.  The last thing you can try is to give the container a name with the **--name** flag.  This way, you can refer to it by name instead of using the random one Docker assigns or the container ID:

```
$ docker container run --name test-nginx -p 80:80 -d  nginx
dfe3a47945d2aa1cdc170ebf0220fe8e4784c9287eb84ab0bab7048307b602b9
```

&nbsp;

After the container is launched, you can see it running by using the **ls** command, get information on what port it is using (port 80), and see what the container is mapped to the local host Ip address (referenced by 0.0.0.0):

```
$ docker container ls

CONTAINER ID IMAGE  COMMAND                  CREATED         STATUS        PORTS      NAMES

dfe3a47945d2 nginx  "nginx -g 'daemon of..." 21 seconds ago  Up 20 seconds 0.0.0.0:   test-nginx
                                                                           80->80/tcp
```

&nbsp;

You can also use **docker container port test-nginx** to list just the port mapping.

&nbsp;

If you open a web browser and point it to http://0.0.0.0, your nginx server should show you a default HTML page (see Figure 13-26).

&nbsp;

**Figure 13-26** *nginx in a Docker Container*

![Figure 13-26 nginx in a Docker Container](assets/images/Figure%2013-26%20nginx%20in%20a%20Docker%20Container.jpeg)

&nbsp;

A web server with default content is not very useful.  Container are meant to be read-only, but there are a couple of ways to add your own content.  There is the **cp** command which allows you to copy files from your local host to the container when it is up and running; however, in order to save those changes, you would have to store another layer on top of your container and then push the new container to your repository.  This would have to be done very time a change is made.  A better way is to mount the content directly to the container when it boots up so that it cna share the content.  This way, if you need to update anything, you just change the files in one directory, and those changes are automatically shared to any container using them.  A quick example of this using the nginx server should make this process clearer.

&nbsp;

We can start with some HTML files that nginx can display.  I have a simple HTML file in a directory called html under Documents on the local laptop running Docker; in macOS the path is ~/Documents/html.  There is a default directory where nginx looks for HTML files to display to users connecting to the service: /usr/share/nginx/html.  You have to supply this mapping with the **-v** or **--volume** flag when you launch your container using the previous example.  Here is what it looks like:

```
$ docker container run --name test-nginx -p 80:80 -d -v ~/Documents/html:/usr/share/nginx/html nginx
d0d5c5ac86a2994ea1037bd9005cc8d6bb3970bf998e5867fe392c2f35d8bc1a
```

&nbsp;

After you enter this long command, when you connect to http://0.0.0.0, you see your own HTML content.  The **-v** flag maps your local directory to the shared directory on the container, and from the container's perspective, those files are in /usr/share/nginx/html.  Figure 13-27 shows the results of this container mapping to the container host's file system.

&nbsp;

**Figure 13-27** *Custom Content Shared from the Local Host*

![Figure 13-27 Custom Content Shared from the Local Host](assets/images/Figure%2013-27%20Custom%20Content%20Shared%20from%20the%20Local%20Host.jpeg)

&nbsp;

To stop running a container, you use the **stop** or **kill** command.  The difference between the two is pretty obvious.  **stop** tries to allow the container time to finish any final work in a graceful way.  Using **kill**, on the other hand, is like pulling the plug.  For most situations, you want to use **stop**:

```
$ docker container stop test-nginx
test-nginx
```

&nbsp;

**stop** and **kill** both halt the container but don't remove it from memory.  If you type **docker container ls -a**, you will still see it listed.  When you want to remove the container from memory, you can use the **rm** command.  You can also use the very handy command **prune** to remove all halted containers from memory.  This is useful on a laptop when you're testing containers and want to free up memory without having to individually remove multiple containers.  Just be careful not to get rid of any container you might actually want to start back up because **prune** will get rid of every inactive container.  Here is an example of p**prune** in action:

```
$ docker container rm test-nginx
test-nginx

$ docker container prune
WARNING! This will remove all stopped containers.
Are you sure you want to continue? [y/N] y
Deleted Containers:
a583eac3cadbafca855bec9b57901e1325659f76b37705922db67ebf22fdd925
```

&nbsp;

##  Dockerfiles

&nbsp;

A Dockerfile is a script that is used to create a container image to your specifications.  It is an enormous time saver and providers a ready-made system for replicating and automating container deployments.  Once oyu have built a Dockerfile, you can create an infinite number of the same images without having to manually edit or install software.  A Dockerfile is simply a text file with a structured set of commands that Docker executes while building the image.  Some of the most common commands are as follows:

>   ***`Key topic`***

-   FROM:  Selects the base image used to start the build process or can be set to **scratch** to build a totally new image.
-   MAINTAINER:  Lets you select a name and email address for the image creator.
-   RUN:  Creates image layers and executes commands within a container.
-   CMD:  Executes a single command within a container.  Only one can exist in a Dockerfile.
-   WORKDIR:  Sets the path where the command defined with **CMD** is to be executed.
-   ENTRYPOINT:  Executes a default application every time a container is created with the image.
-   ADD:  Copies the file from the local host or remotely via a URL into the container's file system.
-   ENV:  Sets environment variables within the container.
-   EXPOSE:  Associates a specific port for networking binding.
-   USER:  Sets the UID (or username) of the user that is to run the container.
-   VOLUME:  Sets up a sharable directory that can be mapped to a local host directory.
-   LABEL:  Provides a label to identify the created Docker image.

&nbsp;

Creating a Dockerfile starts with creating a text file.  The file must be named Dockerfile, and you place it in the working directory where you want to create an image.  Once you have opened your favorite editor, the syntax is straightforward.  Docker reads the file and operates on it line by line, so the order in which you build your Dockerfile should follow the steps you would perform manually to load your software and configure it.  First, you need to select your foundation.  This can be any container, but in this instance, you can use Ubuntu as the foundation.  If you don't select a specific version, Docker defaults to the latest version.  You should also provide details on who created the image with a full name and email address.  Here is an example:

```
FROM ubuntu:16.04
MAINTAINER Cisco Champion (user@domain.com)
```

&nbsp;

Next, you need to specify the software you want to load and what components should be added.  Just as when loading software on a Linux server, you first need to run **apt-get update**.  For this container, you install nginx and any dependencies:

```
RUN apt-get update && apt-get upgrade -y
RUN apt-get install nginx -y
```

&nbsp;

Now you need to tell Docker what port to expose for networking.  In this case, you would expose ports 80 and 443:

```
EXPOSE 80 443
```

&nbsp;

Next, you create a sharepoint for HTML files in nginx so that you cna give it access to your web files:

```
VOLUME /usr/share/nginx/html
```

&nbsp;

Finally, set the container to run nginx on launch:

```
CMD ["nginx", "-g", "daemon off;"]
```

&nbsp;

```
FROM ubuntu:latest
MAINTAINER Cisco Champion (user@domain.com)
RUN apt-get update && apt-get upgrade -y
RUN install nginx -y
EXPOSE 80 443
VOLUME /usr/share/nginx/html
CMD ["nginx", "-g", "daemon off;"]
```

&nbsp;

Now that you have a Dockerfile, it's time to build an image.

&nbsp;

##  Docker Image

&nbsp;

When working with Docker image,s you primarily use the following commands:

&nbsp;

>   ***`Key Topic`***

&nbsp;

-   **build**:  Builds an image from a Dockerfile.
-   **push**:  Pushes a local image to a remote registry for storage and sharing.
-   **ls**:  Lists images stored locally.
-   **history**:  shows the creation and build process of an image.
-   **inspect**:  Provides detailed information on all aspects of an image, including layer detail.
-   **rm**:  Deletes an image from local storage.

&nbsp;

In the previous example, you built a Dockerfile using the latest Ubuntu base and then updated and upgraded the Ubuntu base so that its packages are current.  You then installed nginx, shared a mount point, and exposed ports to access the new web server.  The next step is to kick off the build process with Docker.  While in the directory where you created your Dockerfile, execute the build process shown in Example 13-6.

&nbsp;

**Example 13-6** *Building a Container from a Dockerfile*

```
$ docker build -t myimage:latest .
Sending build context to Docker daemon  2.048kB
Step 1/8 : FROM ubuntu:latest
 ---> 775349758637
Step 2/8 : MAINTAINER Cisco Champion (user@domain.com)
 ---> Using cache
 ---> f83e0f07db18
Step 3/8 : RUN apt-get update
 ---> Using cache
 ---> 646cc0e9f256
Step 4/8 : RUN apt-get upgrade -y
 ---> Using cache
 ---> c2701f555b0f
Step 5/8 : RUN apt-get install nginx -y
 ---> Using cache
 ---> 4abf50fd4a02
Step 6/8 : EXPOSE 80 443
 ---> Using cache
 ---> a9a1533064b2
Step 7/8 : VOLUME /usr/share/nginx/html
 ---> Using cache
 ---> 2ecd13c5af2b
Step 8/8 : CMD ["nginx", "-g", "daemon off;"]
 ---> Running in e03bd2387319
Removing intermediate container e03bd2387319
 ---> 04ae8c714993
Successfully built 04ae8c714993
Successfully tagged myimage:latest
```

&nbsp;

The build is successful.  you can see that with the **-t** flag, you can set a name that can be used to call the image more easily.  The **.** at the end of the command tells Docker to look for the Dockerfile in the local directory.  You could also use the **-f** flag with a path to the location of the Dockerfile file, if it is not in your current directory.  Docker also accepts a URL to the Dockerfile, such as at GitHub.  As shown in this example, the name Dockerfile must be capitalized and one word.

&nbsp;

When an image is built, you can use **docker image ls** to see it in local storage:

```
$ docker image ls
REPOSITORY     TAG      IMAGE ID      CREATED           SIZE
myimage       latest     04ae8c714993  48 minutes ago   154MB
```

&nbsp;

You can use a number of commands to get information from your images.  The first is **inspect**.  Entering **docker image inspect myimage**, as shown in Example 13-7, gets all the details about the image, including its layer structure.

&nbsp;

**Example 13-7** ***docker image inspect** Command*

```
$ docker image inspect myimage
[
    {
        "Id": "sha256:04ae8c7149937b2ce8b8963d6c34810d8dc53607c9a97064e1f3c85cdc3
        abb46",
        "RepoTags": [
            "myimage:latest"
        ],
        "RepoDigests": [],
        "Parent": "sha256:2ecd13c5af2b41349b58f2397cbbbc70f5c1c604262113bae443f1f6fc
        3758cc",
        "Comment": "",
        "Created": "2019-11-28T05:53:37.794817007Z",
        "Container": "e03bd238731932ca2cab6c8b7fa1346105b839ce2a8604c0c7d
        34352b907a4af",
        "ContainerConfig": {
            "Hostname": "e03bd2387319",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "ExposedPorts": {
                "443/tcp": {},
                "80/tcp": {}
            },
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
<Cut for brevity>
```

&nbsp;

The **image history** command shows you the creation nof the image and all the steps that were taken to build the image, as shown in Example 13-8.  This can be very useful in troubleshooting an image build.

&nbsp;

**Example 13-8** ***docker image history** Command*

```
$ docker image history myimage
IMAGE            CREATED          CREATED BY                                  SIZE   COMMENT
04ae8c714993  56 minutes ago   /bin/sh -c #(nop)  CMD ["nginx" "-g" "daemon…  0B
2ecd13c5af2b  57 minutes ago   /bin/sh -c #(nop)  VOLUME [/usr/share/nginx/…  0B
a9a1533064b2  57 minutes ago   /bin/sh -c #(nop)  EXPOSE 443 80               0B
4abf50fd4a02  57 minutes ago   /bin/sh -c apt-get install nginx -y            60.2MB
c2701f555b0f  58 minutes ago   /bin/sh -c apt-get upgrade -y                  1.55MB
646cc0e9f256  58 minutes ago   /bin/sh -c apt-get update                      27.6MB
f83e0f07db18  58 minutes ago   /bin/sh -c #(nop)  MAINTAINER Cisco Champion…  0B
775349758637     3 weeks ago   /bin/sh -c #(nop)  CMD ["/bin/bash"]           0B
<missing>        3 weeks ago   /bin/sh -c mkdir -p /run/systemd && echo 'do…  7B
<missing>        3 weeks ago   /bin/sh -c set -xe   && echo '#!/bin/sh' > /…  745B
<missing>        3 weeks ago   /bin/sh -c [ -z "$(apt-get indextargets)" ]    987kB
<missing>        3 weeks ago   /bin/sh -c #(nop) ADD file:a48a5dc1b9dbfc632…  63.2MB
```

&nbsp;

You probably noticed the missing image IDs at the bottom of the history.  The build process uses something called *intermediate layers* to execute commands.  These layers are like temporary storage that gets rolled up into the next layer when each stage is finished, and then the intermediate layer is deleted.

&nbsp;

When the image is built and ready to go, you can run it by using the following command:

```
$ docker container run -p 80:80 -p 443:443 -d myimage

bf0889f6b27b034427211f105e86cc1bfeae8c3b5ab279ccaf08c114e6794d94

$ docker ps

CONTAINER ID  IMAGE    COMMAND         CREATED       STATUS       PORTS               NAMES

bf0889f6b27b  myimage "nginx -g        7 seconds ago Up 6 seconds 0.0.0.0:80->80/tcp,  elastic_maxwell
                      'daemon of..."                              0.0.0.0:443->443/tc
```

&nbsp;

You can use the **docker image rm** command to remove an image from storage.  This command needs the container ID or a name to select the appropriate container.

&nbsp;

#   Docker Hub

&nbsp;

Docker Hub is a free service that Docker offers to the community to house and share prebuilt container images.  It is the world's largest repository for containers, with more than 100,000 prebuilt container applications.  Chances are that if you are looking to build a container, someone has already put together one that would work for you.  Many software vendors also publish official images that have been validated by the vendor and Docker; when you use such an image, you can be confident that the container you are using has been tested and is malware free.  While anyone can sign up for a free account, Docker makes money by offering, for a fee, private container repositories suitable for individuals and businesses.  Docker Hub is a cloud-only service, so if you want to run a private container registry in your data center, you have to deploy Docker Enterprise software or another container registry system on premises.

&nbsp;

>   ***`Key Topic`***

&nbsp;

Docker Hub has a slick interface that makes it easy to set up a repository and secure it.  It also integrates with GitHub and Bitbucket to enable automated container creation from source code stored in your version control system.  It's a great way to start building a CI/CD pipeline as it is free to get started.  If you set up a free account, you can take advantage of Docker Hub's capabilities immediately.  Figure 13-28 shows Docker Hub signup page.

&nbsp;

**Figure 13-28** *Signing Up for Docker Hub*

![Figure 13-28 Signing Up for Docker Hub](assets/images/Figure%2013-28%20Signing%20Up%20for%20Docker%20Hub.jpeg)

&nbsp;

Once you have an account, you can search through the many containers available and can filter on operating system, category, and whether or not the image is an official Docker certified image, verified by the publisher, or an official image published by Docker itself.  Figure 13-29 shows the image and search function.

&nbsp;

**Figure 13-29** *Docker Hub Image Search*

![Figure 13-29 Docker Hub Image Search](assets/images/Figure%2013-29%20Docker%20Hub%20Image%20Search.jpeg)

&nbsp;

Docker ships a GUI application called Kitematic for interacting with containers on your local host as well as Docker Hub.  This free app can download and launch containers with a simple point and click.  It's great for people who are struggling with all of the command-line options that the typical Docker client requires.  But be warned: With Kitematic you don't have as much direct control as you do with the Docker client.  Download it and give it a try.  Figure 13-30 shows Kitematic in action.

&nbsp;

**Figure 13-30** *Kitematic*

![Figure 13-30 Kitematic](assets/images/Figure%2013-30%20Kitematic.jpeg)

&nbsp;

After you build a container, as you did in the previous example, you need to push it to a repository.  since you can use Docker Hub for free, you can set up a private repository to store this container.  If you wanted to share with the world the container you created, you could do so by simply making the repository public.  A private repository is always a good bet for code that is just for your organization.  Figure 13-31 shows how to set up a private repo in Docker Hub named newrepo that you can push your new container to.

&nbsp;

**Figure 13-31** *Docker Hub Repository Setup*

![Figure 13-31 Docker Hub Repository Setup](assets/images/Figure%2013-31%20Docker%20Hub%20Repository%20Setup.jpeg)

&nbsp;

Once your repository is set up, you need to tag your image to be pushed to Docker Hub.  Use **docker image ls** to list your images and take note of the image ID:

```
$ docker image ls
REPOSITORY    TAG       IMAGE ID       CREATED             SIZE
myimage       latest    04ae8c714993   About an hour ago   154MB
```

&nbsp;

Next, you need to issue the **docker image tag** command with the image ID of your image and assign it to *username*/newrepo:firsttry.  newrepo simply identifies the repo you want to place the image in, and the tag after the : allows you to differentiate this particular image from any other in the repository (in this instance, it is named firsttry):

`$ docker image tag 04ae8c714993 chrijack/newrepo:firsttry`

&nbsp;

Now you are ready to issue the **push** command,as shown in Example 13-9, and you see Docker start to push the layers of your container image to your repository.

&nbsp;

**Example 13-9** ***docker image push** Command*

```
$ docker image push chrijack/newrepo:firsttry
The push refers to repository [docker.io/chrijack/newrepo]
3e92d80e0ac4: Pushed
a87bf84680fc: Pushed
02d0765ebf97: Pushed
e0b3afb09dc3: Pushed
6c01b5a53aac: Pushed
2c6ac8e5063e: Pushed
cc967c529ced: Pushed
firsttry: digest: sha256:01cf95854003cd1312fb09286d41bc6bfd9fe3fb82f63e66e5060c7fd5a
6230a size: 1786
```

&nbsp;

You can nwo check back with Docker Hub and see that the image is now hosted in your private repository (see Figure 13-32).

&nbsp;

**Figure 13-32** *Docker Hub Pushed Image*

![Figure 13-32 Docker Hub Pushed Image](assets/images/Figure%2013-32%20Docker%20Hub%20Pushed%20Image.jpeg)

&nbsp;

After this, any time you want to retrievve the image, you can type **docker image pull** *username*/**newrepo:firsttry**, and Docker will load it in your local image storage.

&nbsp;

There is quite a bit more that you can do with Docker, but this section should get you started and focused on what you need to know for the 200-901 DevNet Associate DEVASC exam.  Make sure that you review the Docker documentation and try these examples on your own computer.  Nothing beats practical experience.

