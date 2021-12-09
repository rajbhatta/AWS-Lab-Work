# Overview of AWS Auto Scaling Group #
<img src="img/img1.png"/>

# What is Crosszone load balancing #
1. It reduces the need to maintain equivalent numbers of instances in each enabled Availability Zone.

# Launch Configuration # 
## 2.1 Introduction ##
1. A launch configuration is an instance configuration template that an Auto Scaling group uses to launch EC2 instances. 

2. When we create a launch configuration, we specify information for the instances. Include the ID of the Amazon Machine Image (AMI), the instance type, a key pair, one or more security groups, and a block device mapping.

## 2.2 Demo for launch configuration ##
<img src="img/2.png"/>
<img src="img/3.png"/>
<img src="img/4.png"/>
<img src="img/5.png"/>
<img src="img/6.png"/>
<img src="img/7.png"/>
<img src="img/8.png"/>
<img src="img/9.png"/>

<b>Note: Launch configuration is similar to launching AWS instance. </b>

# 3. Auto Scaling Group #
## 3.1 Launch auto scaling group ##
### 3.1.1 Auto Scaling Group is Launched in two private subnets within VPC as depicted in top diagram ###
<img src="img/img10.png"/>

### 3.1.2 Auto Scaling Group starts with 2 but it will scale to 6 on the basis of need ###
<img src="img/img11.png"/>

### 3.1.3 Increase instance when execute policy is met ###
<img src="img/img12.png"/>

### 3.1.4  When CPU utilization is more than 80% for 1 period of 5 minutes ### 
<img src="img/img13.png"/>

### 3.1.5. When CPU utilization is more than 80% for 1 period of 5 minutes then add 1 instance ###
<img src="img/img14.png"/>

### 3.1.6 Scale out condition for auto scaling ###
<img src="img/img15.png"/>

### 3.1.7 When CPU utilization is less than 40% for 1 consective period of 5 minutes ###
<img src="img/img16.png"/>

### 3.1.8 When CPU utilization is less than 40% for 1 consectuve period of 5 minutes then remove 1 instance ###
<img src="img/img17.png"/>

### 3.1.9 No notification group is added ####
<img src="img/img18.png"/>

### 3.1.10 Ne Key Value paid for Auto Scaling Group ###
<img src="img/img19.png"/>

### 3.1.11 Confirmation of information for Auto Scaling Group ###
<img src="img/img20.png"/>

<b><i> Note: We can edit launch configuration but we can delete and copy. </i></b>

# 4. Launching Load Balancer #
### 4.1.1 Launch Loadbalancer ###

<img src="img/img21.png"/>

### 4.1.2 Select public subnet for load balancer ###
<img src="img/img22.png"/>

### 4.1.3 Assign security group ###
<img src="img/img23.png"/>

### 4.1.4 Configure health check ###
<img src="img/img24.png"/>

### 4.1.5 Perform Cross-Zone load Balancing if required ###
<img src="img/img25.png"/>

### 4.1.6 Configure load balancer from Auto Scaling ###
<img src="img/img26.png"/>