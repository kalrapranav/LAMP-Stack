# LAMP Stack
## How to host Multiple Websites on one linux server in CentOS 7 / Redhat 7 / Fedora
Check the static Ip address of the remote server.   
For our deivce runnin iver CentOS the following command can be used:   
> user@user: ip addr show   

Install Apache or httpd server   
> user@user: sudo yum install httpd

Go to the config folder
> user@user: sudo cd /etc/httpd/conf.d/  

Create a config file
> user@user: sudo emacs thermofluids.conf  

Inside the file write the following script  


```
<virtualhost *:80>  
servername www.thermofluids.com  
serveradmin sooby@130.191.161.117  
documentroot /var/www/html  
</virtualhost>  
```

Cretate a host file 
> user@user: sudo emacs /etc/hosts  

In the host file write your domain name and the specified Ip address in the last line  
> 130.191.161.117  www.thermofluids.com

Quit out of the file using Ctrl-X > Ctrl-C > Y command  

Go to the document root. It is the directory in remote server wehere all the website files will be dumped. 
> sudo cd /var/www/html  

If not dumping files, create a new html file
> sudo emacs index.html 

```<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>Testing Site</title>
  </head>
  <body>
    This is a testing Site
  </body>
</html>
```
Now start and enable the appache server 
> user@user: sudo systemctl start httpd  
> user@user: sudo systemctl enable httpd    

Cretae a firewall: 
> user@user: firewall-cmd --permanent --add-service=http

Now website can be viewed in any of the browser by typing the server name

Now in order to trsnsfer the  file from yout local machine to your ssh server use the following command:
> scp /home/kalra/Desktop/web/* sooby@IP-address:.

