# Tutorial on Configuring a Load Balancer to filter traffic for multiple EC2 instances.

## Full Step-by-Step guided with Snapshots to both describe and illustrate how to configure a Load Balancer to filter traffic for multiple EC2 Instances set up on AWS.

### This project will display...........

#### Step-by-Step Instructions on how to set up ...........

* Select EC2 from Dashboard and then select Security Groups from the left-hand EC2 options.

* Select Create Security Group


*In the Basic Details Section of the Create Security Groups Page, give your Security Group a name.


* For the Security Groups Inbound Rules, set up HTTP Port 80 to be opened for Anywhere IPV4. (The purpose is that we want anyone to be able to access the website's load balancer that we will soon be creating.)

* Click Create Security Group on the bottom to complete the creation of the Security Group.

* Repeat the process of creating the Security Group. However, 1) Create a different username and leave the Inbound and Outbound Rules Blank.

*Select Instances from Left-Handed Options 


*Select Launch Instances Tab(photo can be cropped a bit)


##### Contribution Policy

This project is not accepting external contributions, including pull requests or feature requests.
