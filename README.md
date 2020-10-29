# ansible

Building and running the ansible container
```
git clone https://github.com/sedillo/ansible.git
cd ansible
docker build -t ansible-base .
mkdir targets
alias ansible-docker="docker run --rm -it -v $(pwd):/ansible/mount -v ~/.ssh/:/root/.ssh ansible-base"
```
Ansible Commands
```
#To enter the container
ansible-docker 

#Ansible version
ansible-docker ansible --version

#Ansible hosts
ansible-docker ansible all --list-hosts

#Get target info, save it, then open overview.html in web browser
ansible-docker ansible all -m setup --tree ./mount/targets/
ansible-docker ansible-cmdb ./mount/targets/ > overview.html
```
