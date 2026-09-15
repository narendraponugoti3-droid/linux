# Package Managers 
Linux Packages 
.DEB ==> ubuntu , Debian , Linux mint 
.RPM ==> RHEK, CENTOS ,Fedora 

USER ----> Package Manager ---> Repository <--->Meta Data 
                                   |
                                   Packages and dependencies 

apt ==> Adv packaged tool ===> ubuntu, Debian 
yum ==> Yellowdog Updater Modified ==> centos ,RHEL 
$apt update 
$apt install tree 
$apt install apache2 -y
$apt install nginx -y 
$systemctl status apache2 
automatically start your services 
$systemctl enable apache2 
verify the version of apache2 
$apache2 -v 
available packages 
$apt list -a apache2 

to upgrade installed packages 
$apt upgrade -y
Only upgrade apache2 
$apt install apache2  --only-upgrade -y
to hold the application 

$apt-mark hold nginx 
to see the hold softwares 
$apt-mark showhold 
to unhold application 
$apt-mark unhold nginx 

to uninstall the application without removes the dependencies 

$apt remove apache2 -y 
to remove the dependecies 
$apt purge apache2 -y 
$apt automremove -y 

$apt full-upgrade -y 

