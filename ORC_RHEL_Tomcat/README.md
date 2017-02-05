Role Name
=========
ORC_RHEL_Tomcat

Role which verifies the Tomcat installation on RHEL.

Requirements
------------

This role is for verifying the installation of Tomcat on RHEL.

Tomcat installation is independent of DataCenter location

Role Variables
--------------

```
my_csv_file - This file used to write the results of ORC
RHEL_Tomcat.tomcat_version - Is used to check the tomcat version
RHEL_Tomcat. http_port - Indicates the port on which Tomcat will run
LOCAL_TOMCAT_PATH - This indicates the path where Tomcat will get installed
host_IP - Indicates the IP of the target node
```

Dependencies
------------

As stated above.  Depends on the variable values and condition.

Example Playbook
----------------

1) Deploy a RHEL server with Tomcat from vRA and selecting your Ansible hub

2) After the role for RHEL Tomcat is executed , then the ORC for Tomcat will run and results will seen in the file /opt/axiom/deployment_library/{{deployed_hostname}}/{{deployed_hostname}}_ORC_results.csv where deployed_hostname is the IP of the target machine selected in vRA.

3) If user wants run the ORC for Tomcat independently from command line follow the below steps 

4) Create a playbook named myplaybook.yml in /etc/ansible with the following:
```
---
- hosts: all
  vars:
     myhostname:               "{{deployed_hostname}}"
     myEnvironment:            "{{deployed_environment}}"
     myDatacenter:             "{{deployed_Datacenter}}"
     my_csv_file:              "/opt/axiom/deployment_library/{{deployed_hostname}}/{{deployed_hostname}}_ORC_results.csv"


  roles:
  - ORC_RHEL_Tomcat
```

4) Create a file named myhosts in /etc/ansible with the following:
```
[orctomcat]
IP address of deployed host
```
5) Run on command line:
```
$ ansible-playbook -i myhosts /etc/ansible/ myplaybook.yml -l orctomcat --user=root --ask-pass --extra-vars deployed_hostname="<IP_addr_target>"
```

License
-------


Author Information
------------------

Robinson Vijaya Panicker ( e3025574 )

