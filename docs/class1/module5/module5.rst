Lab 5: Importing an ASM Policy from an XML Template
===================================================

Overview
~~~~~~~~

Managing the lifecycle of your security policies is as important as managing
the lifecycle of your code. Storing your security policies as code makes it
possible to programmatically stand up an ASM policy, making it easier to
automatically test and provision your WAF in an automated environment. In this
lab, we will use other F5 Ansible modules to manage ASM security policies.

Objective
---------

-  Use Ansible to import an ASM policy.

Lab Requirements
----------------

-  SSH or Terminal access to the Ubuntu Jumpbox/Ansible Host

-  Access to the BIG-IP TMUI (Web GUI)

Estimated completion time: 10 minutes

TASK 1 - Examine the current ASM configuration
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1. In the BIG-IP web GUI, from the left-hand navigation menu, navigate to 
**Security** -> **Application Security** -> **Security Policies** -> 
**Policies List**

  |image5|

.. NOTE:: The security policies list should be empty

TASK 2 ‑ Examine the third playbook and WAF policy
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1.	From the SSH or terminal session, change into the demo3 folder
and list the contents:

  .. code-block:: bash

    $ cd ~/demo3
    $ ls

2. Examine the variable file and playbook:

  .. code-block:: bash

    $ less third.yaml
    $ less owa_asmtemplate.xml
  
  .. NOTE:: The *owa_asmtemplate.xml* file is an example of a WAF policy. This
    particular policy is pre-built for OWA 2010, but you can export any ASM
    policy into an XML file. Once you've built a baseline policy for an app, 
    you can easily export and re-import that policy. For example, you could
    check the XML file into git along with the application code, and use
    Ansible to quickly deploy that policy in your dev or test environment to
    validate the policy against new code versions.

TASK 3: Import the ASM policy with Ansible
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1.	From the SSH or terminal session, run the third playbook

  .. code-block:: bash

    $ ansible-playbook -i inventory/hosts third.yaml

2.	Back in the BIG-IP GUI, refresh the security policies list.

.. |image5| image:: /_static/class1/image5.png
