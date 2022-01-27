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

**LAMP stack has been installed completely ands it is in operation**

**- Step 4** Creating a Virtual Host for your website using Apache2

Created a directory for projectlamp using 'mkdir' command

> $ sudo mkdir /var/www/projectlamp

Assigned ownership to the directory with this variable $USER which still referenced the system user

> $ sudo chown -R $USER:$USER /var/www/projectlamp

Created and opened a new configuration file in Apache's sites-available directory using ''vi'' command line editor

> $ sudo vi /etc/apache2/sites-available/projectlamp.conf



<img width="960" alt="Screenshot 2022-01-27 030211" src="https://user-images.githubusercontent.com/98477745/151291256-3a986cde-b439-4d1b-947a-eb258ee28f57.png">

The below bare-bones configuration by hitting on i on the keyboard to enter the insert mode, and the text:
  
  <VirtualHost *:80>
    ServerName projectlamp
    ServerAlias www.projectlamp 
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/projectlamp
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

**To save and close the file, simply follow the steps below:**

    Hit the esc button on the keyboard
    Type :
    Type wq. w for write and q for quit
    Hit ENTER to save the file
    
Used the below cmdlet to show the new file we created in the sites-available directory

> $ sudo ls /etc/apache2/sites-available

<img width="959" alt="Screenshot 2022-01-27 034740" src="https://user-images.githubusercontent.com/98477745/151291642-fc5ae431-21fe-4739-a962-9d048e2b0ecd.png">

Enabled the new virtualhost created with the below

> $ sudo a2ensite projectlamp



<img width="960" alt="enabled the virtual host created below" src="https://user-images.githubusercontent.com/98477745/151292018-3dca6fa5-7647-45f4-925d-177ce5bb1098.png">

Disabled the default website that comes installed with Apache with the below

> $ sudo a2dissite 000-default


<img width="940" alt="disable the default website that comes with apache" src="https://user-images.githubusercontent.com/98477745/151292043-d6654134-8030-41ab-8288-0216b219bee6.png">



