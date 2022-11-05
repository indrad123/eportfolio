---
description: >-
  By Indra Dewaji, part of assignment of Computer Architecture and Mobile
  Networks, University of York, September 2021
---

# UDP Transmission Simulation

## 1.      UDP Data Transfer Program

The main functionality of the program is to transmit the data from the sender to the receiver using the User Datagram Protocol (UDP). The transmission of the packet is sent by using “Stop and Wait” method and “Go Back N” method. The program is built using Java (Liberica JDK 11). Java is acknowledged as one of the programming languages with reliable capabilities for networking \[1]. Java is a platform independence programming language that provides libraries that include security, sending and receiving data, and other networking tools, which makes programming networking in Java is much easier compared to other programming languages \[1].

The program is divided into Sender and Receiver programs.  The sender uses a generic method for both methods, differentiated by the parameter of the sliding windows. The Stop and Wait will use sliding windows size 1, while Go Back N method is using sliding windows size 5. On the receiver side, the method is also used as a generic method to accept and send an acknowledgment to the sender. To transmit the packet, the sender program is using dataTransmission method, while accepting and receiving the packet in the receiver program is using TransmissionReceiver method. The program structure explains in Appendix A and the program test result is captured in Appendix B. The generic method for sending and receiving covered both methods which are explained below.

### 1.1       Stop and Wait Method

Stop and wait method on UDP data transfer, is a method to send data packets in a block, and then receive by the receiver. If the negative acknowledgment is sent by the receiver, the transmitter should retransmit the same packet \[2]. As an illustration, figure 1 describes how the program works.

The logic for the Stop and Wait method is implemented in the below steps:

a.      The sender starts by sending the packet reads from the file, each packet concatenates with the sequence identifier as header.

b.      The ACK sent by the receiver for the successfully packet and NAK for the incorrect packet received, it’s limited only if the packet is blank, but can be improved in the future enhancement with the byte checks for any corrupted data.

c.       After sending NAK, the receiver will discard the packet and wait for the same packet to be resent by the sender.

d.      If the re-transmit is successfully accepted, the receiver will add the packet into the _ArrayList_ in the sequence.

e.      The sender sends an “end” packet as an identifier that the packets are complete.

f.        After receiving an “end” packet from the sender, the receiver combines all the received packets in re-arrange into the fully arranged data and displays it on the screen.

&#x20;![](<.gitbook/assets/image (4).png>)

Figure 1. Stop and Wait \[3, p.248]

&#x20;

### 1.2       Go-Back-N (GBN) Protocol

In the Go-Back-N (GBN) protocol, multiple data packets are transmitted without waiting for the acknowledgment, but it’s limited to a maximum number \[3]. Figure 2 visualizes the scenario of GBN Protocol.

The logic for Go-Back-N (GBN) Protocol implemented in the below steps:

a.      The sender starts by sending the packet read from the file, each packet concatenates with the sequence identifier as header.

b.      After the pre-defined Sliding Windows packet is sent, the acknowledgment is requested. The ACK was sent by the receiver for the successfully received packet and NAK for the incorrect packet.

c.       For any NAK sent, the next sequence of packets received by the receiver is discarded and request the sender to re-transmit the NAK packet within the new sliding windows sequence.

d.      The packet that was successfully received is inserted into the _ArrayList_ and combined all after receiving the “end” identifier packet into readable data, then displays  on the screen.

![](<.gitbook/assets/image (10).png>)

Figure 2. Go-Back-N Protocol \[7]

&#x20;

## 2.      Evaluation of Networking Protocols, Tools, and Security

### 2.1       Network Protocol Comparison

In the transportation layer routing, User Datagram Protocol (UDP) and Transmission Control Protocol (TCP) are the two protocols largely used. The characteristic of User Datagram Protocol (UDP) is connectionless, which means that it does not require a handshake when sending a message, only provides best efforts service from end-to-end delivery \[4]. Data handling in these two protocols use different methods. TCP is used connection-oriented, guarantees the delivery of the message, with error handling to make sure the packet reaches the destination \[6]. UDP uses a simple transport method, connectionless, and simple error handling \[6]. Table 1. shows the comparison between TCP and UDP.

| **TCP**                                                                                                         | **UDP**                                                                                                                                                 |
| --------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Make sure the transmission is successful and the lost packet is re-sent                                         | Lost packet is not tracked                                                                                                                              |
| The sequence number used and re-order packet that sent in wrong order                                           | No checking in the packet when reaching the destination                                                                                                 |
| Additional functionality added which has the implication of slowness of the transmission                        | No additional functionality added which has resulted in a better time of transmission                                                                   |
| The OS needs to keep track of the transmission which needs additional resources                                 | Simple transmission and fewer resources require                                                                                                         |
| <p>Sample program and service use in TCP:</p><p>-          HTTP</p><p>-          HTTPS</p><p>-          FTP</p> | <p>Sample program and service use in UDP:</p><p>-          DNS</p><p>-          IP Telephony</p><p>-          DHCP</p><p>-          Video Streaming</p> |

Table 1. Comparison between TCP and UDP \[6]

From the table above, we can see there are typical issues in UDP such as lost packets are not tracked and no checking in the packet when reaching the destination. Other typical issues stated by Kurose and Rose are no congestion control and no message continuation \[3, p231]. TCP has reliable transmission over the network. It helps to determine specific computer should be connected in the network, providing how the data should be transmitted, addressed, packetized, routed, and received \[8]. But TCP has more overhead since additional functionality was added which has the implication of slowness of the transmission.

UDP is suitable for fast transmission but does not rely on the accuracy of the packet. As an example, the video streaming application usually will transmit large data but requires fast transmission. The security aspect is not really considered, and data packet loss is accepted to some extent. With the typical UDP using a simple transmission with less additional packet check, this could be a benefit over the TCP approach.

### 2.2       Security over UDP

Many applications are using UDP, such as DNS, IP Telephony, DHCP, Video Streaming, or even a Multiplayer game. The data packet loss during data exchange is not a concern when UDP is used. Also, a handshake during data exchange is not required.

However, there are some identified security issues on the data exchange with UDP. One of them is sniffing or Denial of Service (DoS). Sniffing is the process to capture and decode data packets transmitted over the network with the sniffer application \[9]. The methods in the sniffing attack are divided into promiscuous and non-promiscuous. The promiscuous attack is linked to the method that the sniffer steals the information from the traffic passing over all the network, while a non-promiscuous attack steals the information between sender and receiver \[9]. The sniffing attack is either executed manually or using sniffing tools which are nowadays available as an open-source application.

There is also another potential security risk is in the Simple Network Management Protocol (SNMP) using UDP. The message was sent as plain text through SNMP. The attacker will pretend like the real requester and send false SNMP responses. The message would easily be decoded by the attacker since it’s just plain text without any encryption \[10]. SNMP is an application-layer protocol to monitor and control between server and managed devices \[3, p.452].

Domain Name Server (DNS) attack is the other common attack over UDP. The translation between hostnames and IP address is the method used in DNS \[10]. Fake reply with the wrong IP address commonly used by an attacker. It’s re-routed the packet sent by the sender to the fake requester which the attacker managed.

Currently, the authentication method is used to secure the DNS. DNS Security Extension (DNSSec) is one of the methods to secure the DNS. The security feature added into DNSSec such as Resource Record Signature, Next Secure, Delegation Signer, and DNS Public Key \[11]. Common attack into origin authentication of the DNS, or attack into data integrity, or the method of authenticated denial of existence, protected by DNSSec \[11].

To mitigate the attacks above, we can use a protocol built on top of UDP such as Datagram Transport Layer Security (DTLS). DTLS can run in unreliable protocols such as UDP \[14, p.1]. Even though UDP doesn’t require any handshake, DTLS has the mechanism of a handshake between sender and receiver. The handshake protocol is responsible to identify the session identifier, an optional peer certificate, the method of compression, a chipper suite that helps secure the connection, a secret key, and a Boolean value as a state of the session can be resumed \[14, p.5]. The handshake flow can be identify in the below steps as explained by Claeys, T. et al:

a.      Peers agree on data exchange the compression method includes the encryption algorithm.

b.      The peers will exchange the encryption key parameter and also perform mutual authentication.

c.       The server sends the Server Certificate message depending on the authentication method and the cipher suite used, a method to secure the network connection. DTLS supports a root Raw Public Key (RPK) authentication, Certificate Authority Key (CA), and Pre-Shared Key (PSK).

d.      The server requests mutual authentication through a Client Certificate request.

e.      The final stage of the handshake protocol, the client sends _ChangeCipherSpec_ message to indicate that the key session was successfully installed. The last steps allow both peers to acknowledge that the handshake process were successful.

### 2.3       Wireshark as Monitoring Tool

As discussed in the previous section, sniffing is one security thread. But the sniffing method is also used to monitor the network. One of the popular tools is Wireshark which can run on multiple platforms under GNU General Public License \[12, p.2]. Wireshark has the capability to capture, view, and analyze data packets that can help administrators to track the issues which affected the network performance, connectivity, or other problems \[12.p,2].

Figure 3 and 4, shows the test from the previously created program captured in Wireshark. Wireshark can track the source and destination of the data packet including the size length and other information, such as port, IP address, or even data packet itself. At figure 4, we can see the data packet that has been sent.

The data packet is the basic entity in the network \[12, p.1]. Security implies in the network is all about data packets. Our simple experiment shows how vulnerable the system is because all data and traffic can be captured by a single tool only. All information such as port number, IP Address, data can be seen barely.

The network interface used by Wireshark. Wireshark is a software tool that tracks network traffic. Wireshark is commonly used by a network administrator to review TCP retransmission and network troubleshooting. Wireshark is also commonly used by the Network Security controller to inspect intrusion from the attacker, and indicate malware has been injected into the network or identify a suspicious domain or IP addresses \[13]. Wireshark could convert the network code into raw binary data that flow through the network.  Wireshark could be used as intrusion detection control for the user who has knowledge of the intrusion mechanism. Some advanced features noted by Sakshi Singh and Suresh Kumar are display filter, I/O graph, network conversation window, coloring rules, and expert information \[13].

![](<.gitbook/assets/image (37).png>)

Figure 3. Traffic Capture in the Wireshark

![](<.gitbook/assets/image (39).png>)

Figure 4. Details on the Packet Captured in Wireshark

### 2.4       The Modern Security Era

Networking has evolved from year to year. Jon Oltsik in his article, suggests at least five features should have in modern security \[15]. They are:

a.      Cover end-to-end process.

b.      Encryption/Decryption capabilities.

c.       Business-oriented security.

d.      Centralized control and distributed enforcement.

e.      Comprehensive monitoring and analytics.

Scientific research should evolve following the threats that also evolve.



## References

\[1]          _Java Network Programming, Second Edition_. O'Reilly Media, Inc. 2020. ISBN: 9781565928701.

\[2]          M. Moeneclaey, H. Bruneel, I. Bruyland and Doo-Young Chung, _Throughput Optimization for a Generalized Stop-and-Wait ARQ Scheme_, in IEEE Transactions on Communications, vol. 34, no. 2, pp. 205-207, February 1986, doi: 10.1109/TCOM.1986.1096507.

\[3]          Kurose and Rose. _Computer Networking, a Top-Down Approach_, 7th Edition, England, Pearson, 2017.

\[4]          G. Benelli. _A new ARQ scheme using a go-back-N protocol_. European transactions on telecommunications, 1990, Vol.1(6), p.615-620. ISSN: 1124-318X, 1541-8251; DOI: 10.1002/ett.4460010605.

\[5]          Natarajan Meghanathan. _A Tutorial on Network Security: Attacks and Controls_. Jackson State University, USA. [https://arxiv.org/ftp/arxiv/papers/1412/1412.6017.pdf](https://arxiv.org/ftp/arxiv/papers/1412/1412.6017.pdf) \[Accessed: Oct. 2021]

\[6]          Al-Dhief, Fahad & Sabri, Naseer & Abdul Latiff, Nurul Muazzah & Nik Abd Malik, Nik Noordini & Abd Ghani, Mohd Khanapi & Mohammed, Mazin & Al-Haddad, R.N. & Dawood, Yasir & Ghani, Mohd & Ibrahim Obaid, Omar. (2018). _Performance comparison between TCP and UDP protocols in different simulation scenarios_. International Journal of Engineering & Technology. 7. 172-176.

\[7]          Fayza Ahmed Nada. _Performance Analysis of Go-Back-N ARQ Protocol Used in Data Transmission Over Noisy Channels_. Advances in Science, Technology and Engineering Systems Journal Vol. 5, No. 4, 612-617 (2020).

\[8]          C.O Ezeagwu, K. Ndubuisi, C. Tochukwu, and E. Alagbu. _Comparative Analysis of OSI and TCP/IP Models in Network Communication_. Quest Journals ISSN(Online) __ :2321-3795 pp: 08-14, 2021.

\[9]          B, Prabadevi & Nagamalai, Jeyanthi. (2018). A Review on Various Sniffing Attacks and its Mitigation Techniques. Indonesian Journal of Electrical Engineering and Computer Science. 12. 1117-1125. 10.11591/ijeecs.v12.i3.pp1117-1125.

\[10]      Camilla Olsen. _Security Issues Relating to the Use of UDP_. SANS Institute, 2003.

\[11]      DNS Security Extension. [https://www.dnssec.net/](https://www.dnssec.net/) \[Accessed: Oct. 2021]

\[12]      Banerjee, Usha & Ashutosh, Vashishtha & Mukul, Saxena. (2010). _Evaluation of the Capabilities of WireShark as a tool for Intrusion Detection_. International Journal of Computer Applications. 6. 10.5120/1092-1427.

\[13]      Sakhsi Singh, Suresh K. _Capability of Wireshark as Intrusion Detection System._ International Journal of Recent Technology and Engineering (IJRTE). ISSN: 2277-3878, Volume-8 Issue-5, January 2020

\[14]      Claeys, T., Vucinic, M., Watteyne, T., Rousseau, F., Tourancheau, B. _Performance of the Transport Layer Security Handshake Over 6TiSCH_. Sensors 2021, 21, 2192. [https://doi.org/10.3390/s21062192](https://doi.org/10.3390/s21062192)

\[15]      Jon Oltsik. _5 must-have features in a modern network security architecture._ 2019. Cybersecurity Snippets. [https://www.csoonline.com/article/3406475/must-have-features-in-a-modern-network-security-architecture.html](https://www.csoonline.com/article/3406475/must-have-features-in-a-modern-network-security-architecture.html) \[Accessed: Oct. 2021]

&#x20;

## Appendices

## A. Program Structure

The program for sending the data kept in _Sender.java_ file. It has three primary method, the _main_ method is to control the whole of the program, the _dataTransmission(File Path, Sliding Windows Size)_ method, used to transmit the data based on the sliding windows input parameter, and the _readFromFile(File Path)_ method to read the data from the file.

![](<.gitbook/assets/image (40).png>)

Figure a.1. Sender.java Program Structure

The program for receiving the data kept in _Receiver.java_ file. It has only two primary methods, they are the _main()_ method is to control the whole program and the _TramsmissionReceiver()._

&#x20;__ ![](<.gitbook/assets/image (1).png>)__

Figure a.2. Receiver.java Program Structure

## B. Program Test Result

Program Compilation:

a.      Compilation for Sender.java, no error found.

![](<.gitbook/assets/image (42).png>)

b.      Compilation for Receiver.java, no error found.

![](<.gitbook/assets/image (17).png>)

c.       Run Receiver program.

![](<.gitbook/assets/image (36).png>)

d.      Run Sender program.

![](<.gitbook/assets/image (14).png>)

e.      Select method, first test is for Stop and Wait method, insert number 1 in the screen.

![](<.gitbook/assets/image (41).png>)

![](<.gitbook/assets/image (7).png>)

f.        The packet sent to the receiver. In the receiver side, the packet accepted, arrange in sequence, and display in the screen. The program will close the session after receive all the packet.

![](<.gitbook/assets/image (38).png>)

g.      Run the Receiver program again.

![](<.gitbook/assets/image (19).png>)

h.      Run 2nd scenario for Go Back N method. Run Sender program and select 2nd method by inserting number 2 in the screen.

![](<.gitbook/assets/image (12).png>)

![](<.gitbook/assets/image (6).png>)

## C. Code

### Sender

```
import java.io.BufferedReader;
import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
import java.io.DataOutputStream;
import java.io.DataInputStream;
import java.io.FileReader;
import java.io.IOException;
import java.io.ObjectInputStream;
import java.io.ObjectOutputStream;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;
import java.net.Socket;
import java.net.SocketException;
import java.net.SocketTimeoutException;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Scanner;
import java.io.File;
import java.io.FileReader;

public class Sender {

	// Constants Value
	private static final int PORT = 8999;
	private static final String HOSTNAME = "localhost";
	private static final int BUFFER_SIZE = 1024;
	private static final int TIME_OUT = 1000;
	private static final int WINDOWS_SIZE = 1;

	// Time (ms) before resending all the non-acknowledged packets
	public static final int TIMER = 30;

	// Variables
	private static String msgFromFile;
	private byte[] sendData;
	private byte[] receiveData;
	private DatagramSocket socket;
	private InetAddress inetAddress;
	private int packet;
	private int seq;
	private byte[] data;
	private boolean last;
	private boolean isAck = false;

	// Constructor
	public Sender(DatagramSocket socket, InetAddress inetAddress) {
		this.socket = socket;
		this.inetAddress = inetAddress;
	}

	/////////////////////////////////////////////////////////////
	// Main Class
	/////////////////////////////////////////////////////////////
	public static void main(String[] args) throws Exception, IOException, ClassNotFoundException {

		DatagramSocket socket = new DatagramSocket();
		InetAddress inetAddress = InetAddress.getByName(HOSTNAME);
		Sender sender = new Sender(socket, inetAddress);
		String path = (System.getProperty("user.dir")).toString() + "\\Umbrella.txt";
		sender.readFromFile(path);

		System.out.println("Select Method: [1] Stop and Wait (Sliding Windows Size = 1)");
		System.out.println("               [2] Go-Back-N (Sliding Windows Size = 5)");
		Scanner scanner = new Scanner(System.in);
		int answer = scanner.nextInt();
		switch (answer) {
		case 1:
			System.out.println("======================");
			System.out.println("STOP AND WAIT PROTOCOL");
			System.out.println("======================");
			sender.stopAndWait(msgFromFile);
			break;
		case 2:
			System.out.println("======================");
			System.out.println("GO BACK N PROTOCOL");
			System.out.println("======================");
			sender.goBackN(msgFromFile);
			break;
		}
		scanner.close();

	}

	////////////////////////////////////////////////////////////////////////
	// This class is used to implement stop and wait method ARQ
	// on the sender side.
	// The rule of the Stop and Wait method are:
	//
	// [1] Send one data packet at a time
	// [2] Send the next data packet only after receiving
	// the acknowledgement from the receiver
	// [3] If no acknowledgement during timeout period, the packet will be
	// resent
	//
	// The scenario used in this method, the packet that will be sent is
	// each one character from the message text and includes the sequence
	// number. The acknowledgement will be printed in the screen together
	// with the sequence number.
	//
	// ACK = Acknowledged
	// NAK = Not Acknowledged
	///////////////////////////////////////////////////////////////////////
	private void stopAndWait(String msgFromFile) throws SocketException {

		// calculate how many characters in the message
		int lengthMsg = msgFromFile.length();

		sendData = new byte[BUFFER_SIZE];
		receiveData = new byte[BUFFER_SIZE];

		// DatagramSocket socket = new DatagramSocket();

		// Set the timeout, if until the set timeout time no acknowledgement
		// the packet will be re-sent
		socket.setSoTimeout(TIME_OUT);

		int seqNumber = 0;

		if (lengthMsg > 0) {
			// Loop on each character on the text message
			for (int i = 0; i < lengthMsg; i++) {

				String packetToSent;
				String packetChar;
				boolean timeOut = true;

				// get substring of the character
				packetChar = msgFromFile.substring(i, i + 1);

				while (timeOut) {
					seqNumber++;

					System.out.println("Sending packet char: " + packetChar + " with sequence number: " + seqNumber);

					packetToSent = seqNumber + packetChar;
					sendData = packetToSent.getBytes();

					try {
						// Send UDP Packet to the receiver
						DatagramPacket packet = new DatagramPacket(sendData, sendData.length, inetAddress, PORT);
						socket.send(packet);

						// Receive the server's packet
						DatagramPacket received = new DatagramPacket(receiveData, receiveData.length);
						socket.receive(received);

						// Get the message from the server's packet
						String returnMessage = new String(received.getData(), 0, received.getLength());

						System.out.println("ACK from the receiver: " + returnMessage);
						// If receive an acknowledgement from the receiver, stop the while loop
						timeOut = false;

					} catch (SocketTimeoutException exception) {
						// If no acknowledgement, resent sequence number
						System.out.println("NAK from the receiver " + seqNumber + ") for character " + packetChar
								+ " char will be resent");

						seqNumber--;
					} catch (IOException e) {
						// TODO Auto-generated catch block
						// If no acknowledgement, resent sequence number
						System.out.println("NAK from the receiver " + seqNumber + ") for character " + packetChar
								+ " char will be resent 1");
						seqNumber--;
					}
				}
			}
		} else {
			// Throw a message if no string inside the file
			System.out.println("Your file is empty");
		}
		// Close the session
		socket.close();
	}

	////////////////////////////////////////////////////////////////////////
	// This class is used for Go Back N method. In the Go Back N method,
	// the data packet transmitted in a pre-defined windows without waiting
	// the acknowledgement at the beginning. As the ilustration, below is
	// a simple diagram how the idea of Go Back N method.
	// 1 -----> 1
	// 2 -----> 2
	// 3 -----> 3
	// 4 -----> 4
	// 5 -----> 5
	// 1 <----- 1 Ack
	// 2 <----- 2 Ack
	// 3 <----- 3 Nak
	// 4 <----- 4 Ack
	// 5 <----- 5 Ack
	// 3 -----> 3
	// 4 -----> 4
	// 5 -----> 5
	// The client send the packet to the server from sequence 1 until 5.
	// The acknowledgement received from 1 and 2, but packet 3 is having
	// issue being not acknowledged, then the packet from 3 forward will be
	// retransmit in the sliding windows that already defined.

	private void goBackN(String msgFromFile) throws IOException, ClassNotFoundException {

		// calculate how many characters in the message
		int lengthMsg = msgFromFile.length();
		int windowsCnt = 0;
		int lastAck = 0;
		int lastSent = 0;
		// int i = 0;
		boolean isErr = false;
		boolean inTheLoop = true;

		sendData = new byte[BUFFER_SIZE];
		receiveData = new byte[BUFFER_SIZE];

		// DatagramSocket socket = new DatagramSocket();

		// Set the timeout, if until the set timeout time no acknowledgement
		// the packet will be re-sent
		// socket.setSoTimeout(TIME_OUT);

		// int seqNumber = 0;

		if (lengthMsg > 0) {

			try {
				// Loop on each character on the text message
				for (int i = 0; i < lengthMsg; i++) {
					// while (inTheLoop) {

					String packetToSent;
					String packetChar;
					// boolean timeOut = true;

					// get substring of the character
					packetChar = msgFromFile.substring(i, i + 1);

					// while (timeOut) {
					// seqNumber++;

					System.out.println("Sending packet char: " + packetChar + " with sequence number: " + i);

					packetToSent = i + packetChar;
					sendData = packetToSent.getBytes();

					// try {
					// Send UDP Packet to the receiver

					DatagramPacket packet = new DatagramPacket(sendData, sendData.length, inetAddress, PORT);
					socket.send(packet);

					System.out.println("Sending packet " + packetToSent);

					lastSent = i;

					if (isAck == false) {
						windowsCnt = ((lastSent - lastAck) + 1) % WINDOWS_SIZE;
					} else {
						windowsCnt = (lastSent - lastAck) % WINDOWS_SIZE;
					}

					// get the acknowledgement in the Sliding Windows Size
					if (windowsCnt == 0 || lastSent == lengthMsg - 1) {
						System.out.println("------------------------------");
						System.out.println("Start Block of sliding Windows");
						System.out.println("------------------------------");

						int k = 0;

						isErr = false;
						if (isAck == false) {
							k = lastAck;
						} else {
							k = lastAck + 1;
						}
						int l = k + WINDOWS_SIZE;
						if (l >= lengthMsg) {
							l = lengthMsg;
						}
						for (int j = k; j < l; j++) {
							// Receive the server's packet

							DatagramPacket received = new DatagramPacket(receiveData, receiveData.length);
							socket.receive(received);

							// Get the message from the server's packet
							String returnMessage = new String(received.getData(), 0, received.getLength());

							if (returnMessage.isBlank() == true || returnMessage.isEmpty() == true) {

								isErr = true;
								i = lastAck;
								System.out.println("NAK from the receiver, packet: " + j + " will be re-sent");

							} else {

								if (isErr == false) {
									lastAck = j;
									// if ever acknowledged
									isAck = true;
								}
								System.out.println("ACK from the receiver for packet: " + returnMessage);
							}

							System.out.println("J =" + j);

						}

						System.out.println("------------------------------");
						System.out.println("End Block of sliding Windows");
						System.out.println("------------------------------");

					}

					System.out.println("I =" + i);

				}
			} catch (IOException e) {
				System.out.println(e);
			}
		} else {
			// Throw a message if no string inside the file
			System.out.println("Your file is empty");
		}
		// Close the session
		socket.close();

	}

	//////////////////////////////////////////////////////////////////////
	// Read the text from file
	// The static method used because read the file only need one time
	//////////////////////////////////////////////////////////////////////
	private void readFromFile(String pathFile) throws IOException {
		boolean readFile = true;
		boolean getFile = false;
		String path = pathFile;
		while (readFile) {
			try {
				if (getFile == true) {
					Scanner scanner = new Scanner(System.in);
					path = scanner.nextLine();
				}
				BufferedReader bufferedReader = new BufferedReader(new FileReader(path));
				// Read the text in the file
				msgFromFile = bufferedReader.readLine();

				bufferedReader.close();

				readFile = false;
				getFile = false;

			} catch (IOException e) {
				System.out.println("Default file: " + (System.getProperty("user.dir")).toString() + "\\Umbrella.txt");
				System.out.println("File is not found, please enter the correct path file:");
				getFile = true;
			}
		}

	}

}

```

### Receiver

```
import java.io.*;
import java.net.*;
import java.util.*;
import java.util.ArrayList;

public class Receiver {

	private static final int BUFFER_SIZE = 1024;
	private static final int PORT = 8999;

	// Probability of ACK loss
	public static final double PROBABILITY = 0.1;

	private DatagramSocket serverSocket;
	private int packet;
	private int seq;
	private byte[] data;
	private boolean last;

	static DataInputStream in;
	static DataOutputStream out;

	// Constructor
	public Receiver(DatagramSocket serverSocket) {
		this.serverSocket = serverSocket;
	}

	private void goBackN() throws IOException {

		
		int seq = 0;
		boolean test = true;
		
		boolean connect = true;
		
		ServerSocket serverSocket = new ServerSocket(PORT);
		System.out.println("Waiting for connection...");
		Socket socket = serverSocket.accept();

		in = new DataInputStream(socket.getInputStream());
		out = new DataOutputStream(socket.getOutputStream());

		
		while (true) {

			try {
				//for (int i = 0; i < 7; i++) {

					String rcvPacket = in.readUTF();

					
					System.out.println("Packet " + rcvPacket + " received");

					if (rcvPacket.equals("2b") && test == true) {
						rcvPacket = "";
						System.out.println("2b become null");
						test = false;
					}
					
					out.writeUTF(rcvPacket);
					out.flush();
					

				//}
			} catch (IOException e) {
				System.out.println(e);
			} 
			//finally {
			//	try {
			//		in.close();
			//		out.close();
			//	} catch (IOException e) {
			//		e.printStackTrace();
			//	}
			//}
		}

	}

	private void StopAndWait() throws IOException {
		// Set up byte arrays for sending/receiving data
		byte[] receiveData = new byte[BUFFER_SIZE];
		byte[] dataForSend = new byte[BUFFER_SIZE];

		boolean test = true;
		
		System.out.println("Wait for connection...");
		// Infinite loop to check for connections
		while (true) {

			// Get the received packet
			DatagramPacket received = new DatagramPacket(receiveData, receiveData.length);
			serverSocket.receive(received);

			InetAddress inetAddress = received.getAddress();
			int port = received.getPort();

			String messageFromClient = new String(received.getData(), 0, received.getLength());

			////////////////////////////////////
			// use for test purpose
			////////////////////////////////////
			if (test == true) {
				if(messageFromClient.equals("2b")) {
					messageFromClient = "";
					test = false;
			    }
			}
			
			dataForSend = messageFromClient.getBytes();

			System.out.println("Message from Client (Seq+Char): " + messageFromClient);

			received = new DatagramPacket(dataForSend, dataForSend.length, inetAddress, port);
			serverSocket.send(received);

		}
	}

	public static void main(String[] args) throws IOException, ClassNotFoundException {
		// Create a server socket
		DatagramSocket serverSocket = new DatagramSocket(PORT);
		Receiver receiver = new Receiver(serverSocket);

		//System.out.println("Select Method: [1] Stop and Wait (Sliding Windows Size = 1");
		//System.out.println("               [2] Go-Back-N (Sliding Windows Size = 5)");
		//Scanner scanner = new Scanner(System.in);
		//int answer = scanner.nextInt();
		//switch (answer) {
		//case 1:
		//	System.out.println("======================");
		//	System.out.println("STOP AND WAIT PROTOCOL");
		//	System.out.println("======================");
			receiver.StopAndWait();
		//	break;
		//case 2:
		//	System.out.println("======================");
		//	System.out.println("GO BACK N PROTOCOL");
		//	System.out.println("======================");
		//	receiver.goBackN();
		//	break;
		//}
		//scanner.close();
	}

}

```

### File

The file created as umbrella.txt and contains only text "Umbrella"
