# EC2 Instance Backup Step-by-Step.
	
There are two ways to implement backup of your EC2 instances on AWS:
  - If your instance is EBS backed, you can create the snapshots of the EBS volume.
  - You can create an AMI of your instances as a backup solution.
  
----- Manual EC2 Instance Backup by an EBS Snapshot:  
  
  1* Open AWS CONSOLE: https://aws.amazon.com/fr/console/
  
  2* Click the “Instances” section in AWS console under the EC2 dashboard.
  
  3* Select the instance for which you want to create a backup.
  
  4* Under the description tab for that instance, you can see the details of that instance which will also show you the block devices. Clicking on a block device will show the volume ID.
  
   5* Click on EBS ID (volume ID), which will take you to the volume section under the EC2 dashboard. To create the snapshot click on the action button and select “Create Snapshot” option.
   
   6* Click on EBS ID (volume ID), which will take you to the volume section under the EC2 dashboard. To create the snapshot click on the action button and select “Create Snapshot” option.
   
   ---> To restore volume from a snapshot.
   	1* Search for the snapshot under the snapshot section using its description.
	2* Right-click and select the “Create Volume” option.
	3* Fill in the required details in the Create Volume dialog box and click the “Create” option.
	4* A volume with the same snapshot will be created and then you can attach the new volume to an EC2 Instance for further use.
	
----- Manual Backup Using AMI: 
This solution can be used if your instance is not EBS backed up. To create the EC2 Instance backup, you can create the AMI of an Instance. Furthermore, by using the same AMI you can launch an instance in the same state.
    
    1* Search for the Instance for which you want to create the AMI. Select the “Create Image” option under Image after clicking on the action button.
    
	2* Follow the steps below once you have selected the “Create Image” option:
		- Enter the AMI details in the “Create Image” dialog box as below.
		- Enter the AMI Name and Description.
		- If you want your instance to stay in a running state without restarting while creating the AMI, then check the “No Reboot” option.
		- You can also customize the size and other options like “delete on termination”. The “delete on termination” option will delete the volume if the instance is terminated, otherwise, it will still be in an available state if the EC2 instance is terminated.  
