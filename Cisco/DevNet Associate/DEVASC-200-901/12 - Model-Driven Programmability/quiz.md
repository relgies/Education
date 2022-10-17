#   "Do I Know This Already?" Quiz

&nbsp;

<ol>
    <li>What network protocols support model-driven programmability?  (Choose three.)
        <ol type='a'>
            <li>NETCONF
            <li>RESTCONF
            <li>SSH
            <li>gRPC
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            A, B, D.  There are three standards-based programmable interfaces for operating on the YANG data models: NETCONF, RESTCONF, and gRPC.
        </details>
    <br />
    <li>What is the default port on which the NETCONF protocol runs?
        <ol type='a'>
            <li>TCP 22
            <li>TCP 830
            <li>UDP 161
            <li>UDP 69
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            B.  By default, the NETCONF server on the device runs on TCP port 830 and uses the SSH process for transport.
        </details>
    <br />
    <li>What framework does NETCONF use to exchange messages between the client and the server?
        <ol type='a'>
            <li>REST
            <li>gRPC
            <li>Apache Avro
            <li>RPCs
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            D.  Messages sent with NETCONF use remote procedure calls (RPCs), a standard framework for clients to send a request to a server to perform an action and return the results.
        </details>
    <br />
    <li>Which data type is not a YANG base data type?
        <ol type='a'>
            <li>Binary
            <li>Enumeration
            <li>Percent
            <li>Empty
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            C.  YANG defines a set of built-in types and has a mechanism through which additional types can be defined.  There are more than 20 base types, including binary, enumeration, and empty.  Percent is not a built-in data type.
        </details>
    <br />
    <li>Which component of a YANG module header uniquely identifies a module?
        <ol type='a'>
            <li>Prefix
            <li>Notification
            <li>Namespace
            <li>Organization name
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            C.  The YANG header contains the namespace for the module.  The namespace is used to uniquely identify each module on a system that implements NETCONF.
        </details>
    <br />
    <li>Which of the following is a popular Python library used to interact with NETCONF servers?
        <ol type='a'>
            <li>requests
            <li>ncclient
            <li>json
            <li>pyang
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            B.  One popular NETCONF client is the Python 3 ncclient library.
        </details>
    <br />
    <li>Which of the following are used for data encapsulation in RESTCONF messages?  (Choose two.)
        <ol type='a'>
            <li>XML
            <li>YANG
            <li>YAML
            <li>JSON
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            A, D.  RESTCONF data is encoded with either XML or JSON.  Compared with NETCONF, RESTCONF has added support JSON encoding.
        </details>
    <br />
    <li>What NETCONF operation is the equivalent of the RESTCONF PATCH method?
        <ol type='a'>
            <li>&lt;edit-config&gt; (operation="merge")
            <li>&lt;edit-config&gt; (operation="create/replace")
            <li>&lt;edit-config&gt; (operation="patch")
            <li>&lt;patch-config&gt;
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            A.  The PATCH method provides a resource patching mechanism.  It is equivalent to the NETCONF &lt;edit-config&gt; operation with operation=merge.
        </details>
    <br />
    <li>What RESTCONF resource allows for automatic discovery of the API root?
        <ol type='a'>
            <li>/discover/restconf
            <li>/.well-known/restconf
            <li>/.well-known/host-meta
            <li>/discover/root
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            C.  Per the RESTCONF standard, devices implementing the RESTCONF protocol should expose a resource called /.well-known/host-meta to enable discovery of root programmatically.
        </details>
    <br />
    <li>What types of subscriptions are supported by model-driven telemetry?  (Choose two.)
        <ol type='a'>
            <li>Static
            <li>Dynamic
            <li>Configured
            <li>Hard-coded
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            B, C.  There are two types of telemetry subscriptions.  With a dynamic subscription, the subscriber sends a request, usually via the <strong>ietf-yangpush.yang</strong> data model.  A configured subscription is configured via the CLI, NETCONF, or RESTCONF and is persistent between reboots.
        </details>
</ol>