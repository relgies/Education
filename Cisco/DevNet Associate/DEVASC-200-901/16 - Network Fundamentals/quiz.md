#   "Do I Know This Already?" Quiz

&nbsp;

<ol>
    <li>Which OSI layer is responsible for establishing an end-to-end connection between the sender and the receiver?
        <ol type="a">
            <li>Network layer
            <li>Transport layer
            <li>Session layer
            <li>Presentation layer
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            B.  The transport layer, as the name suggests, is responsible for end-to-end transport of data from the source to the destination of the data traffic.  Connection-oriented protocols at the transport layer establish an end-to-end connection between the sender and the receiver, keep track of all the segments that are being transmitted, and have a retransmission mechanism in place.
        </details>
    <br />
    <li>What layer of the TCP/IP reference model is the equivalent of the network layer in the OSI model?
        <ol type="a">
            <li>Physical layer
            <li>Data link layer
            <li>Internet layer
            <li>Transport layer
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            C.  The Internet layer in the TCP/IP reference model corresponds in functions and characteristics to the network layer in the OSI model.
        </details>
    <br />
    <li>Which of the following are examples of application layer protocols in the TCP/IP reference model?  (Choose two.)
        <ol type="a">
            <li>TCP
            <li>HTTP
            <li>BGP
            <li>FTP
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            B, D.  There are a large number of application layer protocols, including the Hypertext Transfer Protocol (HTTP), which is used for transferring web pages between browsers and web servers, and File Transfer Protocol (FTP), which is used for transferring files between a client and a server.
        </details>
    <br />
    <li>What is the transport layer PDU called in the TCP/IP reference model?
        <ol type="a">
            <li>Data
            <li>Frame
            <li>Packet
            <li>Segment
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            D.  The TCP/IP reference model transport layer PDU is called a <em>segment</em>.
        </details>
    <br />
    <li>What is the role of the Preamble field in the EThernet header?
        <ol type="a">
            <li>It is used as padding data to ensure that the frame has at least the minimum number of bytes for transmission.
            <li>It is used as padding data to ensure that the frame has 1500 bytes for transmission
            <li>It is used to ensure that the frame was transmitted without data corruption.
            <li>It is used to synchronize the signal between the sender and receiver.
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            D.  The Preamble field consists of 8 bytes of alternating 1s and 0s that are used to synchronize the signals of the sender and receiver.
        </details>
    <br />
    <li>How many bits are in a MAC address?
        <ol type="a">
            <li>24 bits
            <li>48 bits
            <li>32 bits
            <li>64 bits
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            B.  A MAC address has 48 bits organized as 12 hexadecimal numbers.
        </details>
    <br />
    <li>What happens to a data frame for which a switch doesn't have the destination MAC address in its switching table?
        <ol type="a">
            <li>It gets discarded.
            <li>It gets transformed into a broadcast data frame.
            <li>It gets sent back to sender as it cannot be switched.
            <li>It gets flooded out all the ports except the port on which it was received.
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            D.  If a switch doesn't have the destination MAC address of the frame, it floods the frame over all the ports except the port on which it was received.  As the frame gets flooded throughout the network, eventually it will get to its destination.
        </details>
    <br />
    <li>What is the bit pattern in the first byte for Classic C IPv4 address?
        <ol type="a">
            <li>110XXXXX
            <li>11110XXX
            <li>10XXXXXX
            <li>1110XXXX
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            A.  The bit pattern for the first byte in a Class C IPv4 address is 110XXXXX.
        </details>
    <br />
    <li>What is the broadcast address for the 192.168.0.96/26 network?
        <ol type="a">
            <li>192.168.0.191
            <li>192.168.0.159
            <li>192.168.0.127
            <li>192.168.0.255
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            C.  The broadcast address for the network 192.168.0.96/27 is 192.168.0.127.
        </details>
    <br />
    <li>What are some of the characteristics of IPv6 addresses?  (Choose three.)
        <ol type="a">
            <li>They are 128 bits long.
            <li>Colons separate 16-bit hexadecimal fields.
            <li>Hexadecimal characters are case sensitive.
            <li>Successive fields of zero can be represented as ::.
        </ol>
        <br />
        <details>
            <summary><strong><em>Answer</em></strong></summary>
            A, B, D.  An IPv6 address is 128 bits long, with colons separating entries (x:x:x:x:x:x:x:x, where x is a 16-bit hexadecimal field).  Successive fields of zero can be represented as :: but only once per address, and the hexadecimal characters are not case sensitive.
        </details>
</ol>