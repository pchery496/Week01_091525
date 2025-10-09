CREATING AN AWS EC2 INSTANCE

1. Login to AWS Console Home page with an admin account containing sufficient admin permission
   + Note: Do not use the root account for this or any AWS exercises

2. In the search bar type "EC2" and select the EC2 Service that pops up

3. From the left hand menu, select "Security Groups" under the Network & Security category

4. Click on the "Create security group" on the top right corner and create a new SG for accessing the EC2 after creation
   + Under "Basic details", give it a name and an optional description
   + Under "Inbound rules", click Add rule with the following parameters: Type = HTTP, Source = 0.0.0.0/0
   + Under "Inbound rules", click Add rule again & add the following parameters: Type = SSH, Source = 0.0.0.0/0
   + Under "Outbound rules", DO NOT TOUCH, LEAVE IT AS IS!!!
   + Click on the "Create security group" button. The new SG should now be listed under the Security Groups

5. From the left hand menu, select "Instances" under the Instance category

6. Click on "Launch instances" to create a new EC2 instance
   + Under "Name and tags", give it a name
   + Keep the default selected Amaxon Machine Image (AMI) - Amazon Linux - includng the default 64-bit architecture and instance type
   + If not yet created, click on "Create new key pair" to create one with the following parameters: Name, Key pair type = RSA, Private key file format = .pem. Then select the newly created key pair.
   + Under "Network settings", click the "Select existing security group" button and select the SG previously created in Step 4.
   + Make sure "Auto-assign public IP" is set to Enable
   + Expand the "Advanced details" section, scroll all the way to the botton of the page, and paste the EC2 script in the text box under "User data - option." the script can be found at the following link: https://github.com/pchery496/bmc5/blob/main/ec2scrpit.

7. Click "Launch instance" to create the EC2 instance. You will redirected to the Instances page and wait for the EC2 Statsus check to complete where all checks have passed.

8. Click on the instance ID. From the summary page of tha particular instance, click on the "Public DNS" copy icon, open a new tab and paste the copied link to access the landing page (Web GUI) of the new EC2.


------------------------------------------------------------


TEARDOWN AN AWS EC2 INSTANCE

1. Login to AWS Console Home page with an admin account containing sufficient admin permission
   + Note: Do not use the root account for this or any AWS exercises

2. In the search bar type "EC2" and select the EC2 Service that pops up

3. From the left hand menu, select "Instances" under the Instance category. Check the botton next to the desired instance and then click "Instance state" > "Terminate (delete) instance". Click on "Terminate (delete)" to confirm. Wait for the termination to complete.

4. From the left hand menu, select "Security Groups" under the Network & Security category. Click the checkbox next the SG that was created for the EC2 instance, and then "Actions" > "Delete security groups." Click "Delete" button to confirm.

5. Optionally, nagivate to "Network & Security" > "Key Pair" to delete the key pair created for that EC2 instance
