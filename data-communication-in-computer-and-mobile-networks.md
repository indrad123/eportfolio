---
description: >-
  By Indra Dewaji, part of assignment of Computer and Mobile Networks,
  University of York, October 2021
---

# Data Communication in Computer and Mobile Networks

## Data Encapsulation and De-encapsulation

## 1.1       Data Encapsulation Transmission in the OSI Model

Data encapsulation is the process in which some extra information is added to add some features to it \[1]. Data encapsulation is encapsulated during transporting data from the Application layer until the physical layer in the OSI model. There are seven layers in the OSI models in the top-down approach, they are, Application, Presentation, Session, Transport, Network, Link, and Physical layer \[2, p.78].

However, in the encapsulation and de-encapsulation process in the OSI model, the application, presentation, and session layers are considered in the same application layer message \[2, p.82].  These layers are also called the upper layer which performs application-specific functions like data formatting, encryption, and connection management. Another layer in the OSI model is called a lower layer. These layers are transport, network, data link, and physical layer. These layers have functions such as routing, addressing, and flow control \[3].

## __<img src=".gitbook/assets/image (18).png" alt="" data-size="original">__

_Figure 1. Encapsulation and De-encapsulation in OSI Model \[2, p.82]_

Figure 1 above describes the encapsulation and de-encapsulation in the OSI model. The sender is passed a message in the upper layer to the transport layer. The transport layer takes the message and adds header segment information. The transport layer then passes the information to the network layer. The added information might have error detection to determine whether the bits in the route have been changed or not. The network layer takes the information and creating a network layer datagram. Then the datagram is passed into the data link layer which added header information and creates a link-layer frame. There are two types of each layer, header, and payload. A payload is typically a packet from the above layer. And the physical layer will convert it into bits and send it to the receiver packet by packet \[2, p.82].

## 1.2       Data De-encapsulation Transmission in the OSI Model

Data de-encapsulation is the reverse process of encapsulation \[1]. Figure 1 also describes the de-encapsulation process when the receiver receives bits in the physical layer. Bits unpacked into data-link header and payloads. The header identifies which information is extracted from the source. And its repeatedly removed the header in the layer above until it reaches the application layer where the message is extracted. In the simplest term, the process to pack the data is called encapsulation, and unpacked the data is called de-encapsulation.

## 1.3       Security Challenges in the OSI Model

There are several security challenges in the OSI model. The security challenge in the physical layer could be from the attack of jamming and manipulation of the data. Jamming used the denial-of-service method, used to reduce, or prevent the normal use of the internet, includes destruction or alteration of configuration between two machines, disruption of routing information, or disruption of physical information \[4].

Sniffing is another challenge in the OSI model. Sniffing is the method to get the sensitive information in the packet sent in the broadcast environment \[2, p86]. These techniques put the man in the middle of the network to capture all the information broadcasted. The next step is to remove all traces of suspicion \[5]. Currently, there is much free software available which causing this vulnerability to increase.

Security challenges increase from time to time. And there are no exact methods to make the model ideal because there are always bad guys who have always threatened the system for many different reasons. And the security subjects will always improve based on the threat trends.

## Data Exchange with UDP

User Datagram Protocol (UDP) is a connectionless, message-based protocol and provides only best-efforts service from end-to-end data delivery \[6]. Unlike TCP which requires a connection handshake during data exchange, UDP no needs to establish a connection during data exchange \[2, p.123]. There are typical issues in UDP such as, no acknowledgement from the destination, no congestion control, and no message continuation \[2, p.231].

In the real world, sample applications used the UDP, such as Voice of Internet Protocol (VoIP), Video Streaming, Multiplayer games, or even a ping into an IP destination. The packet loss during data exchange doesn’t become a big matter. Those applications do not need handshakes during data exchange.

Data exchange with UDP has several identified security issues. Sniffing is the most security issue case in the UDP. One of the samples is in Simple Network Management Protocol (SNMP). SNMP is used to control and monitor the network in the IP based. SNMP message sent in plaintext. It is easy for the attacker to create and send false SNMP responses where he is pretending as the real requester. Many sniffing tools can be used by the attacker. Since the message using plaintext, this can be decoded by the attacker. Nowadays, to secure the SNMP, we can use encryption and authentication during sending the message \[7].

Another security concern in the UDP is the Domain Name Server (DNS) attack. DNS is used to translate between hostnames and IP address \[7]. An attacker might tap a connection and give a fake reply with the wrong IP address. When it happened, the attacker manages to re-route the request from the requester to the host that the attacker-controlled. To secure the DNS, need authentication from the source of the message, and this can be done using DNS Security Extension (DNSSec). DNSSec adds additional security features, which are Resource Record Signature, DNS Public Key, Delegation Signer, and Next Secure \[8].

UDP is used by many application protocols to transport the packet. Need to consider the security aspect when using this protocol. The enhanced and updated security features should be always updated from time to time.



## References

\[1]   C.O Ezeagwu, K. Ndubuisi, C. Tochukwu, and E. Alagbu. _Comparative Analysis of OSI and TCP/IP Models in Network Communication_. Quest Journals ISSN(Online) __ :2321-3795 pp: 08-14, 2021.

\[2]   Kurose and Rose. Computer Networking, a Top-Down Approach, 7th Edition, England, Pearson, 2017.

\[3]   Ei Ei Khaing. _Comparison of DOD and OSI Model in the Internet Communication_. International Journal of Trend in Scientific Research and Development(ijtsrd), ISSN: 2456-6470, Volume-3 Issue-5, August 2019, pp.2574-2579.

\[4]   Syed Umar, P. Gayathri, N. Bashwanth, and Royyur Srikanth. _Attacks of Denial-of-Service on Networks Layer of OSI Model and Mantaining of Security._ Indonesian Journal of Electrical Engineering and Computer Science Vol. 5, No. 1, January 2017, pp. 181-186.

\[5]   Maria Genoveva M.S and Pedro Antonio A.M. _Security in the data link layer of the OSI model on LANs wired Cisco._ Journal of Science and Research: Revista Ciencia e Investigacion, E-ISSN: 2528-8083, Vol. 3, CITT 2017, pp. 106-112

\[6]   Natarajan Meghanathan. _A Tutorial on Network Security: Attacks and Controls_. Jackson State University, USA. [https://arxiv.org/ftp/arxiv/papers/1412/1412.6017.pdf](https://arxiv.org/ftp/arxiv/papers/1412/1412.6017.pdf) \[Accessed: Oct. 2021]

\[7]   Camilla Olsen. _Security Issues Relating to the Use of UDP_. SANS Institute, 2003.         &#x20;

\[8]   DNS Security Extension. [https://www.dnssec.net/](https://www.dnssec.net/) \[Accessed: Oct. 2021]

&#x20;
