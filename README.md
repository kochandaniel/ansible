# Ansible tutorial

1.Make public keys and add them to clients also create public key named ansible for ansible connection. <br />
2.Install Ansible on a server machine ( yum install ansible / sometimes need to ass repolist before like epel ) <br />
3.Create invertory file with ip adresses for your clinets in a ansible folder on your server<br />
4.Test connection form server with ansible command "ansible all --key-file ~/.ssh/ansible -i invertory -m ping<br />
    
other usefull commands: <br />
ansbile all --list-hosts <br />
ansible all -m gather_facts <br />
ansible all -m agther_facts --limit 192.168.84.3<br />


