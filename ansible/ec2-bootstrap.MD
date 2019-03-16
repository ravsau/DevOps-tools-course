Use this to bootstrap Ansible EC2 machines with username , password and sudo priviliges

```bash
#!/bin/bash
# enable password ssh authentication. By default, it's disabled
sed 's/PasswordAuthentication no/PasswordAuthentication yes/' -i /etc/ssh/sshd_config

# restart sshd 
service sshd restart

# add ansible user to the linux system
useradd ansible

# this will set the password for ansible user to be 'ansible123'
echo "password123" | passwd --stdin ansible

# this will give ansible user superuser access without password
echo 'ansible         ALL=(ALL)       NOPASSWD: ALL' >> /etc/sudoers





```
