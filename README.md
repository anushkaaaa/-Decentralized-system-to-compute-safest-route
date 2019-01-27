# -Decentralized-system-to-compute-safest-route
Compute the safest path instead of shortest path using Google API

----------------------------------------------------
Note:
Read the report for detailed information about the project

----------------------------------------------------

Content:<br>
1. <b>Client</b> - Client files
2. <b>Server</b> - Application Server files
3. <b>dbServer</b> - Database Server files
4. <b>LoadBalancer</b> - Load Balancer files
5. <b>makefile</b> - The Makefile
6. <b>policy</b> - policy file for granting permissions 
7. <b>Project Report</b> - Report 
8. <b>Project Presentation</b> - Presentation 
9. <b>mysql-connector-java-5.1.46-bin.jar</b> - mysql connector jar file
10. <b>java-json.jar</b> - json jar file
11. <b>README.md </b><br>

----------------------------------------------------
Compilation and Execution:

1. Clone or download the folder:<br>
2. Open an instance of putty, Run the RMI Registry in the background - this will run at the set port(1400):<br>
<b>command: rmiregistry 4444&</b> <br>
3. Run the makefile <br>
<b>command: make</b> <br>
4. Run the MarketplaceServer<br>
<b>command: java -cp .:mysql-connector-java-5.1.46-bin.jar -Djava.security.policy=policy MarketplaceServer</b><br>
5. Open instances of putty on the above machines<br>
• tesla.cs.iupui.edu -- Client <br>
• rain.cs.iupui.edu -- Load Balancer <br>
• thunder.cs.iupui.edu, lightning.cs.iupui.edu -- Servers (1, 2)<br>
• in-csci-rrpc01.cs.iupui.edu - 10.234.136.55 -- Database Server<br>
<b>command: java -cp .:mysql-connector-java-5.1.46-bin.jar -Djava.security.policy=policy MarketplaceClient</b><br>
6. Follow following steps: <br>
  a. Start Database Server, <b>command: java -cp ".:mysql-connector-java-5.1.46.jar" -Djava.security.policy=policy dbServer.SafePathDB</b><br>
  b. Start Server 1 <b>command: java -cp ".:java-json.jar" -Djava.security.policy=policy Server.SafePathServer 1</b><br>
  c. Start Server 2 <b>command: java -cp ".:java-json.jar" -Djava.security.policy=policy Server.SafePathServer 2</b><br>
  d. Start Load Balancer <b>command: java -Djava.security.policy=policy LoadBalancer.LoadBalancer</b><br>
  e. Run Clients <b>command: java -Djava.security.policy=policy Client.Client</b><br>
7. To clean up i.e. clear the port number by killing the rmiregistry <br>
<b>command: fg</b><br>

---------------------------------------------------
On the client side: It will prompt for source and destination<br>

---------------------------------------------------
