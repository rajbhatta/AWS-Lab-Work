# Accessing RDS from EC2 #
 ## 1. Installing MySQL client on EC2 #
 ```js
 sudo apt-get install mysql-client
 ```

 ## 2. Verify RDS access from EC2 using telnet ##
 ```js

 Install telnet on Ubuntu
 
 sudo apt-get install telnet

 ```

 ## 3. Verify access using telnet call ##
 ```js
telnet <RDS endpoint> <port number>
 ```


 ## 4. Use mysql-client to login to RDS ##
 ```js
 mysql -h mysql–instance1.123456789012.us-east-1.rds.amazonaws.com -P 3306 -u admin -p
 ```

<img src="img/img1.png"/>
