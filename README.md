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
> <virtualhost *:80>  
> servername www.thermofluids.com  
> serveradmin sooby@130.191.161.117  
> documentroot /var/www/html  
> </virtualhost>  

aljmd
