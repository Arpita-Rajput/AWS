# AWS
1 . Practical 1: Creation of AWS user
Go to the AWS website (aws.amazon.com).

Click on the "Create an AWS Account" button.

Enter a valid email address and account name.

Enter the email verification code and verify your email.

Set a strong password.

Choose the account type (Personal/Business) and fill in your contact details.

Provide payment information (credit/debit card).

Enter your phone number and verify it via SMS/call.

Select a support plan (Basic/other).

Check all the details and click on "Complete Sign Up."

After receiving the confirmation email, your account will be activated.

_____________________________________________________________________________________

Practical 2: Creation of AWS Compute Ubuntu & Windows Instance and Connect it using SSH&RDP Client

Steps to do practical:

Linux instance:

Log in to the AWS Management Console.

Go to the EC2 dashboard.

Create your Ubuntu instance and create a key pair for your instance (demo1.Pem).

Open the Windows Cmd Prompt or Windows Power Shell in the Administrator Mode.

Type the following command like SSH -i "The Location of .Pem file you downloaded ec2-user@type the public address of the instance".

Verify the connection by typing "Yes".

You will get the terminal of Instance in your Command prompt.

Windows instance:
Sign in to the AWS Management Console.

Open the Amazon EC2 console.

Choose Instances.

Choose your Windows Server instance.

Choose Connect -> RDP connection.

Choose Get Password, and then choose Choose File (demo2.pem) and generate one password.

Download the remote desktop file (demo2.rdp).

Open the RDP client, check the Username is administrator and the Password you copied from the previous step.

Choose Connect. You will get the windows screen of your Instance with the EC2 instance information.

Remote Desktop Protocol (RDP):
RDP is the go-to method for connecting to Windows instances.

______________________________________________________________________________________________

Practical 3: Create an S3 bucket and Configure bucket policies, versioning, and encryption. Upload and download objects to/from the S3 bucket.


Steps: 

Create an S3 Bucket and Upload Objects
Open AWS Management Console.
Go to "Services".
Scroll to the bottom and click on "Storage".
Click on "Amazon S3".
Click on "Create bucket".
Enter a unique bucket name, e.g., "simple-devops-demo".
Choose an AWS region, e.g., "Seoul".
Leave other settings as default (Access Control List disabled, block public access enabled).
Click "Create bucket".
Click on your bucket name, e.g., "simple-devops-demo".
Click on "Upload".
Click "Add files" and select the file to upload, e.g., a JPEG image.
Click "Upload".

Create a Bucket Policy

Go to your bucket's "Permissions" tab.
Click "Edit" under "Block Public Access".
Uncheck "Block all public access" and confirm by clicking "Save changes".
Under the "Permissions" tab, click "Edit" next to "Bucket Policy".
Click on "Policy Generator" to create a custom policy.
Set the following parameters:
S3 Bucket Policy
Allow

*s3:GetObject
Enter your bucket's ARN (found under "Bucket ARN" in the console) followed by /*.

Click "Add Statement" and "Generate Policy".Copy the generated JSON policy and paste it into the "Bucket Policy" editor.Click "Save changes".Test and Verify
Navigate to your uploaded object.
Click on the object to view its properties, including the "Object URL".
Open the "Object URL" in a new tab to verify public access.
Ensure the bucket policy allows public access.
Confirm the public access settings in your bucket's permissions.


Optional: Delete Objects and Bucket
Select the object(s) in your bucket.
Click "Delete" and confirm the deletion.
Go back to the S3 console.
Select your bucket.
Click "Delete" and confirm by typing the bucket name.
_____________________________________________________________________________________________________________

Practical 4: Creating an Application using AWS Bean Stalk

1. 'Open the AWS Management Console':
   - Search for Elastic Beanstalk.

2. 'Create Application':
   - Click on "Create Application."
   - Name your application (e.g., "My first EB Website").

3. 'Set Up Environment':
   - Choose "Web server environment."
   - The environment name will be generated automatically.

4. 'Configure Domain (Optional)':
   - You can add a custom domain name or use the default.

5. 'Select Platform':
   - Choose the managed platform for your application (e.g., Node.js).

6. 'Key Pair for SSH Access':
   - Select a key pair for SSH access. If you don't have one, create it in EC2 and refresh the list. (Already created like Demo2.pem)

7. 'Attach Instance Profile':
   - Attach an instance profile with necessary permissions (e.g., S3 read-only). (Already done in Practical 2)

8. 'Choose VPC and Subnets':
   - Select your default VPC and subnets.
   - Assign a public IP address.

9. 'Security Group':
   - Select or create a security group with port 80 open for web access.

10. 'Instance Type':
    - Choose an instance type (e.g., T2 micro). delete the remaining instances

11. 'Health Reporting (Optional)':
    - Enable or disable health reporting based on your preference.

12. 'Platform Updates': Un check it 
    - Decide whether to enable managed platform updates.

13. 'Review and Submit':
    - Review all settings.
    - Click "Submit" to create the application.

14. 'Deployment':
    - Wait for the deployment process to complete.(Min 3 to 5 Mins)
    - Monitor the events to ensure a successful launch.

15. 'Access Your Application':
    - Once deployed, access your application using the provided URL.

16. 'Manage and Monitor':
    - Use the EC2 console to manage instances.
    - Connect via SSH if needed.
    - Monitor service metrics and logs.

_________________________________________________________________________________________________________________________________

Pratical 5: Static Website Hosting using AWS EC2

Steps to follow , as well as check the attachment also for Step by step visual guidance
1. Create an EC2 instance(Amazon Linux)- 
2. Create key pair- Download it.
3. Create a security group(Tick all the available options below)
4. Instance successfully initiated
5.Connect to instance using EC2- Instance Connect
6. Open terminal using SSH.
7.  sudo su – (get root access) in terminal of the instance
8. yum update -y (update the system)
9. yum install httpd -y (install httpd web server)
10. systemctl status httpd (check status of web server)
11. mkdir temp (create temp folder)
12. wget https://www.free-css.com/assets/files/free-css-templates/download/page292/settle.zip (For getting the Website in Zipped form)
13. unzip downloaded website zip folder 
14. cd unzipped-folder-location / ls -lrt (check contents of folder)
15. mv * /var/www/html/ (move website folder to destination folder)16. ls -lrt (checking moved folder)
17. Change inbound rules to allow HTTP and HTTPS traffic from the instance Security Group18. Server has started running…
19. Copy the Public IPv4 address of the instance 
20. add http://the ip address
21. The website will be loaded .

_____________________________________________________________________________

Practical 6: Creation of Instance and EBS volume and attaching with the instance.

Creation of Instance and EBS volume and attaching with the instance.(Follow the Document step by step guide)
Step1: Login into the instance
Step2: Create an Instance (Give a name and Tag name similar to identify the Instance easily)
Step 3:  Change the Settings of the Security Group
Step5: Instance launched( make a note of  your AvailabilityZone:  e.g : ap-south-1b)
Step 6: Creation of Volume in Ec2
Step 7: Important Settings in Volume Creation
        a) Select Volume type: General Purpose SSD(gp2)
        b) Size(GiB): 20
        c) Availability Zone: Should Be the same as your Instance Availability Zone (e.g: ap-south-1b)
        d) In the Tags (Give some names similar to Instance name for identification
Step 8: EBS Created (You can edit the name also eg:ebs attach and mount)
Step 9: Attach the EBS to instance we have created already
Step 10 Settings in attach volume
        a)Select the instance from Drop down box
        b) Select the device status( e.g /dev/sdc) and click the attach volume
        c) Check the status in the Volume dash board
 

Upto this step, we have created the volume(EBS) and attached it in Instance.
Mounting the EBS into the instance new directory:

Now we will see the steps to mount the volume into instance,

Step1: Goto instance Dashboard, click connect.
Step2: after clicking the connect , you will get the terminal access of your instance.
Step 3: Type the command sudo su -(It will give the root/admin access to the instance so that we can install /run some system-level commands)
        After this, the command prompt will be changed like this
        [root@ip-172-31-11-222 ~]#
Step 4: Type the command df –h . This command displays the disk space usage in a human-readable format, useful for checking available storage.
        The system has one volume /dev/xvda1 which is already attached and mounted with the instance.
        But, Our Volume /dev/sdc is not showing up, even though we have created and attached to the instance. To check that ,
Step 5: type lsblk (Lists all the block devices in the Linux Machine: ), Now the attached volume is showing in the name xvdc      202:32   0  20G  0 disk but not added to the device directory structure
Step 6: For that, we need to mount the created volume into the directory structure of the instance, before doing mounting Check if there is any file system on the new EBS Volume:
        Type the command :file -s /dev/xvdc
         If it shows data means, you need to setup the file system for this block device(/dev/xvdc)
        Step 6: Create a file system xfs for the on the new EBS Volume:
        Type the command: mkfs –t /dev/xvdc
Step 7: after creating the file system, we need to create one directory in the instance and attach our device .dev/xvdc to it.
        Type the command for directory creation
        mkdir -p /apps/my-data/apps/volume/new-volume
        Get into the directory
        Type the command: cd  /apps/my-data/apps/volume/new-volume
Step 8:
        To Mount volume to EC2 Instance created directory:
        mount  /dev/xvdc  /apps/my-data/apps/volume/new-volume
Step 9: To check the new EBS volume is mounted into directory of the instance,
        Type the command to check df-h
         
We have successfully created an EBS volume, attached with the instance and mounted it into the instance directory.

After this please delete Volume, and Instance from your AWS Login.

______________________________________________________________________________________________________________________________________________

Practical _7a+7b:- Create a REST API by importing +Creation of REst API with Lambda Function


For 7.a: Create a REST API by importing an example - Amazon API Gateway

Use the Amazon API Gateway console to create and test a simple REST API with HTTP integration for a PetStore website.
After loading the API definition into API Gateway, you can use the API Gateway console to examine the API's basic structure or simply deploy and test the API.
Follow the 15 steps in the given link. You can also create your own API, test it, and deploy it.

For 7.b: Create a REST API with a Lambda proxy integration - Amazon API Gateway

Create a "Hello, World!" Lambda function.
Create a "Hello, World!" API.
Deploy and test the API.
______________________________________________________________________________________________
