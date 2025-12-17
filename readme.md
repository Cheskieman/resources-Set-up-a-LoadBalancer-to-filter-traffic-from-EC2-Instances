# Tutorial on Configuring a Load Balancer to filter traffic for multiple EC2 instances.

## Full Step-by-Step guided with Snapshots to both describe and illustrate how to configure a Load Balancer to filter traffic for multiple EC2 Instances set up on AWS.

### This project will display how to create EC2 Instances that will be able to connect to both a newly created LoadBalancer via newly created Target Group(s) 

* How to create the necessary security groups to allow incoming traffic on the load balancer
* Type the correct code in order to create the website which will be both filtered & loaded from the EC2 Loadbalancer
* Create Target Group(s) so that we can connect our multiple created EC2 instances to the load balancer

#### Step-by-Step Instructions on how to set up connect EC2 instances via Target Groups and then connect them to a Load Balancer

* Select EC2 from the Dashboard and then select Security Groups from the left-hand EC2 navigation panel.
<p align="center">  
  <img src="resources/EC2INSTANCESETUPSELECTEC2FROMDASHBOARD.png" alt="Select EC2 from Dashboard" />  
</p>  

Select Security Groups from the left-hand navigation panel.

<p align="center">  
  <img src="resources/EC2SECURITYGROUPSSELECTTABFROMOPTIONS.png" alt="Select Security Groups from navigation panel" />  
</p> 
* Select Create Security Group
<p align="center">  
  <img src="resources/EC2INSTANCESSECURITYGROUPCREATESECURITYGROUP.png" alt="Select Create Security Group" />  
</p>  

*In the Basic Details Section of the Create Security Groups Page, give your Security Group a name.
<p align="center">  
  <img src="resources/EC2INSTANCESSECURITYGROUPGIVESECURITYGROUPNAME.png" alt="Give your Security Group a Name" />  
</p>  

* For the Security Groups Inbound Rules, set up HTTP Port 80 to be opened for Anywhere IPV4. (The purpose is that we want anyone to be able to access the website's load balancer that we will soon be creating.)
<p align="center">  
  <img src="resources/EC2INSTANCESSECURITYGROUPSETUPINBOUNDRULESSECURITYGROUP.png" alt="Set Inbound Rules" />  
</p>  
* Click Create Security Group on the bottom to complete the creation of the Security Group.
<p align="center">  
  <img src="resources/EC2INSTANCESSECURITYGROUPSSELECTCOMPLETECREATESECURITYGROUP.png" alt="Select Create Security Group" />  
</p>  
* Repeat the process of creating the Security Group. However: 

1) Create a different EC2 username 

2) Leave the Inbound and Outbound Rules Blank.



*Select Instances from the Navigation Panel 
<p align="center">  
  <img src="resources/EC2INSTANCESELECTINSTANCEFROMOPTIONS.png" alt="Select Instance from Navigation Panel" />  
</p>  

*Select Launch Instances Tab
<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCESELECTLAUNCHINSTANCEBUTTON.png" alt="Select Launch Instance Tab." />  
</p>  

* Give Your Instance a Name and Select an AMI for the Instance
<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCE NAMEANDAMI.png" alt="Select Instance Name andb AMI" />  
</p>  

* Select Instance Type and Keypair for your Instance.
<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCESETUPINSTANCETYPEANDKEYPAIR.png" alt="Select Instance Type & Keypair" />  
</p>  



* Under Network Settings, Select Existing Security Group and the 2nd Security group that was previously created (the security group that was previously instructed to leave both the Inbound and Outbound Rules Blank).
<p align="center">  
  <img src="resources/EC2INSTANCELAUNHINSTACESELECTEXISTINGSECURITYGROUPPLUSCREATEDSECURITYGROUP.png" alt="Select Existing Security Group & 2nd Security Group" />  
</p>  

*Select Edit tab from the Network Settings
<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCESETUPINSTANCESELECTEDITFROMTHENETWORKSETTINGS.png" alt="Select Edit from Network Settings" />  
</p>  


* Select Availability Zone from Expanded Options Network Settings and Type the Region-A that you are in (see photo for comparsion to have proper setup.)
<p align="center">  
  <img src="resources/EC2INSTANCESETUPINSTACEEDITAVAILBITYZONENETWORKSETTINGS.png" alt="Select Availability Zone." />  
</p>  


* Scroll further down the page and select the Advanced Details Tab
<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCESELECTADVANCEDETAILS.png" alt="Select Advanced Details Tab" />  
</p>  
* In the Advanced Details Tab, Scroll Down to the section where it says User Data and has a box right underneath it.
<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCEADVANCEDETAILSUSERDATA.png" alt="Scroll down to the User Data box" />  
</p>  

* Type the code (from the below photo) into the User Data Box/. (This will allow any user to access the EC2 Loadbalncer which we will create later on.)
<p align="center">  
  <img src="resources/S3 Search AWS Search Bar s3.png" alt="Select S3 from AWS Search Bar" />  
</p>  
* Select the Launch Instance tab at the bottom to complete Instance Creation.
<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCESELECTLAUNCHINSTANCEBUTTON.png" alt="Select Launch Instance Tab" />  
</p>  


* Now click the Pencil Icon on the newly created Instance and Modify the Name of your Instance to finsih with "-A".
<p align="center">  
  <img src="resources/CREATEDEC2INSTANCESELECTPENCICON.png" alt="Select Pencil Icon" />  
</p>  

* Select the Launch Instance Tab
<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCESELECTLAUNCHINSTANCEBUTTON.png" alt="Select Launch Instance Tab" />  
</p>  

* Repeat the above process of setting up the Instance with 2 slight variations.

*   1) The name of your instance should be different from the name of the previous instance set up.
*   2) Select from the Availability Zone in Network Settings and type the Region-B that you are in.


SELECT TARGET GROUP(S) FOR FUTURE CONNECTION TO LOAD BALANCER

* With EC2 Instances Created, select Target Group from the left-hand options.
<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCESELECTLAUNCHINSTANCEBUTTON.png" alt="Select Launch Instance Tab" />  
</p>  

* Select the Create target Button
<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCESELECTLAUNCHINSTANCEBUTTON.png" alt="Select Launch Instance Tab" />  
</p>  

* On Create Target Group, Give the Target Group a Name.
<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCESELECTLAUNCHINSTANCEBUTTON.png" alt="Select Launch Instance Tab" />  
</p>  

* Click Next at the bottom of the Create Target Group Page

<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCESELECTLAUNCHINSTANCEBUTTON.png" alt="Select Launch Instance Tab" />  
</p>  

* Select Create Target Group button bottom(?)
<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCESELECTLAUNCHINSTANCEBUTTON.png" alt="Select Launch Instance Tab" />  
</p>  


* Select both EC2S Click Deregister(?)

<p align="center">  
  <img src="resources/EC2INSTANCELAUNCHINSTANCESELECTLAUNCHINSTANCEBUTTON.png" alt="Select Launch Instance Tab" />  
</p>  



SETTING UP THE LOAD BALANCER

* Select Load Balancer from the left-handed options

* Click the Create Load Balancer Tab

* Select Create from Application Load Balancer

* Give your Load Balancer a name in the Basic Configuration Section

* In the Network Mapping Section, select the 2 Availability Zones that you created earlier.

*  In the Security Group Section, Remove the Default Security Group and replace it with the  "alb-sg". That is the first security group we created(specfially for the load balancer rules)

*  In the Listening and Routing Section, Select the Target Group Created Earlier in the Target Group Box.

* Scroll to the bottom and select Create Load Balancer.


BACK IN SECURITY GROUPS

* Select Security Group from the left-hand options

* Search f the earlier created security group name "web-sg" in the search box

* Select the Security Group ID for "web-sg".

* Select Edit Inbound Rules

* Click Add Rule

* Select HTTP for Type, Select Custom for Source and type "alb-sg" in search box(it will populate in the search box as the suffix to the security group once I click on it.)

* Click Save Rules


##### Contribution Policy

This project is not accepting external contributions, including pull requests or feature requests.
