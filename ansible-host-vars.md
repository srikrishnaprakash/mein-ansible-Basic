# Welcome Prakash's Basics of ansible host variables ! 
# Here you can get the ansible host variables, brief definition and usage.

**Variable: ansible_host:** The name of the node to connect to <br/>
**Example**<br/>
&emsp;#Inventory file<br/>
&emsp;*mytestnode ansible_host=192.168.177.129*

**Variable ansible_port:** The connection port number, if not the default (22 for ssh) <br/>
**Example**<br/>
&emsp;#Inventory file<br/>
&emsp;*mytestnode ansible_host=192.168.177.129 ansible_port=229*

**Variable: ansible_user** The user name to connect to the host(Linux & Windows) <br/>
**Example**<br/>
&emsp;#Inventory file<br/>
&emsp;*mytestnode ansible_host=192.168.177.129 ansible_port=229 ansible_user=prakash*

**Variable: ansible_ssh_user** The linux user name to connect to the host <br/>
**Example**<br/>
&emsp;#Inventory file<br/>
&emsp;*mytestnode ansible_host=192.168.177.129 ansible_port=229 ansible_ssh_user=prakash*

**Variable: ansible_password** The password of user to authenticate to the host(Windows)  <br/>
**Example**<br/>
&emsp;#Inventory file<br/>
&emsp;*mytestnode ansible_host=192.168.177.129 ansible_port=229 ansible_ssh_user=prakash  ansible_password=myuserP@ss*

**Variable: ansible_ssh_pass** The password of linux user to authenticate to the host  <br/>
**Example**<br/>
&emsp;#Inventory file<br/>
&emsp;*mytestnode ansible_host=192.168.177.129 ansible_port=229 ansible_ssh_user=prakash  ansible_ssh_pass=mySshP@ss*

**Variable: ansible_ssh_private_key_file** Private key file used by ssh to connect using key file to host <br/>
**Example**<br/>
&emsp;#Inventory file<br/>
&emsp;*mytestnode ansible_host=192.168.177.129 ansible_port=229 ansible_ssh_user=prakash  ansible_ssh_private_key_file=/path_to/folder/.ssh/mykey.ppk*

**Variable: ansible_become** Equivalent to ansible_sudo or ansible_su, allows to force privilege escalation <br/>
**Example**<br/>
&emsp;#Inventory file<br/>
&emsp;*mytestnode ansible_host=192.168.177.129 ansible_port=229 ansible_ssh_user=prakash ansible_become=yes*

**Variable: ansible_become_method** Allows to set privilege escalation method valid choices: [ sudo | su | pbrun | pfexec | doas | dzdo | ksu | runas | machinectl ]<br/>
**Example**<br/>
&emsp;#Inventory file<br/>
&emsp;*mytestnode ansible_host=192.168.177.129 ansible_port=229 ansible_ssh_user=prakash ansible_become=yes ansible_become_method=sudo*

**Variable: ansible_become_user** Equivalent to ansible_sudo_user or ansible_su_user, allows to set the user you become through privilege escalation <br/>
**Example**<br/>
&emsp;#Inventory file<br/>
&emsp;mytestnode ansible_host=192.168.177.129 ansible_port=229 ansible_ssh_user=prakash ansible_become=yes ansible_become_method=sudo ansible_become_user=root"

#### Remote host environment parameters:

**Variable: ansible_shell_type**
The shell type of the target system. You should not use this setting unless you have set the ansible_shell_executable to a non-Bourne (sh) compatible shell. By default commands are formatted using sh-style syntax. Setting this to csh or fish will cause commands executed on target systems to follow those shell’s syntax instead.

**Variable: ansible_python_interpreter**
The target host python path. This is useful for systems with more than one Python or not located at /usr/bin/python such as *BSD, or where /usr/bin/python is not a 2.X series Python. We do not use the /usr/bin/env mechanism as that requires the remote user’s path to be set right and also assumes the python executable is named python, where the executable might be named something like python2.6.

**Variable: ansible_*_interpreter**
Works for anything such as ruby or perl and works just like ansible_python_interpreter. This replaces shebang of modules which will run on that host.


**Variable: ansible_shell_executable**
This sets the shell the ansible controller will use on the target machine, overrides executable in ansible.cfg which defaults to /bin/sh. You should really only change it if is not possible to use /bin/sh (in other words, if /bin/sh is not installed on the target machine or cannot be run from sudo.).