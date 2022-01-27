# Project 1

**- Step 1** Installing apache and Updating firewall

*The below cmdlet updates a list of packages in package manager*

> $ sudo apt-get update
<img width="960" alt="sudo apt-get update" src="https://user-images.githubusercontent.com/98477745/151252295-19f33dd1-3dcc-42cd-a3ae-aed56f7eef8c.png">

*The below cmdlet runs apache2 package installation*

> sudo apt-get install apache2

 <img width="960" alt="sudo apt-get install apache2" src="https://user-images.githubusercontent.com/98477745/151252868-d0dc2906-a8ce-4dba-b97a-7fcb3d0bdacc.png">

*This below cmdlet verifies that apache2 is running as a service in my server*

> sudo systemctl status apache2

<img width="960" alt="sudo systemctl status apache " src="https://user-images.githubusercontent.com/98477745/151253959-a2c6ff12-0132-4f2f-a80d-169dc2e53ad4.png">

*I added a rule to EC2 configuration to open inbound connection through port 80*


<img width="954" alt="Screenshot 2022-01-26 220946" src="https://user-images.githubusercontent.com/98477745/151256104-86126874-2d20-49b8-9de8-589aaff80fd3.png">

*output to check if we can access the apache2 locally*

<img width="951" alt="Screenshot 2022-01-26 231705" src="https://user-images.githubusercontent.com/98477745/151263569-a66337b5-5670-4023-8f33-1a55f8b7ec81.png">

*Test that apache server is running over the browser, generated my ip address using cmdlet*
> ip a

*pasted the ip in a broswer*
<img width="960" alt="Screenshot 2022-01-26 233906" src="https://user-images.githubusercontent.com/98477745/151265244-2c4fcd2f-d6b5-4c01-9ffd-6c094ea19ea7.png">

**- Step 2** Installing mysql

*Used the below cmdlet to install Mysql in the server*

>$ sudo apt install mysql_server

<img width="960" alt="Screenshot 2022-01-27 002500" src="https://user-images.githubusercontent.com/98477745/151272547-d586f0fd-df8a-491e-a842-e1af31cf2f32.png">

*The below cmdlet runs a security script which removes some insecure default settings and lock down access to the data base system*

>sudo mysql secure_installation


<img width="960" alt="Screenshot 2022-01-27 002753" src="https://user-images.githubusercontent.com/98477745/151273306-231dc815-3740-43f8-b283-6130bd523064.png">

*The below code test if are we able to login into Mysql server*

>$ sudo mysql

<img width="960" alt="test if we are able to login to mysql console" src="https://user-images.githubusercontent.com/98477745/151273568-61dbe8f0-481b-4c27-b100-f798ff03ef4b.png">

*Step 3* Installing PHP
*The below cmdlet installs php, libapache2-m0d-php and php-mysql*

> $ sudo apt install php libapache2-mod-php php-mysql

<img width="960" alt="php install" src="https://user-images.githubusercontent.com/98477745/151279744-f4458e48-d5f3-465e-9bb5-832a9bb76276.png">

*The below cmdlet confirms the version of the php*

> $ php -v

<img width="960" alt="confirm php" src="https://user-images.githubusercontent.com/98477745/151279919-8b46c4e4-692e-4fdd-8e6e-b33755e6b1d6.png">


