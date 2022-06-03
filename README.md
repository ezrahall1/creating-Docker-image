<h1>Creating Docker Image</h1>

<h2>Description</h2>
This project I install the docker engine on an EC2 Instance and use this to create the image.
<br />


<h2>Services Used</h2>

- <b>EC2</b> 
- 
<h2>Environments Used </h2>

- <b>AWS</b>
- <b>Docker</b>


<h2>Program walk-through:</h2>
<H3>Step 1 - Creating EC2 instance</H3>
Once you have log into the AWS account you would need to click on services and navigate to EC2. Enter the name of the EC2 select Amazon Linux, make sure the Amazon Machine Image (AMI) says free tier eligible.
For the instance type make sure you select free tier eligible or you would be charged. Leave the rest as default and click launch instance.

<img src="https://i.imgur.com/fdVAGzB.png" height="80%" width="80%" alt="Image 1"/>


<H3>Step 2 – Connecting to EC2 instance </H3>
Once the EC2 instance is in a running state you would need to connect to it. Right click and select connect.

<img src="https://i.imgur.com/kaoMGqH.png" height="80%" width="80%" alt="Image 2"/>

Select session manager and click coonect

<img src="https://i.imgur.com/3BtIoNb.png" height="80%" width="80%" alt="Image 3"/>


<H3>Step 3 –  Install Docker Engine on EC2 Instance</H3>
The Docker engine is the thing that allows Docker containers to run on this EC2 instance, so you would need to install the Docker engine package.

This is the first command you would need to enter:
 - sudo amazon-linux-extras install docker

<img src="https://i.imgur.com/EUkJJZz.png" height="80%" width="80%" alt="Image 4"/>

Once Docker engine has been installed you would need to start the service.

The command for this is:
  - sudo service docker start

Now you need to test that you can interact with the Docker engine.
This is the command to use:
   - sudo usermod -a -G docker ec2-user
   - sudo su - ec2-user
   - docker ps

<img src="https://i.imgur.com/7G4XhKD.png" height="80%" width="80%" alt="Image 6"/>

</p>
</p>
