# Users and Group Management 
```

Create Users 
Create a User with folder in /home 
$useradd -m narendra 
$ cat /etc/passwd 
$id  // show user details 
whenver you create the user , the linux automatically create the group for you 

Create a User with out folder in /home 
$useradd navishna 

Set the Passwrod for user 
$passwd narendra


Create Groups 
$groupadd prod

Add Users to Group 
$usermod -g prod narendra   // remove the existing primary group  and group and add this group 
$id 
$usermod -G prod narendra  // add the exsting group 
$id 
uid=1001(narendra) gid=1006(prod) groups=1001(narendra),1006(prod)

to Append the group on existing group 
$usermod -aG prod navishna 
```
