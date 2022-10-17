#   "Do I Know This Already?" Quiz

&nbsp;

<ol>
    <li>What protocols were historically used to manage network devices?  (Choose two.)
        <ol type="a">
            <li>SMTP
            <li>SSH
            <li>TFTP
            <li>TELNET
            <li>SNNP
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            B, D.  Historically, network devices were managed through command-line interfaces (CLIs) using protocols such as Telnet and Secure Shell (SSH).
        </details>
    <br />
    <li>Which of the following is an example of a central network controller?
        <ol type="a">
            <li>Nagios
            <li>Grafana
            <li>Cisco DNA Center
            <li>Prometheus
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            C.  We've seen in Chapter 8 an example of a network controller with Cisco DNA Center.  Cisco DNA Center can be used to completely configure, manage, and monitor networks.
        </details>
    <br />
    <li>What are two common approach to infrastructure as code?
        <ol type="a">
            <li>Subjective
            <li>Declarative
            <li>Imperative
            <li>Objective
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            B, C.  There are usually two types of approaches to infrastructure as code: declarative and imperative.  With the declarative approach, the desired state of the system is defined, and then the system executes all the steps that need to happen in order to attain the desired state.  The imperative approach defines a set of commands that have to be executed in a certain order for the system to achieve the desired state.
        </details>
    <br />
    <li>Which of the following are issues with deploying infrastructure that are being addressed with infrastructure as code?  (Choose two.)
        <ol type="a">
            <li>The amount of time needed to deploy new infrastructure
            <li>Maintaining code across different versions
            <li>Troubleshooting issues
            <li>Lack of code documentation
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            A, C.  Implementing infrastructure as code processes leads to shorter deployment times for new infrastructure and faster and easier troubleshooting steps.
        </details>
    <br />
    <li>What is a key component of a continuous integration pipeline?
        <ol type="a">
            <li>Integration server
            <li>Delivery server
            <li>File server
            <li>Build server
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            D.  A key component of any CI pipeline is the build server, which reacts to developers committing their code into the central repository and starts the initial tests on the new code features.
        </details>
    <br />
    <li>What are the four steps in a CI/CD pipeline?
        <ol type="a">
            <li>Code, test, build, deploy
            <li>Source, build, test, deploy
            <li>Source, test, deploy monetize
            <li>Build, test, deploy, monetize
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            B.  The four steps of a CI/CD pipeline are source, build, test, and deploy.
        </details>
    <br />
    <li>What command is used to run Ansible playbooks?
        <ol type="a">
            <li><b>ansible</b>
            <li><b>ansible-playbook</b>
            <li><b>ansible-playbooks</b>
            <li><b>ansible-plays</b>
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            B.  Ansible playbooks can be run from a terminal with the <strong>ansible-playbook</strong> command.
        </details>
    <br />
    <li>What language are Puppet manifests written in?
        <ol type="a">
            <li>Puppet Domain Specific Language
            <li>Puppet Python
            <li>YAML
            <li>Java
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            A.  The Puppet manifests are standard text files that contain Puppet Domain Specific Language (DSL) code and have the .pp extension.
        </details>
    <br />
    <li>What language are Chef recipes written in?
        <ol type="a">
            <li>Python
            <li>Java
            <li>Ruby
            <li>Go
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            C.  Recipes are authored in Ruby, and most of them contain simple configuration patterns that get enforced through the Chef client.
        </details>
    <br />
    <li>What Cisco NSO component manages the YANG data models that get sent to a device?
        <ol type="a">
            <li>Service Manage
            <li>Device Manager
            <li>Core Engine
            <li>CDB
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            B.  The NSO Device Manager manages network devices using YANG data models and NETCONF.  For devices that natively implement NETCONF and YANG models, the device manager is automatic, and devices that do not support NETCONF are integrated in the platform by using Network Element Drivers (NEDs).
        </details>
    <br />
    <li>What language are Cisco CML/VIRL topology files written in?
        <ol type="a">
            <li>JSON
            <li>CSV
            <li>YAML
            <li>XML
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            C.  Network topologies are stored as YAML files and can be easily modified and shared.
        </details>
    <br />
    <li>What are the two main components of pyATS?
        <ol type="a">
            <li>pyATS test framework
            <li>pyATS repo
            <li>pyATS testbed
            <li>pyATS library
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            A, D.  The pyATS solution is composed of two main components: the pyATS test framework and the pyATS library, which used to be called Genie but was renamed in an effort to simplify the nomenclature of the product.
        </details>
</ol>
