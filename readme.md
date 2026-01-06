# Testing Load Balancer Connectivity Across Multiple EC2 Instances

## A complete step-by-step guide to configuring an AWS Load Balancer with target groups

Create EC2 Instances

Create and configure target groups for EC2 instances

 Configure an AWS Load Balancer to filter and distribute traffic

### This project will demonstrate how to

Set up multiple EC2 instances

Create and configure target groups

Register EC2 instances with the target groups

Attach target groups to an AWS Load Balancer

Verify load balancer traffic distribution across EC2 instances in the target groups
#### Step-by-Step Instructions Guidance

* Select EC2 from the Dashboard.
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
*In the Basic Details Section of the Create Security Groups Page, give your Security Group a name and a description.
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
  <img src="resources/EC2INSTANCEADVANCEDDETAILUSERDATABOXCODE.png" alt="DataBoxCode" />  
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
  <img src="resources/TARGETGTROUPSELECTTARGETGROUPFROMOPTIONS.png" alt="Select Target Group from left hand options" />  
</p>  

* Select the Create target Button
<p align="center">  
  <img src="resources/TARGETGROUPCLICKINITIALCREATETARGETBUTTON.png" alt="Select Create Target Group" />  
</p>  

* On Create Target Group, Give the Target Group a Name.
<p align="center">  
  <img src="resources/TARGETGROUPGIVETARGETGIVETARGETGROUPNAME.png" alt="Give Target Group Name" />  
</p>  

* Click Next at the bottom of the Create Target Group Page

<p align="center">  
  <img src="resources/TARGETGROUPCREATENEXT.png" alt="Click Next at bottom of page" />  
</p>  

* Select Create Target Group button at the bottom
<p align="center">  
  <img src="resources/TARGETGROUPSELECTTARGETGROUPBOTTOM.png" alt="Create Target Group button bottom" />  
</p>  


* Select both EC2'S Click Deregister

<p align="center">  
  <img src="resources/TARGETGROUPCLICKDEREGISITER.png" alt="Select Deregister" />  
</p>  


SETTING UP THE LOAD BALANCER

* Select Load Balancer from the left-handed options
<p align="center">  
  <img src="resources/LOADBALANCERSELECTLOADBALANCEROPTIONS.png" alt="Select Load Balancer from left hand options" />  
</p>
* Click the Create Load Balancer button
<p align="center">  
  <img src="resources/LOADBALANCERSELECTCREATELOADBALANCERTAB.png" alt="Select Create Load Balancer button" />  
</p>
* Select Application Load Balancer
<p align="center">  
  <img src="resources/LOADBALANACERSELECTAPPLICATIONLOADBALANCERCREATE.png" alt="Select Application Load Balancer" />  
</p>
* Give your Load Balancer a name in the Basic Configuration Section
<p align="center">  
  <img src="resources/LOADBALANCERBASICCONFIGURATIONGIVENAME.png" alt="Give Load Balancer a name" />  
</p>
* In the Network Mapping Section, select the 2 Availability Zones that you created earlier.
<p align="center">  
  <img src="resources/LOADBALANCERNETWORKMAPPINGSELECTSUBNETS.png" alt="Select 2 availability zones" />  
</p>
*  In the Security Group Section, Remove the Default Security Group and replace it with the  "alb-sg". That is the first security group we created(specfially for the load balancer rules)
<p align="center">  
  <img src="resources/LOADBALANCERSELECTSECURITYGROUP.png" alt="alb-sg as new security group" />  
</p>
*  In the Listening and Routing Section, Select the Target Group Created Earlier in the Target Group Box.
<p align="center">  
  <img src="resources/LOADBALANCERSELECTTARGETGROUP.png" alt="Select Earlier Created Target Group Box" />  
</p>
* Scroll to the bottom and select Create Load Balancer.
<p align="center">  
  <img src="resources/LOADBALANCERSELECTFINALCREATELOADBALANCERTAB.png" alt="Create Load Balancer" />  
</p>

BACK IN SECURITY GROUPS

* Select Security Group from the left-hand options
<p align="center">  
  <img src="resources/EC2SECURITYGROUPSSELECTTABFROMOPTIONS.png" alt="Select Security Group from options" />  
</p>
* Search  the earlier created security group name "web-sg" in the search box
<p align="center">  
  <img src="resources/BACKINSECURITYGROUPSSEARCHFOREARLIERCREATEDSECURITYGROUP.png" alt="Select Earlier Created Security Group" />  
</p>
* Select the Security Group ID for "web-sg".
<p align="center">  
  <img src="resources/BACKINTHESECURITYGROUPSELECTSECURITYGROUPID.png" alt="Select Security Group ID" />  
</p>
* Select Edit Inbound Rules
<p align="center">  
  <img src="resources/BACKINTHESECURITYGROUPSELECTEDITINBOUNDRULES.png" alt="Select Edit Inbound Rules" />  
</p>
* Click Add Rule
<p align="center">  
  <img src="resources/BACKINTHESECURITYGROUPCLICKADDRULE.png" alt="Click Add Rule" />  
</p>
* Select HTTP for Type, Select Custom for Source and type "alb-sg" in search box(it will populate in the search box as the suffix to the security group once I click on it.)
<p align="center">  
  <img src="resources/BACKINSECURITYGROUPCREATEINBOUNDRULES.png" alt="Create Inbound Rules" />  
</p>
* Click Save Rules
<p align="center">  
  <img src="resources/BACKINSECURITYGROUPSAVERULESFORINBOUNDRULES.png" alt="Click Save Rules Button" />  
</p>

##### Contribution Policy

This project is not accepting external contributions, including pull requests or feature requests.
