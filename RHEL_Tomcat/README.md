Role Name
=========


Ansible role for Tomcat app server Installation on a managed VM in Converged Infrastructure (CI)

Requirements
------------

RHEL_Tomcat role triggred based on user selection in vRA. If user select Tomcat check box then Tomcat get installed on the deployed Linux VM. Otherwise Tomcat installation simply ignored.

Please make sure the Tomcat checkbox available in vRA Linux request form.


Role Variables
--------------

 
 
Dependencies
------------



Example Playbook
----------------

Including an example of how to use this role (for instance, with variable passed in as parameters) is always nice for users too:

```yaml
    ---
    - hosts: managed_node
      pre_tasts:
      ........
      roles:
        - RHEL_Deploy_Tomcat
      post_tasks:
      ........
```

Where vars/main.yml contains:
```yaml
   ---


Todo
----
- 

Author Information
------------------

RHEL_Deploy_Tomcat was written by:

Mohan Lakshmanan [Mohan.Lakshmanan@fisglobal.com]

