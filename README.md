<h1>Creating Docker Image</h1>

<h2>Description</h2>
In this project I demonstrate how I installed Docker engine on an EC2 instance and use it to create a Docker image.
<br />


<h2>Services Used</h2>

- <b>EC2</b>

<h2>Environments Used </h2>

- <b>AWS</b>
- <b>Docker</b>

<h2>YouTube Demonstration </h2>

[Creating Docker image - video walk-through guide](https://youtu.be/YXjbYLgB4iA)

<h2>Program walk-through:</h2>
<H3>Step 1 - Creating EC2 instance</H3>
Once I logged into my AWS account, I clicked on services and navigated to EC2. From there I entered the name of the EC2 instance and select Amazon Linux. I left remaining settings as defualt and clicked launch instance.

<img src="https://i.imgur.com/fdVAGzB.png" height="80%" width="80%" alt="Image 1"/>


<H3>Step 2 – Connecting to EC2 instance </H3>
Once the EC2 instance was in a running state I connected to it, by right clicking and selecting connect.

<img src="https://i.imgur.com/kaoMGqH.png" height="80%" width="80%" alt="Image 2"/>

<img src="https://i.imgur.com/3BtIoNb.png" height="80%" width="80%" alt="Image 3"/>


<H3>Step 3 –  Install Docker Engine on EC2 Instance</H3>
The Docker engine is the thing that allows Docker containers to run on this EC2 instance, this means I would need to install the Docker engine package.

This is the first command I had to enter:
 
 <b>- sudo amazon-linux-extras install docker</b>

<img src="https://i.imgur.com/EUkJJZz.png" height="80%" width="80%" alt="Image 4"/>

Once Docker engine had been installed I had to start the service.

The command for this is:
  **- sudo service docker start**

Now I need to test that I can interact with the Docker engine.
This is the command to use:
**   - sudo usermod -a -G docker ec2-user
   - sudo su - ec2-user
   - docker ps**

<img src="https://i.imgur.com/7G4XhKD.png" height="80%" width="80%" alt="Image 5"/>

This is the web application which I have configured to be automatically downloaded to this EC2 instance. Its a simple web page which consist of index.html and a few images and a Docker file.
The Docker file is the thing that the Docker engine will use to create the Docker image.

<H3>Step 4 –  Creating the Docker image</H3>

This command create the docker image:
  ** - docker build -t containerofcats .**

<img src="https://i.imgur.com/343TSQ6.png" height="80%" width="80%" alt="Image 6"/>

This command show a list of images on the EC2 instance  but its filtered based on the name containerofcats.
 **- docker images --filter reference=containerofcats**

<img src="https://i.imgur.com/9T1Voz0.png" height="80%" width="80%" alt="Image 6"/>

The final step is to use the Docker run command which is going to take the image that I have just created and use it to create a running container, and its that container that I will be able to interact with.
This is the command I used:
   -** docker run -t -i -p 80:80 containerofcats**

Docker is going to take the Docker image that I have on the EC2 instance run it to create a running container, and I should be able to interact with that container via the public ip address.




</p>
</p>
