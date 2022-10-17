#  "Do I Know This Already?" Quiz

&nbsp;

<ol>
    <li>Which characteristic matches an SaaS deployment model?
        <ol type="a">
            <li>Provider deploys your software customizations.
            <li>Any update to the software requires a new license.
            <li>You can recommend tweaks to the underlying infrastructure.
            <li>None of the above
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            D.  A SaaS provider offers software for use and maintains all aspects of it.  You may be allowed to customize parts of the software configuration, but typically you are not allowed to change anything regarding how the software functions.
        </details>
    <br>
    <li>Which is a good deployment model for real-time IoT sensors?
        <ol type="a">
            <li>SaaS model
            <li>Edge computing model
            <li>Private cloud model
            <li>Hybrid cloud model
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            B.  IoT is heavily reliant on sensors detecting and responding to events in real time.  The edge computing model allows for centralized control of IoT sensors and real-time response because computing capabilities are closer to the sensor.
        </details>
    <br>
    <li>In which of the following ways are containers different from virtual machines?  (Choose two.)
        <ol type="a">
            <li>Containers have less storage requirements than VMs.
            <li>VMs can run any operating system, but containers run only on Linux.
            <li>Containers start at 500 ms, and VMs start in minutes.
            <li>VMs are better if you have a microservice architecture.
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            A, C.  Containers differ from virtual machines in that they are lighter (fewer resources used in storage), and they can start as fast as an application (500 ms), whereas a virtual machine requires the guest operating system to boot so it takes more time to start.
        </details>
    <br>
    <li>Which deployment methods is best for processes that are run periodically?
        <ol type="a">
            <li>Serverless
            <li>Containers
            <li>Virtual machines
            <li>All of the above
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            A.  Serverless deployment is great for applications that process data periodically but not designed for continuous use.
        </details>
    <br>
    <li>What is the second way of DevOps?
        <ol type="a">
            <li>Automation
            <li>Continuous learning and experimentation
            <li>Culture
            <li>Feedback loop
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            D.  The second way of DevOps is the feedback loop for continuous improvement.
        </details>
    <br>
    <li>What is continuous integration?
        <ol type="a">
            <li>Automated software delivery and deployment
            <li>An Agile software development technique
            <li>The process of merging development work with code base for automated testing
            <li>None of the above
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            C.  Continuous integration refers to the merging of development work with a shared code base to facilitate automatic testing and software building.
        </details>
    <br>
    <li>A docker image uses what type of file system?
        <ol type="a">
            <li>Layered file system
            <li>NFS
            <li>XFS
            <li>Union file system
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            D.  Docker natively uses the union file system for container construction.
        </details>
    <br>
    <li>What command do you use to launch an nginx container on port 80 of the host file system?
        <ol type="a">
            <li><b>docker image build -p 80 nginx</b>
            <li><b>docker start -it -d nginx -p 80|80</b>
            <li><b>docker container run -p 80:80 -d nginx</b>
            <li>None of the above
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            C.  To launch an nginx container on port 80, you run the command <strong>docker container run -p 80:80 -d nginx</strong>.
        </details>
</ol>