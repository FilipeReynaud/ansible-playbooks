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
ansible --version
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

For more information regarding the installation of Vagrant, check the [official documentation](https://developer.hashicorp.com/vagrant/downloads).

### Start Vagrant VM

Go to the `tests` folder and run the following command: `vagrant up`. This will start the VM created for test purposes.

### SSH to the test Vagrant VM

To ssh to the test VM, go to the `tests` folder and run the following command: `vagrant ssh test_sandbox`.

### Configure the test Vagrant VM

In the `tests/roles` folder, you'll see a test role to configure our test VM (`test_sandbox`). To execute that role, follow the steps below:

1. Change to tests directory: `cd tests`.
2. Start VM: `vagrant up`.
3. Run the playbook: `ansible-playbook playbook.yml`.

## Run playbooks

```
sudo ansible-playbook -b --private-key $HOME/.ssh/<PRIVATE_KEY> playbook.yml
```
