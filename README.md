# Lab 2
[Fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo) this repo and clone it to your machine to get started!

Client implemented in C++

## Team Members
- Riad Alasadi

## Lab Question Answers

QA.1: How did the relibaility of UDP change when you added 50% loss to your local environment? Why did this occur?
The reliability of UDP diminished when 50% loss was added. When trying to send a sequence, sometimes the message would get lost. This would happen because 50% loss was added to the UDP.

QA.2: How did the reliability of TCP change? Why did this occur?
The reliability of TCP did not change because the server still received the messages but just at a slower rate. This is because it is resending the messages that it lost.

QA.3: How did the speed of the TCP response change? Why might this happen?
The speed of the TCP response decreases when the 50% loss was added. This happens because TCP is resending the loss. So since it keeps trying to resend what is lost it takes a longer time for the full message to be received.


QC.1: What is argc and *argv[]?
argc and *argv[] are used to be able to pass the inputs from the command line into the program. argc is a counter which is used to count the number of arguments entered in the command line and *argv[] is an array of pointers.

QC.2: What is a UNIX file descriptor and file descriptor table?
A UNIX file descriptor is an unsigned integer that handle for files or i/o resources. A UNIX file descriptor table is a collction of unsigned integers from the UNIX file descriptor, and the elements of these descriptors are pointers to the entries of the file descriptor table.

QC.3: What is a struct? What's the structure of sockaddr_in?
A struct is a collection of variables that are all part of a defined named group. Variables in a struct can be of different data types. The structure of sockaddr_in consists of:
	short sin_family;
	unsigned short sin_port;
	struct in_addr sin_addr;
	char sin_zero[8];
	
QC.4: What are the input parameters and return value of socket()?
The input parameters are domain, type, and protocol, in this respective order. So in the tcp_server.c file, AF_INET is the domain, SOCK_STREAM is the type, and 0 is the protocol. The return value is the socket file descriptor which is an unisigned integer.

QC.5: What are the input parameters of bind() and listen()?
The input parameters of bind() are socket (the socket descriptor), address (pointer to a sockaddr structure), and address_len (size of the address), in this respective order. The input parameters of listen() are socket (the socket descriptor) and backlog (the maximum length for the line of pending connections).

QC.6: Why use while(1)? Based on the code below, what problems might occur if there are multiple simultaneous connections to handle?
while(1) is used to keep receiving until the socket is closed. If there are multiple simultaneous connections to handle the issue will be that the server will lose messages as it is unable to process multiple simultanous messages from different connections.

QC.7: Research how the command fork() works. How can it be applied here to better handle multiple connections?
fork() is a system call used to create new processes which are able to run concurrently. This could be applied in the code to better handle multiple connections because fork() can create a process for each connection and so this can be used to better handle the multiple connections.

QC.8: This program makes several system calls such as 'bind', and 'listen.' What exactly is a system call?
A system call is used to make a request for an action for a program to interact with the operating system's kernel.
 

References: 
I used the following youtube vidoes to guide my code
	1: https://youtu.be/MOrvead27B4
	2: https://youtu.be/fmn-pRvNaho

