# 1. Why should we need to use application load balancer ? #
<img src="imgs/1.png"/>

- Application load balancer are basically designed for managing load across ec2

- In the above picture we can see that loads are balanced using the URL and target groups

# 2. EC2 instances created for load balancers #
<img src="imgs/2.png"/>

# 3. Order target group is created #
<img src="imgs/3.png"/>

# 4. Path for order health check is provided #
<img src="imgs/4.png"/>

# 5. Order instance is provided to order target group #
<img src="imgs/5.png"/>

# 6. Assigned EC2 instance is in pending condition #
<img src="imgs/6.png"/>

# 7. Customer target group is created #
<img src="imgs/7.png"/>

# 8. Healthcheck URL for cusomter EC2 instance is provided #
<img src="imgs/8.png"/>

# 9. EC2 instance is added inside customer target group #
<img src="imgs/9.png"/>

# 10. Target group is created for customer order #
<img src="imgs/10.png"/>
<img src="imgs/11.png"/>

# 11. Application load balancer is created #
<img src="imgs/12.png"/>

# 12. Application load balancer is converted to internet facing #
<img src="imgs/13.png"/>

# 13. HTTP port is assigned to target group for load balancer #
<img src="imgs/14.png"/>
<img src="imgs/15.png"/>

# Rule for load balancer is detected #
<img src="imgs/16.png"/>