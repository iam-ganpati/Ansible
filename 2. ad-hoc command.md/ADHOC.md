## Introduction:

- An Ansible ad hoc command uses the /usr/bin/ansible command-line tool to automate a single task on one or more managed nodes. ad hoc commands are quick and easy, but they are not reusable

***why use ad-hoc command***
- Ad-hoc commands are great for tasks you repeat rarely. For example, if you want to power off all the machines in your lab for Christmas vacation, you could execute a quick one-liner in Ansible without writing a playbook. An ad-hoc command looks like this

***Here are some common use cases for ad-hoc commands:***

- Checking System Information: Ad-hoc commands allow you to gather system information such as disk usage, memory usage, or installed packages across multiple hosts.

```ansible all -a "df -h"```

- Running Commands: You can use ad-hoc commands to execute shell commands or run scripts on remote hosts without writing a dedicated playbook.

```ansible all -a "uname -a"```
  
- Installing Packages: Ad-hoc commands are useful for installing or updating packages on remote hosts using package management utilities like yum or apt.

```ansible all -b -m yum -a "name=httpd state=present"```

- Managing Services: You can start, stop, restart, or check the status of services on remote hosts using ad-hoc commands.

```ansible all -b -m service -a "name=httpd state=restarted"```

- Copying Files: Ad-hoc commands enable you to copy files or directories between local and remote hosts or between remote hosts.
  
```ansible all -m copy -a "src=/path/to/local/file.txt dest=/remote/destination/"```

- Managing Users and Permissions: You can create or delete users, change file permissions, or manage user accounts on remote hosts using ad-hoc commands.

```ansible all -b -m user -a "name=myuser state=present"```
