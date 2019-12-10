Lab 4: Using Variables
======================

Overview
~~~~~~~~

One of the more powerful features of Ansible is its ability to use variables
to separate infrastructure description from implementation, allowing you to
re-use code more easily. Ansible has a robust variable precendence system that
can be used to define global, host-specific, or run-time parameters. More 
information is available from the `Ansible Docs section on variables`_.

Objective
---------

-  Use variables to simplify the main playbook

Lab Requirements
----------------

-  SSH or Terminal access to the Ubuntu Jumpbox/Ansible Host

-  Access to the BIG-IP TMUI (Web GUI)

Estimated completion time: 10 minutes

TASK 1 - Review the playbook and variable files
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1.	From the SSH or terminal session, change into the demo2 folder
and list the contents:

  .. code-block:: bash

    $ cd ~/demo2
    $ ls


2. Examine the variable file and playbook:

  .. code-block:: bash

    $ less netvar.yaml
    $ less second.yaml

  .. NOTE:: In this lab, the *netvar.yaml* file contains the information needed
    to configure multiple services, while the *second.yaml* playbook contains the
    steps to implement the configured in the variables file. This allows you to
    maintain the configuration without modifying the main playbook.

  .. NOTE:: You'll also notice that the tasks in this playbook include a 
    "with_dict" parameter. This is an example of a loop, and in this case it
    allows the playbook to run the same task multiple times, iterating over
    elements of a YAML dictionary (key-value array), again simplifying the main
    playbook and reducing the amount of code that needs to be duplicated. More 
    information on loop structures can be found in the `Ansible Docs section on
    loops`_.

TASK 2 - Run the second playbook
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1. Run the second playbook:

  .. code-block:: bash

    $ ansible-playbook -i inventory/hosts second.yaml

2. Return to the BIG-IP GUI and review the objects that have been created.

TASK 3 ‑ Remove the configuration from the second playbook
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
1. From the SSH or terminal session, execute the seconddel.yaml playbook:

  .. code-block:: bash

    $ ansible-playbook -i inventory/hosts seconddel.yaml

2. From the BIG-IP GUI, confirm that the configuration has been deleted.

.. NOTE:: Keep your SSH or terminal session open for the next lab.

.. _Ansible Docs section on variables: https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html
.. _Ansible Docs section on loops: https://docs.ansible.com/ansible/latest/user_guide/playbooks_loops.html