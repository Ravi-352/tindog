# Deploying 'tindog' in AWS EC2 Instance using httpd

Create AWS EC2 instance:
![image](https://github.com/Ravi-352/tindog/assets/91112573/4c48ff0b-1f7a-4aaf-b893-f7f8b8017114)
![image](https://github.com/Ravi-352/tindog/assets/91112573/5d17ef8a-8c9b-4902-92c7-f51d07bdaad8)

In EC2 Dashboard, click on Instances
![image](https://github.com/Ravi-352/tindog/assets/91112573/059c6fc1-4b0d-4761-9806-cfbff54837f9)

Click on Launch Instances
![image](https://github.com/Ravi-352/tindog/assets/91112573/a6021e39-046b-4ee1-91be-0fdab45af29f)

Provide Necessary Details: Name, OS Image, Instance Type
![image](https://github.com/Ravi-352/tindog/assets/91112573/825c2288-c61b-4997-8efc-93c1366a7942)

![image](https://github.com/Ravi-352/tindog/assets/91112573/9ea32e59-e37a-4289-ba70-bd9541e6fc03)

![image](https://github.com/Ravi-352/tindog/assets/91112573/8fd34c5b-81a6-43cd-8f77-e530be7d8349)

In order for us to access the EC2 instance from our local system (laptop), we need key pair. So create it and save the file in the local machine safely.
![image](https://github.com/Ravi-352/tindog/assets/91112573/d641a3e2-b604-46f6-a12e-45f3b5fa162d)

Setting the Network Settings: For current Demo purpose, all SSH, HTTP and HTTPS traffic being allowed:
![image](https://github.com/Ravi-352/tindog/assets/91112573/0745d6ce-1da5-4af3-b489-eb67327b1b5c)

Configure Storage: set 10GiB general purpose 2 (gp2) in root volume - EBS storage (Elastic Block Storage)

Advanced Details: Like Purchasing options, Domain Join Directory, IAM profile etc. 
  To keep the things simple to understand in the Demo for beginners, lets not touch this.

Launch The instance:
![image](https://github.com/Ravi-352/tindog/assets/91112573/f5d7fcd5-e255-441c-b92b-ef79bb03ce82)

Click on the instance id:
![image](https://github.com/Ravi-352/tindog/assets/91112573/af12fae7-6d29-4d24-a013-1f9a6e7bb4d4)

![image](https://github.com/Ravi-352/tindog/assets/91112573/65cf34c3-f48c-44ea-bff8-8dec111057cd)

We can notice that instance is created and running successfully.

Now we want to connect to the instance from our Local Laptop.
![image](https://github.com/Ravi-352/tindog/assets/91112573/84531656-9fce-496a-b482-992ece4f2429)

  Implement the below steps exactly from an secure shell (ssh) like MobaXterm/Putty - 
  	
  ![image](https://github.com/Ravi-352/tindog/assets/91112573/a35a9fc8-f315-4490-817f-2a30c9fd8038)

  ![image](https://github.com/Ravi-352/tindog/assets/91112573/9498a6a9-ae5d-4f64-bdfd-f82cc243f8fd)

Update OS and install packages - git, httpd

Commands:

sudo su - # switching to root user
yum update -y #updating the OS and related packages

It will take some time based on connectivity and internet speed

Now install git, clone/fork this repo and httpd

Commands:
yum install git -y
git clone https://github.com/Ravi-352/tindog.git
yum install httpd -y

![image](https://github.com/Ravi-352/tindog/assets/91112573/31d97d45-9538-413a-89fd-25fcd17b2b42)

![image](https://github.com/Ravi-352/tindog/assets/91112573/0097d94a-b5f4-4476-88e9-32dd2236e301)

Change the directory to "tindog" repo and Copy all the files in "tindog" folder to /var/www/html: 
cd tindog
cp * /var/www/html

![image](https://github.com/Ravi-352/tindog/assets/91112573/46058520-d768-4347-bbc6-8c2187f9daac)

![image](https://github.com/Ravi-352/tindog/assets/91112573/90f48711-99c3-46d3-82ac-494c2bbac2ef)

Start the httpd instance and try accessing the webpage using public IP address (refer to AWS EC2 intance console)

![image](https://github.com/Ravi-352/tindog/assets/91112573/a528acbc-f8a0-4b47-af3d-ce5052e5e6c8)

![image](https://github.com/Ravi-352/tindog/assets/91112573/0595e703-a475-4dea-bdac-764dae75abcc)



















