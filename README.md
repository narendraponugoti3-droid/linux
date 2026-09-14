# linux
$sudo su // going to current user home directory 
$pwd 
$sudo su - // going to root user 
$cd 
$ls 
$cd /   ==> 
$cd ~   going to user home directory 
absulete path : cd /var/wwww/html
relative path : cd var/, cd www/ , cd html

$ls 
$ls -l 
hidden files 
$ls -la 
sort by time
$ls -lt 
sort by size 
$ls -lS 

$ls --help 
Create a file 
$touch index.html 
$cat index.html                  // open file read-only file 
adding contenxt to index.html 
$echo "This is my index file ">index.html 
$echo "This is my second file ">index.html 
> remove the existing content and then add another content 
$echo " This is my 3rd Content ">>index.html 
>> apend the content 
$vi index.html 
$cat -n index.html
$cat -E index.html 
$cat --help 
$grep index index.html 
$grep command index.html 
$grep -i command index.html 
$grep -c command index.html 
$grep -ic command index.html 
create directory 
$mkdir page1 
$mkdir page1 page2 page3 
parent directory 
$mkdir -p f1/f2/f3 
$mkdir -v f5 
remove file 
$rm index.html 
remove directory 
$rmdir page1 // remove only empty folder 
$rmdir -p f1/f2/f3/f4
$rmdir -r page4  // remove folder with content 
$rmdir -rf page4 

$du --disk usage 
$du -h 
$du -sh /var/log
$du -sh auth.log
