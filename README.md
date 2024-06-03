# Ansible tutorial v1.0
# Created by Dan Koch

1.Make public keys and add them to clients also create public key named ansible for ansible connection. <br />
2.Install Ansible on a server machine ( yum install ansible / sometimes need to ass repolist before like epel ) <br />
3.Create invertory file with ip addresses for your clinets in a ansible folder on your server<br />
4.Test connection form server with ansible command "ansible all --key-file ~/.ssh/ansible -i invertory -m ping<br />
    
Where
-m = Module name
-a = allow parameters
-u = username

Other usefull Ad hoc Commands: <br />
ansbile all --list-hosts <br />
ansible all -m gather_facts <br />
ansible all -m gather_facts --limit 192.168.84.3<br />
ansible 127.0.0.1 -m file -a "dest=/opt/a.txt mode=600 state=touch"<br />
ansible 127.0.0.1 -m file -a "dest=/opt/a.txt mode=600 state=touch"<br />
ansible 127.0.0.1 -m file -a "dest=/opt/a.txt mode=600 state=touch owner=ec2-user"<br />
ansible 127.0.0.1 -m file -a "dest=/opt/b.txt mode=755 state=touch owner=ec2-user"<br />
ansible 127.0.0.1 -m file -a "dest=/opt/c.txt mode=755 state=touch owner=ec2-user"<br />
ansible 127.0.0.1 -m file -a "dest=/opt/bmc.txt mode=755 owner=ec2-user"<br />
ansible localhost -m file -a "dest=/opt/bmcdir mode=755 owner=ec2-user group=ec2-user state=directory"<br />
ansible 127.0.0.1 -m yum -a "name=httpd state=present"<br />
ansible 127.0.0.1 -m yum -a "name=httpd state=absent"<br />
ansible 127.0.0.1 -m service -a "name=httpd state=started"<br />
ansible 127.0.0.1 -m service -a "name=httpd state=stopped"<br />
ansible 127.0.0.1 -m command -a "/bin/yum update -y"<br />
ansible 127.0.0.1 -a "/bin/yum update -y"<br />
ansible 127.0.0.1 -m copy -a "src=/opt/index.html dest=/var/www/html/index.html"<br />
ansible 127.0.0.1 -m setup<br />
# Install Apache<br />
$ ansible webservers -i inventory -m yum -a "name=httpd state=present" --sudo<br />
# Start Apache<br />
$ ansible webservers -i inventory -m service -a "name=httpd enabled=yes state=started" --sudo<br />
# Install MySQL<br />
$ ansible dbservers -i inventory -m yum -a "name=mysql-server state=present" --sudo<br />
# Start MySQL<br />
$ ansible dbservers -i inventory -m service -a "name=mysqld enabled=yes state=started" --sudo<br />
# Stop IPTables on all systems<br />
$ ansible webservers:dbservers -i inventory -m service -a "name=iptables enabled=no state=stopped" --sudo<br />
$ ansible servers -a "/sbin/reboot" <br />
$ ansible all -m user -a "name=foo password="<br />
$ ansible webservers -m git -a "repo=https://foo.example.org/repo.git dest=/srv/myapp version=HEAD"<br />
$ ansible all -m user -a "name=foo state=absent"<br />

new line of text
