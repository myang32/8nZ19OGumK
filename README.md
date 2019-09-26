# 8nZ19OGumK
This is for testing Assessment of installation Wordpress automatically though AWS cloudformation and ansible playbook

The task is breaking to the following steps:

1. Make sure you setup MFA (required)

2. Generate AWS keypair for your login EC2 instance - prerequisities

3. Use cloudformation file cloudformation-ansible-ec2.yaml, then run from the AWS web portal, which will trigger the following tasks:
   
   A. Setup EC2 instance, along with VPC, Intenet gateway, security group and ansible package installed.
   B. download this git repository https://github.com/myang32/8nZ19OGumK.git, and run playbook to install single instance of wordpress 
      LAMP stack.
      
4. using IP address or AWS DNS name to login and test it out, setup wordpress admin user and password.


Notes:

 The MySQL DB password is hardcoded, which can be implemented by ansible vault or AWS secret manager, but it is out of topic here, please don't use the default password if you want to use it as template.
 
Lesson learn:

1. Do NOT run yum upgrade,  It takes long time for debuging this issue. Since yum upgrade will upgrade your AMI yum package from yum3 to yum4, and ansible is confusing what backend yum using, I hope it can be fixed in the next version of ansible.

2. Getting DB connection error when using the latest 5.2 series of wordpress.tar.gz, due to wordpress changed wpdb to wp_query, which is not documented anywhere, upgrade from 4.8 to newer version is warned.

WordPress admin user password will be sent by email.

