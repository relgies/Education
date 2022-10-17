#   "Do I Know This Already?" Quiz

&nbsp;

<ol>
    <li>On what family of switches does Cisco ACI run?
        <ol type='a'>
            <li>Cisco Catalyst 9000
            <li>Cisco Nexus 9000
            <li>Cisco Nexus 7000
            <li>Cisco Catalyst 6800
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            B.  The Cisco Nexus 9000 family of switches can run in two separate modes of operation, depending on the software that is loaded.  The first mode is called standalone (or NX-OS) mode, which means the switches act like regular Layer 2/Layer 3 data center devices, which are usually managed individually.  The second mode is called ACI mode, in which the Cisco Nexus devices are part of an ACI fabric and are managed in a centralized fashion.
        </details>
    <br />
    <li>True or false:  An ACI bridge domain can be associated with multiple VRF instances.
        <ol type='a'>
            <li>True
            <li>False
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            B.  Bridge domains represent the Layer 2 forwarding domains within the fabric and define the unique MAC address space and flooding domain for broadcast, unknown unicast, and multicast frames.  Each bridge domain is associated with only one VRF instance, but a VRF instance can be associated with multiple bridge domains.
        </details>
    <br />
    <li>What Cisco ACI REST API endpoint is used for authentication?
        <ol type='a'>
            <li>https://APIC_IP_or_Hostname/api/aaaLogin.json
            <li>https://APIC_IP_or_Hostname/api/login
            <li>https://APIC_IP_or_Hostname/api/v1/aaaLogin
            <li>https://APIC_IP_or_Hostname/api/v1/login.json
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            A.  APIC REST API username- and password-based authentication uses a special URI that includes aaaLogin, aaaLogout, and aaaRefresh as the DN targets of a POST operation.
        </details>
    <br />
    <li>In Cisco UCS Manager, what is the logical construct that contains the complete configuration of a physical server?
        <ol type='a'>
            <li>Server profile
            <li>Service profile 
            <li>Template profile
            <li>None of the above
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            B.  The service profile is a logical construct in UCS Manager that contains the complete configuration of a physical server.  All the elements of a server configuration - including RAID levels, BIOS settings, firmware revisions and settings, adapter settings, network and storage settings, and data center connectivity - are included in the service profile.
        </details>
    <br />
    <li>What is the Cisco UCS Manager Python SDK library called?
        <ol type='a'>
            <li>ucsmsdk
            <li>ucssdk
            <li>ucsm
            <li>ciscoucsm
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            A.  The Cisco UCS Python module for UCS Manager is called ucsmsdk.  It can be installed using pip by issuing the following command at the command prompt: <strong>pip install ucsmsdk</strong>.
        </details>
    <br />
    <li>What is the managed object browser called in Cisco UCS Manager?
        <ol type='a'>
            <li>Mobrowser
            <li>UCSMobrowser
            <li>Visore
            <li>UCSVisore
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            C.  Cisco UCS Manager provides a managed object browser called Visore.  Visore can be accessed by navigating to https://&lt;UCS-Manger-IP&gt;/visore.html.
        </details>
    <br />
    <li>What is a Cisco UCS Director workflow?
        <ol type='a'>
            <li>The atomic unit of work in Cisco UCS Director
            <li>A single action with inputs and outputs
            <li>A collection of predefined tasks
            <li>A series of tasks arranged to automate a complex operation
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            D.  A workflow is a series of tasks arranged to automate a complex operation.  The simplest workflow contains a single task, but workflows can contain any number of tasks.
        </details>
    <br />
    <li>What is the name of the header that contains teh Cisco UCS Director REST API access key?
        <ol type='a'>
            <li>X-Cloupia-Access-Key
            <li>X-Cloupia-Request-Key
            <li>X-Cloupia-Secret-Key
            <li>X-Cloupia-API-Access
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            B.  Each REST API request must be associated with an HTTP header called X-Cloupia-Request-Key, with its value set to the REST API access key.
        </details>
    <br />
    <li>How are the managed objects organized in Cisco Intersight?
        <ol type='a'>
            <li>Management information table
            <li>Hierarchical management information tree
            <li>Management Information Model
            <li>Hierarchical Managed Objects Model
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            C.  The Intersight API is a programmatic interface to the Management Information Model similar to Cisco ACI and Cisco UCS Manager.  Just like Cisco ACI and Cisco UCS Manager, the Cisco Intersight Management Information Model is comprised of managed objects.
        </details>
    <br />
    <li>What does the Cisco Intersight REST API key contain?
        <ol type='a'>
            <li>keyId and keySecret
            <li>token
            <li>accessKey and secretKey
            <li>cookie
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            A.  An Intersight API key is composed of a keyId and a keySecret.  The API client uses the API key to cryptographically sign each HTTP request sent to the Intersight web service.
        </details>
</ol>