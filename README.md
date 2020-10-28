# ansible

Building and running the ansible container
```
git clone https://github.com/sedillo/ansible.git
cd ansible
docker build -t ansible-base .
mkdir out
docker run --rm -it -v $(pwd)/out:/ansible/out ansible-base
```
While inside the container
```
ansible -m setup --tree out/ all
ansible-cmdb out/ > overview.html
```
