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
remove users from group 
$gpasswd -d narendra prod 
$cat /etc/passwd 
$cat /etc/group

usermod -aG dev,prod,marketing,tech_team tom

getent group dev  - getent means get entries. It is a Linux command used to retrieve information from system databases such as:
getent group dev = Look up the Linux group called dev and show its details.
```

``` text

While Creating the user using interact mode  , we need to enter all details, we should provide all details like password , name , mobile 

$adduser narendra
delete the user but not delete the home directory 
$userdel narendra
delete the user completly like home directory
$userdel -r navishna
delete the group
$groupdel narendra
$ls 


```

<img width="1190" height="184" alt="image" src="https://github.com/user-attachments/assets/1b507298-907b-4ec6-9daa-a0274d8c0d36" />
<img width="1350" height="666" alt="image" src="https://github.com/user-attachments/assets/ee60a708-c8c1-4080-8486-667567071b58" />

<img width="989" height="106" alt="image" src="https://github.com/user-attachments/assets/40e5f495-cb58-45ba-bde7-daf4d2df7056" />

root = User             , root =Group 
we need to change the user of the file and group of the file 
$chown narendra healthcheck.py 
change the group name 
$chown narendra:prod healthcheck.py 

$groupadd marketing 
$chown :marketing healthcheck.py 
Chnage the directory owner files 
$mkdir folder1 
$cd folder1 
$touch file1.txt 
$touch file2.txt 
chnage the ownership of folder and files 
$chown -R narendra:prod folder1 
