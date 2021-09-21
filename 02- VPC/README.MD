# Design consideration for VPC #

## VPC to communicate with the internet by creating and attaching an internet gateway to the VPC? ##

- An internet gateway must be attached to the VPC.
- The route tables associated with your public subnet (including custom route tables) must have a route to the internet gateway.

- The security groups associated with your VPC must allow traffic to flow to and from the Internet.
- Any instances in the VPC must either have a public IP address or an attached Elastic IP address.

# Important consideration #
- Each subnet either public or private subnet in VPC must be attached to a route table.
- Each route table comes with rule to communicate within VPC.
