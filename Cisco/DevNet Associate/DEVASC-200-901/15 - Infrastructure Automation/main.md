#   Controller Versus Device-Level Management

&nbsp;

Historically, network devices were managed through command-line interfaces (CLIs) by using protocols such as Telnet and Secure Shell (SSH).  The network administrator would connect to the CLI of a network device using a software client that implements these protocols and performs the configuration changes needed for the device to function as expected.  On a small- to medium-sized network, this approach might still work, but as networks keep growing bigger and more and more devices become connected, managing networks in a device-by-device manner becomes time-consuming and prone to errors.  Combine this with the needs for automation, network programmability, and reductions in operational costs, and you can see that a new way of managing networks is needed.

&nbsp;

Network controllers are a possible solution to the challenges of managing networks in a device-by-device manner.  A network controller is a centralized software platform dedicated to managing the configuration and operational data of network devices.  Controllers take over the management of network devices, meaning that all interactions with the devices have to go through the controller.  They provide an abstraction layer between the administrators of the network and network devices.  Network controllers usually expose a northbound REST API interface for management and integration with third-party systems and one or several southbound interfaces through which they connect and manage the network devices.  Typical southbound interfaces are CLI-based interfaces that use Telnet and SSH, OpenFlow, SNMP, NETCONF, RESTCONF, and so on.  In most situations, the network controller manages different network devices running different network operating systems with different version and different features; by abstracting the underlying network capabilities, the controller exposes only a subset of the network functions.  This minimal loss of network functionality is an assumed risk when choosing to go the network controller route for managing a network

&nbsp;

>   ***`Key Topic`***

&nbsp;

On one side is the controller-based management of networks supporting a subset of network functions, and on the other side is direct access to the devices with full access to the network features.  Network administrators have to choose between these two options, keeping in mind the requirements of the network and which option works best for each situation.

&nbsp;

There are several other consideration to keep in mind when integrating controllers into a network.  Support for atomic network configuration is one of them.  Atomicity in the case of network configuration means that either the intended configuration has been applied to all network elements without error or, to deal with potential errors, there is a rollback mechanism in place to ensure that the partial configuration is removed and the devices are brought back to the initial state before there is any attempt to change the configuration.  Atomicity is very important to ensure a holistic and uniform view of the network and to make sure that partial and incomplete configurations do not negatively affect the functionality of the network.

&nbsp;

Another consideration with network controllers involves auditing and managing the configuration drift of the network elements.  Configuration drift happens when the configuration of a network device has changed from its intended state, which means the configuration of the device in the network controller is different from the configuration of the device itself.  This situation can easily lead to inconsistencies and unexpected network behavior.  A good controller has built-in mechanisms to address configuration drift; in some instances these mechanisms go as far as limiting or even blocking device configuration changes.

&nbsp;

The main advantage provided by network controllers is that the abstraction and central administration of individual network devices eliminates the need for device-by-device configuration, management, and monitoring, as shown in Figure 15-1.

&nbsp;

**Figure 15-1** *Network Managed Through a Network Controller*

![Figure 15-1 Network Managed Through a Network Controller](assets/images/Figure%2015-1%20Network%20Managed%20Through%20a%20Network%20Controller.jpeg)

&nbsp;

Direct device configuration allows access to the full feature set of a device, but it can be time-consuming and prone to errors - especially in large networks.  The scale of a network is certainly a limiting factor when performing configuration and management tasks on a device-by-device basis.  As you've seen in Chapter 12, "Model-Driven Programmability," historically, there has been an evolution from custom CLIs to standard data models and network configuration protocols such as NETCONF and RESTCONF.  Having custom-built protocols for network configuration as well as standard data models is definitely helping with the network automation efforts and the scale limitations.  Configuration changes made on a single device can be replicated across an entire network.  Device-by-device configuration is illustrated in Figure 15-2.

&nbsp;

>   ***`Key Topic`***

&nbsp;

**Figure 15-2** *Network Managed on a Device-by-Device Basis*

![Figure 15-2 Network Managed on a Device-by-Device Basis](assets/images/Figure%2015-2%20Network%20Managed%20on%20a%20Device-by-Device%20Basis.jpeg)

&nbsp;

Using a controller for network management and device-by-device configuration are not mutually exclusive.  A controller can be used to globally configure devices, while direct connection to devices can be helpful for monitoring and ensuring that the changes made by the controller do not create undesired behavior.

&nbsp;

Chapter 8, "Cisco Enterprise Network Management Platforms and APIs," provides an example of a network controller with Cisco DNA Center.  Cisco DNA Center can be used to completely configure, manage, and monitor networks.  It can also be used to deploy SD-Access fabrics.  It is possible to deploy SD-Access by using automation tools and connecting to each device using NETCONF, the CLI, or even SNMP.  This gives the network administrator more granular control but at the same time requires more work and time to define configuration parameters and data models and to ensure that the correct configuration gets applied to all the devices in an unified manner.  Cisco DNA Center performs all these tasks automatically, and automation scripts can be used to collect operational data and ensure that the network performs within optimal parameters.

&nbsp;

#   Infrastructure as Code

&nbsp;

Inspired by software development practices, infrastructure as code is a new approach to infrastructure automation that focuses on consistent, repeatable steps for provisioning, configuring, and managing infrastructure.  For a long time, infrastructure has been provisioned and configured in a manual fashion.  Deploying a new application on a network used to take anywhere from weeks to months to even years in some situations.  During that time, the IT team would try to size the hardware requirements for the new application, go through the approval process to purchase the new hardware, order the hardware, wait for it to be delivered, rack it up, and start the provisioning and configuration steps.  The provisioning and configuration of the new hardware was in most cases a manual process: installing the operating system one step at a time following guided instructions and then finally installing and configuring the new application.  At best, technologies like PXE booting and installation scripts would be used to try to automate the arduous process of provisioning new hardware and installing new applications.  This resulted in one-of-a-kind, or "snowflake," environments in which each application ran on different hardware, with different options and features enabled; supporting and maintaining such environments was incredibly challenging.  A new paradigm for deploying and managing infrastructure was needed.

&nbsp;

The IT infrastructure of the past had a number of limitations, including high deployment and maintenance costs, long waiting times for new infrastructure to be ready for production (slowing down new application deployments and hampering innovation and fast prototyping), and difficulty in troubleshooting since each environment was slightly different.  Several technologies have evolved to address these limitations.  The one that has had the biggest impact is public cloud computing.  Besides making infrastructure available almost instantaneously and reducing the costs associated with purchasing hardware, cloud computing ahs also changed the way IT infrastructure is being provisioned, configured, and consumed.  With the advent of APIs, public cloud infrastructure can more easily be automated, and cookie-cutter templates can be created for easy and fast deployment of new infrastructure.

&nbsp;

Infrastructure as code is all about the representation of infrastructure through machine-readable files that can be reproduced for an unlimited amount of time.  It is a common practice to store these files in a version control system like Git and then use them to instantiate new infrastructure - whether servers, virtual machines, or network devices.  In this way, infrastructure can be treated as source code, with versioning, history, and easy rollback to previous versions, if needed.  Being able to spin up new infrastructure in a repeatable, consistent fashion becomes extremely useful, for example, in cases in which there is a spike in traffic and in the number of application requests for a certain period of time.  In such cases, new servers, load balancers, firewalls, switches, and so on can be dynamically provisioned within seconds to address the additional load.  Once the traffic subsides and the need for higher capacity subsides, the infrastructure can be scaled down by dynamically decommissioning servers, load balancers, and so on to save on costs.  This *elasticity* of the infrastructure is another of the benefits of defining all infrastructure as code.

&nbsp;

>   ***`Key Topic`***

&nbsp;

By defining infrastructure through code, the infrastructure becomes transparent in the sense that it is enough to read the code in the document to know all the characteristics and features that will be instantiated when it gets provisioned.  Other people can review the code, make improvements, have the changed tracked through version control, and make sure the code is in compliance with the security requirements of the company.

&nbsp;

While change was frowned upon in the infrastructure of the past, and a limited number of strict change windows were provided through the year, with infrastructure as code, change is welcomed and even desired.  With infrastructure as code, change is a catalyst to improve the reliability and the performance of the infrastructure as a whole.  Just as source code goes through multiple version and becomes better with each new release, infrastructure becomes more resilient and reliable with each new version.

&nbsp;

By using infrastructure as code, it is possible to have identical environments for testing, integration, and production.  This leads to significantly fewer troubleshooting steps needed to repair and maintain the infrastructure and the applications running on top of it.

&nbsp;

There are usually two types of approaches to infrastructure as code:

&nbsp;

>   ***`Key Topic`***

&nbsp;

-   Declarative:  With the declarative approach, the desired state of the system is defined and then the system executes all the steps that need to happen in order to attain the desired state.
-   Imperative:  The imperative approach defines a set of commands that have to be executed in a certain order for the system to achieve the desired state.

&nbsp;

A popular infrastructure as code solution is Terraform from HashiCorp.  Infrastructure as code integrates very well in the continuous integration/continuous delivery pipelines discussed next.

&nbsp;

#   Continuous Integration/Continuous Delivery Pipelines

&nbsp;

Software is quickly becoming pervasive in all aspects of our lives.  From smartphones to smart cars and smart homes, we interact with software hundreds or even thousands of times each day.  Under the DevOps umbrella, there have been several efforts to improve software development processes in order to increase the speed, reliability, and accuracy of software development.  ***Continuous integration/continuous delivery (CI/CD)*** pipelines address all these requirements and more.  All the software development processes - from writing code to building, testing, and deploying - were manually performed for years, but CI/CD pipelines can be used to automate these steps.  Based on specific requirements for each company, different tools and different solutions are used to implement these pipelines.  Some companies implement only continuous integration solutions, and others take advantage of the whole CI/CD pipeline, automating their entire software development process.

&nbsp;

CI/CD is a series of automated steps that code goes through from the IDE of the individual developer, through building, testing, and finally deployment to staging and production environments.  Although usually used to together, continuous integration and continuous delivery are two separate concepts that can be addressed separately.  

&nbsp;

>   ***`Key Topic`***

&nbsp;

Continuous integration is a software development practice in which developers commit their code to a central repository that is part of a version control system on an hourly, daily, or weekly basis or at some other frequency that is agreed upon within the team.  As developers commit their code to the central repository, it is important to verify that the code integrates well with the full code base.

&nbsp;

As new code is written, it is critically important to run code base tests against the new changes in the code base in a fast, automated fashion.  Continuous integration tools accomplish exactly this task.  As the code gets committed to a central repository - in most cases, to a Git-style version control system - a webhook gets triggered that starts the whole automated testing phase of the pipeline.  Common triggers at this stage include automatic integrations with tools such as Cisco Webex Teams for immediate notifications on the status of the tests.  In the event that a test fails, the developer is notified and can correct the issues that caused the test to fail very early in the development process.  If all the tests pass, teh code moves on to the next state of the pipeline.

&nbsp;

A key component of any CI pipeline is the build server.  The role of the build server is to react to developers committing their code to the central repository and to start the initial tests on the new code features.  Most version control systems support webhook mechanisms to automatically notify the build server when pull requests are opened and code is committed.  Popular build servers include Jenkins, Travis CI, and Drone CI.  Table 15-2 compares development environments that have implemented CI pipelines and the ones that have not.

&nbsp;

>   ***`Key Topic`***

&nbsp;

**Table 15-2** Development Environments With and Without CI

| Development Without CI | Development With CI |
| -- | -- |
| Increased number of bugs | Fewer bugs |
| Insufficient testing | Automated builds, tests, documentations, and reports |
| Few releases per year | Multiple releases per day |
| Lack of integration testing | Dedicated build and test servers |
| Project delays | Frequent commits |
| Fewer features | More features |
| Instability | Stability |

&nbsp;

Continuous delivery adds on top of continuous integration all the remaining steps needed to automate the entire software release cycle, from building to testing to deployment (see Figure 15-3).

&nbsp;

**Figure 15-3** *Complete CI/CD Pipeline*

![Figure 15-3 Complete CI/CD Pipeline](assets/images/Figure%2015-3%20Complete%20CI%20CD%20Pipeline.jpeg)

&nbsp;

In the building phase, the code is compiled for languages such as Java, C/C++, or Go; for code written in interpreted languages such as Ruby or Python, the compilation step can be ignored.  Regardless of the language the code is written in, in most cases, the output of the build phase is a Docker image that containers all the code, all required dependencies, and startup scripts to ensure that the application runs consistently, whatever the destination environment might be.

&nbsp;

During the testing phase, automated tests are run to ensure correct behavior of the product.  In an effort to catch software bugs as soon as possible, tests are developed at this stage to make sure the new code follows the expected requirements.  Several types of tests are run at this stage, from unit and smoke tests that perform quick sanity checks, to integration, code coverage, code standards, and end-to-end tests that try to mimic the way users interact with the software as closely as possible.  Developers following the results of the tests, and if any of the tests fail, the developers can immediately address the problems and fix the code and restart the pipeline until all tests pass.

&nbsp;

The next phase in the IC/CD pipeline is the deployment phase.  By this stage, the software has been packaged and tested and is ready to be deployed for consumption.  Before containers, in most cases, this meant installing the new binaries in new server, either physical or virtual, and reconfiguring load balancers to point to the new servers and monitor the environment to ensure that the new version worked as expected.  With the advent of Docker and similar container technologies, the deployment phase has become much easier to implement.  Containers can be destroyed and restarted with the new version of code within seconds.  Container orchestrator solutions, such as Kubernetes, DC/OS, and Docker Datacenter, can be used to simplify this process even further.  By using the container orchestrator APIs, a call can be made to roll out the new Docker containers with the new features - and there is zero downtime.  Several strategies can be used to ensure zero downtime while deploying containers; changing only one container at a time from a pool of many instances is one of them.

&nbsp;

In most situations, there are several environments available at the deployment stage of the pipeline, but at least two are present in all cases: staging and production.  In the staging environment, final preparations and manual testing by the production team takes place to ensure that everything functions as expect  Approved changes in the staging environment automatically get deployed into the production environment.

&nbsp;

The CI/CD pipelines described so far can be adopted for network management and configuration.  Taking advantage of infrastructure as code, network configurations can be stored in version control systems, and build servers can be used to integrate with solutions such as Cisco CML/VIRL (virtual Internet Routing Lab) to dynamically instantiate virtual networks, test the configuration changes in the virtual network, and if the tests pass, use automation solutions such as Ansible to perform the desired changes in the production network.  A working network management CI/CD pipeline could including the following:

&nbsp;

>   ***`Key Topic`***

&nbsp;

-   Github.com as a cloud-based version control system or Gogs as a self-hosted Git option could be used to storage the configurations.
-   Travis CI as a cloud-based build server or Done as a self-hosted build server could be used to orchestrates the whole CI/CD pipeline.
-   Cisco CM/VIRL could be used to create a test network and verify the impact of the configuration changes in the network.
-   Ansible could be used to automate the configuration of all the elements in the network.

&nbsp;

CI/CD pipelines are used by more and more companies to speed up and increase the reliability and accuracy of their software development processes.  Companies that have adopted CI/CD pipelines as part of their development processes release hundreds of software features every week.

&nbsp;

#   Automation Tools

&nbsp;

It is common practice for network administrators to perform configuration, monitoring, and maintenance activities every day on all the devices in a network or at least a subset of them.  These changes were traditionally deployed manually: The network administrator would connect to each network device individually and perform the changes.  The changes could be anything, from adding a new access VLAN throughout the network, to updating entries in an access control list, to changing SNMP communities' names.  Where there is a manual task that is being performed, there is an opportunity to improve the process by automating that task.  Open-source tools such as Ansible, Puppet, and Chef can dramatically reduce the number of manual interactions with a network.  These tools enable automation at scale for application deployment, infrastructure management, and network configurations.  The following sections discuss each of them in turn.

&nbsp;

##  Ansible

&nbsp;

Ansible is a configuration management and orchestration tool that can be used for a variety of purposes.  It can be used to configure and monitor servers and network devices, install software, and perform more advanced tasks such as continuous deployments and zero-downtime upgrades.  It was created in 2012 and acquired by RedHat in 2015.  Ansible is appropriate for both small and large environments and can be used for managing a handful of servers and network devices or for managing thousands of devices.  It is agentless, meaning there is no software or service that needs to be installed on the managed devices.  Ansible connects to managed devices just as a regular system or network administrator would connect for management purposes - in most cases, over SSH, but NETCONF and REST API interfaces are also supported.  Ansible is open source and was developed using Python.  There is also a commercial offering available, called Ansible Tower, which includes a web user interface, a northbound REST API, role-based access control, statistics, and much more.

&nbsp;

Several Ansible concepts need to be discussed before we go further:

&nbsp;

>   ***`Key Topic`***

&nbsp;

-   **Control node**:  The control node is any machine that has Ansible installed.  All flavors of Linux and BSD operating systems are supported for the control node.  Any computer, laptop, virtual machine, or server with Python installed can be an Ansible control node.  The exception to this rule is that Microsoft Windows machines currently cannot be used as control nodes.  Multiple control nodes can run at the same time in the same environment.  It is best practice to play the control node close to the systems that are being managed by Ansible to avoid network delays.<br><br>
-   **Managed node**:  The managed nodes in the Ansible taxonomy are the network devices or servers that are being managed by Ansible.  They are also called hosts and do not need to have Ansible installed on them or even Python, as discussed later in this chapter.<br><br>
-   **Task**:  Ansible tasks are the units of action.  You can run them as ad hoc commands by invoking them as follows:<br>`$ ansible [pattern] -m [module] -a "[module options]"`<br><br>
-   Playbook:  An Ansible playbook is a file that containers an ordered set of tasks that will be run in the order in which they are defined and as many times as needed.  Playbooks are written in YAML, which makes them easy to read, write, and share.  It is common (but not mandatory) to name the main playbook site.yml.<br><br>
-   **Inventory file**:  The inventory file is a list of all the managed nodes.  Also called the hostfile, it contains a list of IP addresses or hostnames for all the managed nodes as well as credentials and variables that can be referenced in playbooks.  Managed devices can be grouped together by function or location or based on some other feature.  As the hostfile grows larger in a bigger environment, it is a best practice to move the variables to dedicated files in **group_vars/** and **host_vars/** folders.  The group_vars folder would contain files with definitions for variables related to groups of devices, and the host_vars folder would contain files with definition of variables related to individual hosts.  Variables can define anything of interest for the specific environment: TCP/UDP port numbers, custom proxy configurations, timer values, and so on.  Inventory files are created in either INI or YAML format.  INI is a file format commonly used for configuration files of software platforms.  It was extensively used in older versions of Microsoft Windows to configure the operating System.  INI files are simple text files composed of basic structures such as sections, properties, and values.<br><br>
-   **Module**:  Ansible modules are units of parameterized Python code that get executed by Ansible.  Every module in Ansible has a specific use.  There are modules, for example, for installing server packages, for managing users, for configuring NTP servers on Cisco NX-OS switches, and for performing **show** commands on Cisco IOS devices.  Any individual module is invoked through an Ansible task, or multiple modules can be invoked through an Ansible playbook.

&nbsp;

Ansible can be installed in several different ways.

&nbsp;

-   **Using the operating system package manager**:  For example, on RedHat and CentOS Linux, it can be installed with the following command:<br>`sudo yum install ansible`<br><br>
-   **Using the Python package manager**:  The command for installing using the Python package manage is **pip install ansible**.  As always, it is recommended to use a virtual environment when working with Python.  Some dependencies might need to be installed before you can install Ansible.  Always check the latest release notes at https://docs.ansible.com.<br><br>
-   **Using the development version**:  You can clone the developer repository and issue the **source** command from a bash terminal.

&nbsp;

When automating server configurations, Ansible uses SSH to log in to the server, copies the Python code, and runs that code on the server.  There is no need to have an Ansible component installed on the managed servers, as the implementation is agentless.  For network devices, because there is limited Python support on the devices themselves, the Python code that represents the Ansible job runs locally on the control host.  The control host still uses SSH or NETCONF, RESTCONF, SNMP, and other interfaces to connect to the network devices and perform the desired configuration changes.  Ansible has a large number of modules that support several Cisco operating systems, including IOS, IOS XE, IOS XR, and NX-OS.  Some of the most popular Ansible modules that are used with Cisco devices are the following:

-   **ios_command** to send mostly **show** commands to devices running IOS and IOS XE operating systems
-   **ios_config** to send configuration commands to IOS and IOS XE devices
-   **nxos_command** and **nx_os_config** to interact with devices running the NX-Os operating system.

&nbsp;

Next, let's explore sample Ansible project.  Tow files are required in order to get started with Ansible playbook projects: an inventory file and a playbook.  In the following Ansible project, the inventory file is called **hosts**, and the playbook file is called **site.yml**:

&nbsp;

>   ***`Key Topic`***

&nbsp;

```
$ tree.
├── hosts
└── site.yml

0 directories, 2 files
```

&nbsp;

The hosts file contains an inventory of all the devices that will be managed by Ansible.  For example, the host file can look like this:

&nbsp;

```
$ cat hosts
[iosxe]
10.10.30.171

[iosxe:vars]
ansible_network_os=ios
ansible_connection=network_cli
```

&nbsp;

The brackets are used to define group names.  Groups are used to classify hosts that share a common characteristics, such as function, operating system, or location.  In this case, the [iosxe] group of devices contains only one entry: the management IP address of a Cisco CSR1000v router.  The **vars** keyword is used to define variables.  In this example, two variables are defined for the iosxe group.  The **ansible_network_os** variable specifies that the type of operating system for this group of devices is IOS, and the **ansible_connection** variable specifies that Ansible should connect to the devices in this group by using network_cli, which means SSH.  Variables can be referenced in playbooks; as mentioned previously, as the inventory file becomes larger, it is a good idea to separate the variables' definitions into separate files.

&nbsp;

The site.yml file in this example uses the **ios_command** Ansible module to send two commands to the iosxe group of devices: **show version** and **show ip interface brief**.  The YAML definitions of the playbook looks as shown in Example 15-1.

&nbsp;

Example 15-1 Ansible Playbook Example

```YAML
$ cat site.yml
---
- name: Test Ansible ios_command on Cisco IOS XE
  hosts: iosxe

  tasks:
    - name: show version and ip interface brief
      ios_command:
        commands:
            - show version
            - show ip interface brief
```

&nbsp;

YAML files start with **---** (and so do Ansible playbooks).  A playbook contains one or multiple plays.  The plays are logical groupings of tasks and modules.  The playbook in this example contains only one play that is marked by the hyphen (**-**) character at the leftmost position.  The name of the play is optional,l but it should contain an arbitrary string describing the actions that the play will perform.  The name is displayed on the screen when the playbook is executed.  The **hosts** keyword specifies which hosts or machines the play will be executed against.  In Example 15-1, the play is executed against the iosxe group of devices.  The value of the **hosts** parameter in the playbook must match the names of the groups, as defined in the inventory file.  Tasks are executed on the hosts that are defined in the play definition.  For each task, a name value should contain an arbitrary description of the task.  Like the name of the play, the name of the task is optional, but it should contain pertinent description text, as it is displayed to the screen when the playbook is executed.  **ios_command** is the name of the Ansible module that is part of the task in this example.  The **ios_command** module takes in multiple parameters, but only one of them is mandatory: the actual command that will be sent to the IOS device.  The two commands that will be sent to the [iosxe] device are **show version** and **show ip interface brief**.

&nbsp;

Some of the other optional parameters for the **ios_command** module are the following:

-   **interval**:  Specifies the interval of time, in seconds, to wait between retries of the command.
-   **retries**:  Configure the number of retries for a command before it is considered failed.
-   **wait_for**:  Specifies a list of conditions that have to be evaluated against the output of the command.  In this example, it could be defined as **wait_for: result[0] contains IOS-XE**, which verified that the output of the **show version** command contains the value of **IOS-XE** before going further with the execution fo the playbook.

&nbsp;

The playbook can be run from a terminal with the following command

&nbsp;

>   ***`Key Topic`***

&nbsp;

`$ ansible-playbook -i hosts site.yml -u admin -k`

&nbsp;

The **-i** option specifies the name of the inventory file, the **-u** option specifies the username that will be used to connect to the device, and the **-k** option specifies that the user should be asked for the connection password when the playbook is executed.  Connection credentials can also be included in the inventory file but in this example they are passed in as parameters of the ansible-playbook command.  The output of this command looks as shown in example 15-2.

&nbsp;

**Example 15-2** *Output of **ansible-playbook** Command*

```
$ ansible-playbook -i hosts site.yml -u admin -k
SSH password:

PLAY [Test Ansible ios_command on Cisco IOS XE] ************************************
******************************************

TASK [show version and ip interface brief] *****************************************
*************************************
ok: [10.10.30.171]

PLAY RECAP *************************************************************************
*****
10.10.30.171               : ok=1    changed=0    unreachable=0    failed=0
                           skipped=0    rescued=0    ignored=0
```

&nbsp;

The name of the play and the task are displayed to the screen, as are a play recap and color-coded output based on the status of the playbook execution.  In this case, the playbook ran successfully, as indicated by the value of **1** for **ok** status.  you can reuse the output of the two **show** commands in the playbook to build custom automation logic, or you can display it to the screen in JSON format by using the **-v** option with the **ansible-playbook** command.

&nbsp;

##  Puppet

&nbsp;

Puppet is a configuration management tool used to automate configuration of servers and network devices.  Puppet was founded in 2005, making it one of the most venerable automation tools on the market today.  It was created as an open-source project - and it still is today, but it is also available as a commercial offering called Puppet Enterprise that was created by Puppet Labs in 2011.  **It is written in *Ruby* and defines its automation instructions in files called *Puppet manifests***.  Where Ansible is agentless, **Puppet is agent based**.  This means that a software agent needs to be installed on each device that is to be managed with Puppet.  This is a drawback for puppet as there are instances of network devices in which third-party software agents cannot be easily installed.  Proxy devices can be used in these situations, but the process is less than ideal and means Puppet has a greater barrier to entry than other automation tools.  Puppet is architected in a client/server manner, with the client being the software agent and running on the managed devices and the server being the main Puppet server, referred to as the ***Puppet MasteR***.  By default, agents check their configuration every 30 minutes and ensure that a match exists between the expected configuration and the local configuration.  There are software agents for Linux and Windows hosts, as well as for various network devices, including Cisco NX-OS and IOS XR.

&nbsp;

Puppet manages systems in a declarative manner, meaning that the administrator defines the state the target system should be in without worrying about how the system gets to that state.  Puppet models the desired system state, enforces that state, and reports any differences between the desired state and the current state of the system for tracking purposes.  In order to model the system states, Puppet uses a declarative resource-based language called ***Puppet Domain Specific Language (DSL)***.  The desired state of the system is defined in this language, and Puppet converges the infrastructure to the desired state.  The communication between the puppet Master and the agents is over an encrypted SSL connection.

&nbsp;

>   ***`Key Topic`***

&nbsp;

Several components make up the Puppet architecture, as shown in Figure 15-4.

&nbsp;

**Figure 15-4** *Puppet Architecture*

![Figure 15-4 Puppet Architecture](assets/images/Figure%2015-4%20Puppet%20Architecture.jpeg)

&nbsp;

The central control server, the Puppet Master, provides features such as reporting, web user interface, security, and more.  The software agents run on the target node that will be monitored by Puppet.  The agents connect to the Master and retrieve the correct configuration for the device they are running on.  Puppet Forge is a community-based central repository where people can share their Puppet manifests and modules.

&nbsp;

There are currently two separate versions of Puppet:

&nbsp;

-   **Open source**:  This community-driven version is a collection of smaller projects and binaries, including the main Puppet agent binaries, mcollective and facter.  mcollective provides orchestration capabilities, and facter is a separate binary that resides on the monitored devices and gathers facts about them.
-   **Enterprise**:  This version streamlines the installation process and the use of the various software packages required.  For example, a single agent package that contains both the agent software and facter is available with the Puppet Enterprise offering.  Enterprise Console, a single-pane-of-glass solution that presents a simplified view of all the facts collected by the agents, is also available with the Enterprise offering.

&nbsp;

For a system administrator or network administrator using Puppet as a configuration management solution, the first step is to define - using Puppet DSL - what the desired state of the infrastructure needs to be.  these definitions are captured in text files called ***Puppet manifests***.  Some examples of desired states at this stage could be the existence of a certain VLAN on all switches in the network or maybe just a subset of devices, how and which interfaces should be configured on border routers, and which NTP servers to use for time synchronization.

&nbsp;

Once the desired state is defined, Puppet offers the option to simulate the changes needed to reach that state and see what would happen if the changes were applied.  This gives the administrator a chance to dry run the Puppet manifests and take note of what changes would actually get applied to the devices.

&nbsp;

If the changes to be performed to reach the desired state are in line with expectations, the manifests can be executed, and the changes can be enforced.  The Puppet agents report back to the Master with the status of the tasks that are being executed.

&nbsp;

The Puppet software agent running on the managed devices is the enforcing element of the solution.  The other component that is usually installed on the managed device is facter, which has the role of gathering facts about the managed device and reporting them back to the Master control server.  facter reports to the control node facts such as operating system, hardware configuration, and number and type of interfaces.

&nbsp;

The Puppet manifests are standard text files that contain Puppet DSL code and have the .pp extension.  They contain declarative configuration and are descriptive and easy to read.  The following is an example of a manifest used to ensure that the interface Ethernet 1/3 is in Layer 2, or switching, mode:

&nbsp;

>   ***`Key Topic`***

&nbsp;

```
# Configuring the interface using Puppet
cisco_interface { "Ethernet1/3" :
    switchport_mode     =>  enabled,
}
```

&nbsp;

Puppet forge is a cloud-based repository that contains manifests and modules contributed by the community.  Puppet modules are collections of files and directories that contain Puppet manifests.  When you download modules from Puppet Forge, with each module you get a group of subdirectories that have in them all the components that are needed to specify the desired state.

&nbsp;

##  Chef

&nbsp;

Chef is another popular open-source configuration management solution that is similar to Puppet.  It is written in ***Ruby***, uses a ***declarative model***, is ***agent based***, and refers to its automation instructions as ***recipes*** and ***cookbooks***.  Several components are part of the Chef Infra offering, as shown in Figure 15-5.

&nbsp;

**Figure 15-5** *Chef Architecture*

![Figure 15-5 Chef Architecture](assets/images/Figure%2015-5%20Chef%20Architecture.jpeg)

&nbsp;

A Chef workstation is an administrator computer used to manage the network.  One or more workstations can exist in an environment, depending on the size and complexity.  A Chef workstation contains all the tools necessary for developing and testing the infrastructure automation tasks that are captured in documents called ***recipes***.  A Chef workstation has an instance of Chef Infra client and can run command-line tools such as **chef** and **knife** as well as testing tools such as **Test Kitchen**, **ChefSpec**, and **Cookstyle**.  A workstation computer also includes **chef-repo**, the central repository in which recipes and cookbooks are created, tested, and maintained.  Chef cookbooks contains recipes, attributes, libraries, files, templates, tests, custom resources, and metadata.  chef-repo should be managed with a version control system such as Git.  Recipes are authored in Ruby, and most of them contain simple configuration patterns that get enforced through the Chef client.  Cookbooks are uploaded from the workstation to the Chef Infra Server.

&nbsp;

>   ***`Key Topic`***

&nbsp;

Chef Infra Servers acts as the main hub for all the configuration information.  Chef Infra Client, which is installed on each managed device, connects to Chef Infra Server to retrieve the configuration data that will be enforced on the managed client device.  After each Chef Infra Client run finishes, the run data is uploaded to Chef Infra Server for troubleshooting and historical purposes.  The actual managed device configuration work is done as much as possible through Chef Infra Client on the managed device; offloading these tasks from Infra Server makes the Chef solution more scalable.  Infra Server also indexes all the infrastructure data, including environments, nodes, and roles, making them available for searching.  The Chef management console is a web-based interface through which users can managed nodes, cookbooks, and recipes, policies, roles, and so on.

&nbsp;

Cookbooks are the fundamental building blocks for configuration and policy distribution with Chef.  A cookbook defines a scenario and contains everything needed to support that scenario: recipes that specify the resources to use, templates, attribute values, tests, metadata, file distributions, and custom resources and libraries.  A large set of resources to support the most common infrastructure automation requirements come built in with Chef Infra Client.  As Chef is written in Ruby, additional resources and capabilities can easily be created, if necessary.

&nbsp;

A Chef node is any device that has the Chef Infra Client software installed, which means it is managed by Chef Infra.  A large variety of nodes are supported by Chef Infra, including virtual and physical servers; cloud-based nodes running in public and private clouds; network devices from vendors such as Cisco, Arista, F5, and others; and container environments.  The main roles of Chef Infra client are to register the node and authenticate to Chef Infra Server using RSA public key pairs, synchronize cookbooks, configure the node to match the desired state specified in the cookbooks, and report back to Infra Server with status reports.  Chef has a tool built in to the Infra Client called **ohai** that is used to collect system information such as the operating system, network, memory, disk, CPU, and other data; ohai is similar to facter in Puppet.

&nbsp;

The following is a sample Chef cookbook used for configuring an interface on a Cisco Nexus switch:

&nbsp;

>   ***`Key Topic`***

&nbsp;

```
cisco_interface 'Ethernet1/3' do
     action :create
     ipv4_address '10.1.1.1' 
     ipv4_netmask_length 24
     ipv4_proxy_arp true
     ipv4_redirects true
     shutdown false
     switchport_mode 'disabled'
 end
```

&nbsp;

#   Cisco Network Services Orchestrator (NSO)

&nbsp;

Cisco Network Services Orchestrator (NSO) is a network services orchestration platform that enables end-to-end service deployment across multivendor physical and virtual infrastructure.  NSO can also be considered a multivendor service-layer SDN controller for data center, enterprise, and service provider networks.  It takes full advantage of NETCONF and YANG data models to provide a single API and a single user interface to the network that it manages.  Cisco NSO is the single source of truth in a network, constantly maintaining the current state of all the devices in its database.  It ensures that the configuration database is synchronized with all the network devices at all times.

&nbsp;

The main components of Cisco NSO are as follows (see Figure 15-6):

&nbsp;

>   ***`Key Topic`***

&nbsp;

-   Service manager
-   Device manager
-   Mapping logic
-   Configuration database

&nbsp;

**Figure 15-6** *Cisco NSO Architecture*

![Figure 15-6 Cisco NSO Architecture](assets/images/Figure%2015-6%20Cisco%20NSO%20Architecture.jpeg)

&nbsp;

The two primary technologies that are being used with Cisco NSO are the following:

-   **NETCONF**:  Used for standard and efficient automation of configuration
-   **YANG**:  Used for services and device configuration data modeling

&nbsp;

One of the main advantages of Cisco NSO is the model-to-model mapping capability.  A network administrator can define the data models for the end-to-end services that need to be implemented in the network (for example, Layer 3 MPLS VPNs, IPTV), and NSO maps those service models into device models for various vendor devices.  Because a large number of devices do not fully support NETCONF and YANG data models, NSO uses ***Network Element Drivers (NEDs)*** to model native device CLIs into YANG models.  NSO offers a level of abstraction that makes network devices transparent to the service management of the network.  This way, complex services can be described and implemented in simple ways and pushed to the devices no matter the device vendor, configuration semantics, and so on.

&nbsp;

NSO provides several northbound interfaces for service and platform management including NETCONF, RESTCONF, JSON/RPC, a CLI, a web user interface, and SNMP.  The NSO CLI and web user interface are usually used for human interaction with the platform, SNMP and NETCONF are used for monitoring, and the NETCONF, RESTCONF, and JSON/RPC interfaces are used for automation integration.  The NSO CLI has two modes of operation: operational mode, used primarily to monitor and maintain the platform, and configure mode, used to configure the services, the devices, and the NSO server.  Two CLI styles are offered to NSO operators: Cisco style, which is identical to the Cisco CLI, and Juniper style, which is identical to the Juniper CLI.  CLI users can easily switch between them by using the **switch cli** command.

&nbsp;

The southbound communication with the network device is done through components called ***Network Element Drivers (NEDs)***, which implement a large set of southbound interfaces, including NETCONF, the CLI, SNMP, and OpenFlow.

&nbsp;

The logical architecture of Cisco NSO is a dual-layered approach: a device manager component that handles the device configuration scenarios and a service manager component that provides an interface for the administrator to define the services that need to be implemented in the network.  The configuration data store, called the ***Configuration Database (CDB)***, is in sync with all the devices in the network and contains all the devices and services configurations.  A dedicated mapping layer manages the correspondence between the service models and the device models.

&nbsp;

>   ***`Key Topic`***

&nbsp;

The Cisco NSO Core Engine manages critical operational functions such as transactions, high-availability replication, and upgrades and downgrades, role-based access control, and rollback management.  All operations in NSO are handled by the transaction manager.  The Core Engine connects all the other NSO components together; it is the communication backbone for tall other components and is the process that reads the initial configuration defined in the ncs.conf file.

&nbsp;

The CDB stores all the platform data in a RAM database, including the NSO configuration, the configurations of all services and all managed devices, and all NSO operational data.  The CDB is stored in RAM for increased speed and quick response, and a persistent version of it is stored on the disk drive of the server.  The CDB is a hierarchical database organized in a tree-like structure, and although other database solutions can be used with NSO, it is recommended to use CDB as it has been optimized for NSO and the transactional nature of the solution.

&nbsp;

With the Cisco NSO service manager, users develop YANG models of the services they want deployed in the network, such as IPTV or MPLS VPNs.  At this stage, the service model also has to be mapped to the corresponding device configuration model.  This is done either through configuration templates that map service parameters into device configuration parameters or programmatically by building the mapping logic with Java or Python code.  The lifecycle of the services defined in NSO is managed by a FASTMAP algorithm.  As services get created, modified, and deleted, FASTMAP dynamically reacts and adjusts the configuration of the devices in the network to reflect the status of the service models.  In addition, FASTMAP enables the following functions:

- **Service dry-run**:  NSO calculates what the device changes would be if the service model were to be pushed on the devices in the network.
- **Service check-sync**:  The service configuration is verified to be in sync with the actual device configuration.  Device configuration drift can be detected this way.
- **Service re-deploy**:  Device configurations can be redeployed to restore a service on the network.

&nbsp;

The NSO device manager manages the network devices by using YANG data models and NETCONF.  For devices that natively implement NETCONF and YANG models, the device manager is automatic; devices that do not support NETCONF are integrated in the platform with NEDs.  NEDs that support different vendor CLIs as well as SNMP configuration and hundreds of other southbound management options come with Cisco NSO by default.  If needed, custom NEDs can be developed to address any device management protocol that is not already included with the default installation.  Distributed atomic transactions are used for all configuration changes on all the devices in the network.  If applying the configuration changes fails on any of the devices in the service path, a rollback mechanism can be used to revert all the changes and return the network devices to their initial status before the service deployment was attempted.  Configuration templates can be used at this stage to easily and quickly provision new devices.

&nbsp;

As of this writing, an educational version of Cisco NSO can be downloaded from Cisco DevNet at https://developer.cisco.com/site/nso/.  Installation steps can also be found there.  The following examples use Cisco NSO version 5.1 running locally on macOS Catalina.

&nbsp;

Cisco NSO provides a network simulation tool called **ncs-netsim**.  This tool makes it very easy to test NSO packages against simulated devices and to learn how to use the platform without any hardware needed.  The same YANG models are used for both real and NetSim simulated devices.  Several options are available with ncs-netsim, as shown in Example 15-3.

&nbsp;

**Example 15-3** *ncs-netsim Options*

```
$ ncs-netsim --help
Usage ncs-netsim  [--dir <NetsimDir>]
                  create-network <NcsPackage> <NumDevices> <Prefix> |
                  create-device <NcsPackage> <DeviceName>           |
                  add-to-network <NcsPackage> <NumDevices> <Prefix> |
                  add-device <NcsPackage> <DeviceName> |
                  delete-network                     |
                  [-a | --async]  start [devname]    |
                  [-a | --async ] stop [devname]     |
                  [-a | --async ] reset [devname]    |
                  [-a | --async ] restart [devname]  |
                  list                      |
                  is-alive [devname]        |
                  status [devname]          |
                  whichdir                  |
                  ncs-xml-init [devname]    |
                  ncs-xml-init-remote <RemoteNodeName> [devname] |
                  [--force-generic]                  |
                  packages                  |
                  netconf-console devname [XpathFilter] |
                  [-w | --window] [cli | cli-c | cli-i] devname |
                  get-port devname [ipc | netconf | cli | snmp]
See manpage for ncs-netsim for more info. NetsimDir is optional and defaults to
./netsim, any netsim directory above in the path, or $NETSIM_DIR if set.
```

&nbsp;

In order to create a new network simulation, the **create-network** option is used with the following parameters:

`ncs-netsim create-network <NCS package> <#N devices> <PrefixY>`

&nbsp;

*\<NCS package>* contains the path to where the NCS packages were installed.  By efualt, this is $NCS_DIR/packages/neds, and it contains NCS packages for Cisco IOS, Cisco IOS XR, Cisco NX-OS, Juniper JunOS, and so on.  the *\<#N devices>* parameter specifies the number of devices that will be created, and *\<PrefixY>* defines the prefix that will be used to name the devices.  For example, the following command would be used to create a network simulation with three cisco IOS devices named ios0, ios1, and ios2:

```
$ ncs-netsim create-network $NCS_DIR/packages/neds/cisco-
ios-cli-3.8 3 ios

DEVICE ios0 CREATED

DEVICE ios1 CREATED

DEVICE ios2 CREATED
```

&nbsp;

After the virtual devices are created, the simulation can be started with the **start** command:

```
$ ncs-netsim start
DEVICE ios0 OK STARTED
DEVICE ios1 OK STARTED
DEVICE ios2 OK STARTED
```

&nbsp;

An ordered list of all the devices that are running at any point on the NSO server can be obtained by using the **list** option for ncs-netsim, as shown in the following output:

```
$ ncs-netsim list

ncs-netsim list for  $NCS_DIR/nso-run/netsim


name=ios0 netconf=12022 snmp=11022 ipc=5010 cli=10022 dir=$NCS_DIR/
nso-run/netsim/ios/ios0

name=ios1 netconf=12023 snmp=11023 ipc=5011 cli=10023 dir=$NCS_DIR
/nso-run/netsim/ios/ios1

name=ios2 netconf=12024 snmp=11024 ipc=5012 cli=10024 dir=$NCS_DIR
/nso-run/netsim/ios/ios2
```

&nbsp;

Access to the console ports of all the simulated devices is possible by using the **cli-i** option followed by the name of the device, as in Example 15-4, which demonstrates console access to the ios0 device.

&nbsp;

**Example 15-4** *CLI Access to a Simulated Device*

```
$ ncs-netsim cli-i ios0

admin connected from 127.0.0.1 using console on *
ios0> en
ios0# show running-config
no service pad
no ip domain-lookup
no ip http server
no ip http secure-server
ip routing
ip source-route
ip vrf my-forward
 bgp next-hop Loopback 1
!
```

&nbsp;

The simulated devices implemented all control plane functions of the original operating system, but they do not have the data plane implemented, so they do not forward data traffic.  Even with this limitation, ncs-netsim network simulations are used extensively for testing and learning.

&nbsp;

As mentioned previously, Cisco NSO exposes a RESTCONF northbound interface for automation and integration purposes.  Before simulated devices are accessible over this interface, they have to be onboarded with Cisco NSO.  Devices can be onboarded through any of the northbound interfaces that Cisco NSO exposes, but in this example, the NSO CLI was chosen.  First, access to the NSO Cisco version (**-C** parameter) of the CLI for the admin user is obtained by issuing the **ncs_cli -C -u admin** command.  The default password is also **admin**.  Once access to the NSO CLI is granted, all the simulated Cisco IOS devices need to be added to the configuration of the Cisco NSO server.  Example 15-5 shows the configuration for ios0.

&nbsp;

**Example 15-5** *Onboarding Simulated Devices in Cisco NSO*

```
$ ncs_cli -C -u admin

admin connected from 127.0.0.1 using console on *
admin@ncs# config term
Entering configuration mode terminal
admin@ncs(config)# devices device ios0
admin@ncs(config-device-ios0)# address 127.0.0.1
admin@ncs(config-device-ios0)# port 10022
admin@ncs(config-device-ios0)# authgroup default
admin@ncs(config-device-ios0)# device-type cli ned-id cisco-ios-cli-3.8
admin@ncs(config-device-ios0)# state admin-state unlocked
admin@ncs(config-device-ios0)# exit
```

&nbsp;

When all three simulated IOS devices are onboarded and the configuration changes are committed, the devices can be displayed through a GET call over the RESTCONF interface.  Cisco NSO exposes its full functionality over this RESTCONF interface that is available by default starting at **http://\<NSO_Server_IP>:8080/restconf/root**.  A list of all the devices that have been onboarded can be obtained by performing a GET call on the following RESTCONF URI resource:

`http://<NSO_Server_IP>:8080/restconf/data/tailf-ncs:devices/device`.  The **curl** command to test this GET call looks as follows:

&nbsp;

>  ***`Key Topic`***

&nbsp;

```
$ curl --request GET 'http://localhost:8080/restconf/data/tailf-
ncs:devices/device' \

--header 'Content-Type: application/yang-data+json' \

--header 'Authorization: Basic YWRtaW46YWRtaW4='
```

&nbsp;

The Content-Type header needs to be **application/yang-data+json** because JSON-formatted YANG data models are exchanged over the RESTCONF interface.  The authorization header contains the basic authentication Base64 encoded for the **admin** username and the **admin** password.  A snippet of the response is shown in Example 15-6.

&nbsp;

**Example 15-6** *Output of the RESTCONF GET Devices API Call*

```
{
  "tailf-ncs:device": [
    {
      "name": "ios0",
      "address": "127.0.0.1",
      "port": 10022,
      "authgroup": "default",
      "device-type": {
       "cli": {
          "ned-id": "cisco-ios-cli-3.8:cisco-ios-cli-3.8"
        }
      },
      "commit-queue": {
        "queue-length": 0
      },
      "active-settings": {
        "connect-timeout": 20,
        "read-timeout": 20,
        "write-timeout": 20,
        "ssh-keep-alive": {
          "interval": 20,
          "count": 3
        },
        "ned-keep-alive": {
          "count": 3
        },
... omitted output
}
```

&nbsp;

The Cisco NSO RESTCONF interface can also be explored by using Postman.  For example, we can get the configuraiton of the ios01 simulated device from the NSO RESTCONF interface by using Postman instead of **curl**.  The URI that returns this information is very similar to the one explored previously, with one difference: h<span>ttp://localhost:8080/restconf/data/tailf-ncs:devices/device=ios1.  device=ios1 is used to indicate that the API should return only data specific ot hte device ios1.  The same headers for Content-Type, application/yang-data+json, Authorization, and Basic Auth with username **admin** and password **admin** need to be included.  Figure 15-7 shows the response from the NSO server after the Send button is pressed.

&nbsp;

**Figure 15-7** *RESTCONF GET Device API Call in Postman*

![Figure 15-7 RESTCONF GET Device API Call in Postman](assets/images/Figure%2015-7%20RESTCONF%20GET%20Device%20API%20Call%20in%20Postman.jpeg)

&nbsp;

## Cisco Modeling Labs/Cisco Virtual Internet Routing Laboratory (CML/VIRL)

&nbsp;

For a long time, building and maintaining infrastructure laboratories for testing and learning was time-consuming and required a lot of hardware, which needed space, power, and cooling; these labs were therefore very expensive in reach of only a few companies.  With the advent of ***Network Function Virtualization (NFV)*** and ***Cisco Modeling Labs/Cisco Virtual Internet Routing Laboratory (CML/VIRL)***, it has finally become easy and cost-effective to build infrastructure laboratories for all types of purposes.

&nbsp;

NFV is meant to decouple the hardware and software requirements that are typical for network devices and enable the software component or the network operating system to run on commodity hardware as a virtual machine, in a container, or on bare-metal servers.  while in most cases this leads to a loss of performance as custom hardware components such as ***Application Specific Integrated Circuits (ASICs)*** are not used with NFV offerings, it is usually considered an acceptable trade-off and offers a cost-effective way to take advantage of the software features that come with the network operating system.  If maximum performance is required, then a combination of dedicated custom hardware and software can be used to ensure guaranteed performance.  If the performance requirement is not as stringent, then an NFV alternative that includes just the software network operating system running on off-the-shelf hardware can be considered.  For example, Cisco offers the enterprise-grade network operating system Cisco IOS XE as a downloadable virtual machine in the form of a Cisco CSR1000v router for an NFV offering covering enterprise routing and switching capabilities, and it also offers IOS XE as a combination of hardware and software with the Cisco Catalyst 9000 Series of switches that offer 100Gbps interfaces and guarantee hardware routing and switching forwarding performance.  There is a virtual option for almost all Cisco operating systems currently available, including Cisco IOS XE with Cisco CSR1000v, Cisco IOS XR, with Cisco IOS XRv, and Cisco XS-OS with Cisco NS-OSv 9000.  These virtual instances can be run on x86 commodity hardware on premises or in private and public cloud environments.

&nbsp;

Cisco CML/VIRL is a powerful network simulation platform that is meant to be a flexible, all-in-one virtual networking lab.  With Cisco CML/VIRL and virtual instances of network operating systems from Cisco, it is possible to build entire network simulations.  The CML/VIRL version 2 web interface looks as shown in figure 15-8.

&nbsp;

**Figure 15-8** *CML/VIRL 2 Web Interface*

![Figure 15-8 CML/VIRL 2 Web Interface](assets/images/Figure%2015-8%20CML%20VIRL%202%20Web%20Interface.jpeg)

&nbsp;

>  ***`Key Topic`***

&nbsp;

Cisco CML/VIRL provides several interfaces: a CLI interface, a powerful web user interface (refer to Figure 15-8), and a REST API for automation and integration.  Multiple virtual instances of operating systems and solutions - including Cisco SD-WAN (Cisco vManage, Cisco vSmart, Cisco vBond, Cisco vEdge), Cisco CSR1000v, Cisco NX-OS, Cisco IOS XRv, Ubuntu, CoreOS, and TRex - are included with CML/VIRL by default, and it is possible to add other third-party virtual instances as well.  While the software features in the virtual instances of the Cisco network operating systems are in most cases on parity with the binary files installed on Cisco routers and switches, there are limitations in regard to the data plan implementation.  There are no switching backplanes and no ASIC modules with the virtual nodes in CML/VIRL, so throughput performance cannot be tested accurately in most cases.

&nbsp;

Using an external connector, a simulation running in Cisco CML/VIRL can be connected to the external world and the Internet.  This is done through the network interface on the server that cisco CML/VIRL is installed on.  Cisco CML/VIRL comes as an OVA file that can be deployed on virtual machine hypervisors such as VMware ESXi or on bare-metal servers.  For details on where to download CML/VIRL, installation steps, and licensing, see http://virl.cisco.com.

&nbsp;

Several lab simulations can be run at the same time.  Going back to the web user interface from Figure 15-8, under the Lab Manager tab, new labs can be created, modified, or deleted.  A lab in CML/VIRL is a logical construct used to organize and separate network topologies into separate environments.  Once a lab is created, a network topology can be built with the nodes and virtual instances that are available in CML/VIRL.  Network interfaces can be dynamically added and removed from CML/VIRL nodes and can be easily interconnected by simply hovering the mouse over the devices, selecting the network connection option, and then dragging the virtual network cable between the network connection option, and then dragging the virtual network cable between the devices that need to be connected.  Direct access to the console of the nodes is also managed through CML/VIRL.  In the case of servers, VNS connections are also supported.  Startup configurations for network devices can be specified prior to starting a simulation.  Network topologies are stored as YAML files and can be easily modified and shared.  Example 15-7 shows a snippet of a CML/VIRL network topology file.

&nbsp;

Example 15-7 CML/VIRL Topology File Example

```YAML
lab:
  description: ''
  notes: ''
  timestamp: 1581966586.8872395
  title: DEVASC official guide
  version: 0.0.3
nodes:
  - id: n0
    label: iosv-0
    node_definition: iosv
    x: -500
    y: 50
    configuration: ''
    image_definition: iosv-158-3
    tags: []
    interfaces:
      - id: i0
        label: Loopback0
        type: loopback
      - id: i1
        slot: 0
        label: GigabitEthernet0/0
        type: physical
  - id: n1
    label: csr1000v-0
    node_definition: csr1000v
...omitted output
```

&nbsp;

Downloading and uploading CML/VIRL network topology YAML files is easy and straightforward, and CML/VIRL users can easily share topologies and also store them in version control systems such as Git.  CML/VIRL can be part of a CI/CD pipeline for network configuration changes.  An example of such a pipeline could contain the following components and processes:

- CML/VIRL topology files could be stored together with automation scripts, device configuration files, and possibly Ansible playbooks in a version control system
- Whenever a change is made to any of these files, a build automation tool such as Jenkins or Drone can be used to monitor and detect the change in version and initiate the automation process.
- A complete automated process can create a test environment using the CML/VIRL REST APIs, build application servers, and deploy them in the test environment.
- The network configuration changes can be tested in this CML/VIRL virtual environment and a pass or fail criterion can be set based on the expectations of the administrator.
- If the tests pass, a configuration automation solution like Ansible could use playbooks and automation scripts to apply the test configuration changes in the production network.

&nbsp;

##  Python Automated test System (pyATS)

&nbsp;

pyATS and the pyATS library together form the Cisco test and automation solution, a vibrant ecosystem that aims to standardize how automated network tests are set up and run.  pyATS was developed by Cisco in 2014 and is used extensively internally by thousands of engineers to run unit tests, regression tests, and end-to-end and integration tests for a large number of Cisco products.  The solution is completely developed in Python33, making it easy to work with, scalable, and extensible.  Millions of pyATS tests are run every month internally at Cisco.  pyATS tests provide sanity, feature, solution, system, and scale checks for any type of physical or virtual device, including routers, switches, access points, and firewalls.

&nbsp;

The solution has two main components: the pyATS test framework and the pyATS library, which used to be called Genie but was renamed in an effort to simplify the nomenclature of the product.  the pyATS test framework provides ways to define how the network topologies are created and modeled, how to connect to devices through connection libraries, and how to actually perform the tests and generate reports.  The pyATS library builds on this infrastructure framework and provides easy-to-use libraries that implement pyATS features, parsers to interpret the data received from the devices, a mechanism for modeling network device configurations for both Cisco and third-party vendors, reusable test cases in the form of triggers and verifications, and the ability to build test suites through YAML-based text files.  In the rest of this chapter, when pyATS is mentioned, assuming that we are referring to the product as a whole, unless otherwise specified.  Figure 15-9 shows the components of the pyATS solution.

&nbsp;

> ***`Key Topic`***

&nbsp;

**Figure 15-9** *pyATS Architecture*

![Figure 15-9 pyATS Architecture](assets/images/Figure%2015-9%20pyATS%20Architecture.jpeg)

&nbsp;

pyATS fits very well in infrastructure automation use cases, especially around configuration change validation.  As discussed earlier in this chapter, tools like Ansible, Puppet, and Chef are great at infrastructure configuration automation, but they do not have great change validation options.  pyATS can be easily integrated in day-to-day DevOps activities and CI/CD automation pipelines.  some of hte most common use cases for pyATS are as follows:

- **Profiling the current status of a network and taking a snapshot of both the configuration status as well as the operational data of the network**:  This can be done before and after a configuration change or a software upgrade/downgrade is performed to ensure that the network still performs within desired parameters.  For example, a snapshot of the network is taken with pyATS before a software upgrade is performed, and key metrics are noted, such as number of BGP sessions in the established state or the number and type of routing table entires or any other metric that is considered critical for that environment.  The software upgrade is completed, and then a new pyATS snapshot is taken to ensure that those critical metrics have values within expected parameters.  pyATS offers all the tooling to be able to automatically perform the network snapshots, compare key metric values, set pass/fail criteria, and even generate reports.
- **Automating configuration changes and monitoring of devices**:  By using the Conf module within the pyATS library, configuration changes can be performed in a uniform fashion across different devices from different vendors.  Together with the profiling capabilities, pyATS offers a full set of capabilities for infrastructure automation, including creating a snapshot of the network pre-change, performing the changes, taking another snapshot post-change, and continuously monitoring for any performance outliers.

&nbsp;

pyATS offers an abstraction layer and programmatically stores device configuration and operational data in Python objects such as dictionaries and lists.  It is not necessary to screen scrape and parse different proprietary CLI outputs, as pyATS automatically accomplishes this through its extensive collection of parsers and outputs the data into standard formats that can be easily consumed.  The platform is easily extensible and customizable with scripts and test cases that pertain to various environments.  A pyATS CLI is also available for network testers who are not comfortable with Python.  pyATS supports several options to connect to devices: Telnet, SSH, REST, NETCONF, and RESTCONF.

&nbsp;

pyATS can be installed through **pip** by issuing the following command:

`pip install pyats[full]`

&nbsp;

Different options are available:

- **pyats[full]** installs all pyATS components, the pyATS library framework, and optional extras.
- **pyats[library]** installs all the pyATS components iwthout the optional extras.
- **pyats** without any options installs jsut the pyATS test infrastructure framework.

&nbsp;

As of this writing, pyATS version 20.1 is the current version, and it is only available for Linux and macOS.  Microsoft Windwos is not directly supported, but Windows Subsystem for Linux (WSL) can be used to run pyATS on Windows 10.  As uaual, it is recommended to install pyATS in its own virtual environment.  A prebuilt Docker container with pyATS already installed can be found at https://hub.docker.com.  More up-to-date information on pyATS versions, documentation, and installation steps can be found online at https://developer.cisco.com/pyats/.

&nbsp;

In order to start iwth pyATS, a testbed YAML file needs to be created.  This file containers the connectivity details for all the devices in the testbed.  Example 15-8 shows an example of a YAML file with only one device.

&nbsp;

> ***`Key Topic`***

&nbsp;

**Example 15-8** *pyATS Testbed File*

```YAML
---
devices:
 csr1000v-1:
     type: 'router'
     os: 'iosxe'
     platform: asr1k
     alias: 'uut'
     credentials:
         default:
             username: vagrant
             password: vagrant
     connections:
         cli:
             protocol: ssh
             port: 2222
             ip: "127.0.0.1"
```

&nbsp;

Most of hte options, while definign devices in a testbed, should be self-explanatory.  there are just a few options that need to be explained in more detail.  first, the hostname - which is csr1000v-1 in Example 15-8 - has to match the configured hostname of the device.  Second, the alias is used to identify the device during script execution.  Thet test script can be reused on a different testbed as long as the aliases stay the same.  A complete list of values for the type, operating system, and platform is available with the pyATS documentation.  Say that you save this file and call it testbed.yaml.

&nbsp;

Example 15-9 shows a simply Python script that uses the pyATS library and loads the testbed.yaml file, searches in that file for a device with alias **uut**, conencts to that device, runs the **show version** command, and extracts the Cisco IOS XE version number and prints it to the screen.

&nbsp;

**Example 15-9** *pyATS Test*

```python
#! /usr/bin/env python
from genie.testbed import load

# Load the testbed
tb = load('testbed.yaml')

# Find the device with alias uut
dev = tb.devices['uut']

# Connect to the device
dev.connect()

# Parse the output of the show version command
output = dev.parse('show version')

# Extract the version number and print it to the screen
print('IOS-XE version number: ' + output['version']['version'])
```

&nbsp;

The **output** variable is a Python dictionary that contains the JSON standardized data returned by the **show version** command.  This makes it very easy to parse and extract the needed data from the output of the **show** command.

