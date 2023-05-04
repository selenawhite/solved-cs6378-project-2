Download Link: https://assignmentchef.com/product/solved-cs6378-project-2
<br>
<ol>

 <li>Source code must be in the C/C++/Java programming language.</li>

 <li>The program must run on UTD lab machines (dc01, dc02, …, dc45).</li>

 <li>You will need to know thread and/or socket programming and its APIs for the language you choose. It can beassumed that each process (server/client) is running on a single machine (dcXY). Please get familiar with basic UNIX commands to run your program on <em>dcXY</em>.</li>

</ol>

<h1>1          Description</h1>

<ol>

 <li>There are three servers in the system, numbered from zero to two.</li>

 <li>There are five clients in the system, numbered from zero to four.</li>

 <li>Assume that each file is replicated on all the servers, and all replicas of a file are consistent in the beginning. Tohost files, create separate directory for each server.</li>

 <li>A client can perform a READ or WRITE operation on the files.

  <ul>

   <li>For READ operation, one of the servers is chosen randomly by the client to read from it.</li>

   <li>For WRITE operation, the request should be sent to all of servers and all of the replicas of the target fileshould be updated in order to keep them consistent.</li>

  </ul></li>

 <li>READ/WRITE on a file can be performed by only one client at a time. However, different clients are allowedto concurrently perform a READ/WRITE on different files.</li>

 <li>In order to ensure the mentioned conditions, you must implement Ricart-Agrawala algorithm for distributed mutual exclusion, with the optimization proposed by Roucairol and Carvalho, so that no READ/WRITE violation could occur. The operations on files can be seen as <em>critical section </em></li>

 <li>The supported operations by servers are as follows:

  <ul>

   <li>ENQUIRY: A request from a client for information about the list of hosted files.</li>

   <li>READ: A request to read last line from a given file.</li>

   <li>WRITE: A request to append a string to a given file.</li>

  </ul></li>

</ol>

The servers must reply to the clients with appropriate messages after receiving each request.

<ol start="8">

 <li>Assume that the set of file does not change during the program’s execution. Also, assume that no server failureoccurs during the execution of the program. 9. The client must be able to do the following:

  <ul>

   <li>Gather information about the hosted files bu querying the servers and keep the metadata for future.</li>

   <li>Append a string h<em>client id,timestamp</em>i to a file <em>f<sub>i </sub></em>during WRITE operation. <em>Timestamp </em>is the value of the clients, local clock when the WRITE request is generated. This must be done to all replicas of <em>f<sub>i</sub></em>.</li>

   <li>Read last line of a file <em>f<sub>i </sub></em>during READ.</li>

  </ul></li>

 <li>Write an application that periodically generates READ/WRITE requests for a randomly chosen file from the setof files stored by the servers.</li>

 <li>Display appropriate log messages to the console or to a file.</li>

</ol>

Keep in mind to close all open sockets when your program exits/terminates.