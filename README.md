ansible-sakura
==============

Ansible playbook for SakuraServer VPS


##Usage
$ user_password=$(openssl passwd -salt salty -1 \<user password\>)  
$ ansible-playbook -k -c paramiko -i hosts sakura_root.yml -vv --extra-vars "user_password=$user_password"  
  
$ ssh-keygen  
$ ssh-copy-id -i ~/.ssh/sakura_rsa.pub "-p 10022 admin@\<SakuraServer ip address\>"  
$ cat \<\<EOF \>\> ~/.ssh/config  
Host sakura  
  Hostname \<SakuraServer ip address\>  
  Port 10022  
  User admin  
  IdentityFile ~/.ssh/sakura_rsa  
EOF  
  
$ ansible-playbook sakura_lamp.yml -i hosts -vv  

##See detail
akiyoko blog  
http://akiyoko.hatenablog.jp/entry/2013/12/16/020529
