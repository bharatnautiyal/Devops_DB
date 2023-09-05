# SSH tunnel from MySQL Workbench to connect to a private Amazon MySQL DB EC2 instance that uses a public EC2 instance?


## Short description ##
Before you connect over an SSH tunnel using MySQL Workbench, confirm that the security group inbound rules, network access control lists (network ACLs), and route tables are configured to allow a connection between your EC2 instance and your RDS DB instance. Also confirm that the EC2 instance can be connected to over the internet using its public IP address from your local machine. For more information, see Scenarios for accessing a DB Instance in a VPC.


# Resolution

1. Open MySQL Workbench.
2. Select MySQL New Connection and enter a connection name.  (ssh-tunel)
3. Choose the Connection Method, and select Standard TCP/IP over SSH.
4. For SSH Hostname, enter the public IP address of your EC2 instance.
5. For SSH Username, enter the default SSH user name to connect to your EC2 instance. (usually: ubuntu, ect-user)
6. Choose SSH Key File, and select the .pem file used to connect from your file system. 
7. For MySQL Hostname, enter the database endpoint name.  (private IP of MySql EC2)
8. For MySQL Server Port, enter the port number that you use to connect to your database. (Default 3306)
9. For Username, enter the user name that you use to connect to your database.
10. For Password, enter the MySQL user password.
11. Choose Test Connection. After the test is successful, choose OK to save the connection.


After the connection is configured, you can connect to your private RDS DB instance using an SSH tunnel.
