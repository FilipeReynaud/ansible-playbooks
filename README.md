# ansible-playbooks

## Ansible installation

1. Install python3

```
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update
sudo apt install python3.8
```

2. Install pip3

```
sudo apt-get install python3-pip
```

3. Install Ansible and check its version

```
sudo pip3 install ansible
ansible -version
```

[Sample output]

```ansible 2.10.5
config file = None
configured module search path = ['/home/
ubuntu/.ansible/plugins/modules', '/usr/share/ansible/
plugins/modules']
ansible python module location = /home/ubuntu/.local/
lib/python3.8/site-packages/ansible
executable location = /usr/local/bin/ansible
python version = 3.8.5 (default, Jul 28 2020, 12:59:40)
[GCC 9.3.0]
```

## Create an inventory

1. Create an inventory file with:

```
touch inventory
```

2. Copy the following example:

```
[example]
192.168.60.5
```

## Run Ansible ad-hoc commands

### Using ansible modules

```
ansible -i inventory example -m ping -u ubuntu
```

## Run Ansible alongside with Vagrant

### Vagrant installation

### SSH to a Vagrant VM

## Run playbooks

```
sudo ansible-playbook -b --private-key $HOME/.ssh/<PRIVATE_KEY> playbook.yml
```
