# ansible-playbooks

Repository for common ansible playbooks for server configuration and administration.

# Pre-requisites

This repository uses Ansible to complete the configuration of the servers. You will need to install Ansible on your local machine before you can run the playbooks.

# Host configuration

You should have all of your servers configured in your `~/.ssh/config` file. This will allow you to use the 
hostnames defined in the config file instead of having to type out the IP address and username of each server.

Hosts should be added to a file in the root directory named `hosts` as follows:

```
[all]
<hostname>
<hostname>

[role]
<hostname>

[another_role]
<hostname>
```

Servers can be added to multiple groups by adding them to multiple sections in the file.

# Running playbooks

To run a playbook, you can use the following command:

```
ansible-playbook -i hosts <playbook>.yaml
```

# Writing playbooks

Playbooks should be written as agnostic as possible to allow them to be run on multiple servers.

Hosts should be defined in the `hosts` file as described above and then referenced in the playbook as follows:

```
- hosts: [<group_name>]
```