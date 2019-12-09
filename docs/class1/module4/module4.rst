Lab 4: Using Variables
======================

One of the more powerful features of Ansible is its ability to use variables
to separate infrastructure description from implementation, allowing you to
re-use code more easily. Ansible has a robust variable precendence system that
can be used to define global, host-specific, or run-time parameters. More 
information is available from the `Ansible Docs section on variables`_.

Objective:

-  Use variables to simplify the main playbook

Lab Requirements:

-  SSH or Terminal access to the Ubuntu Jumpbox/Ansible Host

-  Access to the BIG-IP TMUI (Web GUI)

Estimated completion time: 10 minutes

TASK 1 - Delete the virtual server
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1. In the BIG-IP web GUI, from the left-hand navigation menu, navigate to 
**Local Traffic** -> **Virtual Servers**

2. Select the *web_vip* virtual server, and click **Delete...**

  |image4|

3. On the following screen, click **Delete** again to confirm.

.. NOTE:: The Virtual Server list should now be empty


TASK 2 ‑ Re-run the playbook with a specific tag
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1.	From the SSH or terminal session, re-run the playbook with the "virtual" 
tag:

  .. code-block:: bash

    $ ansible-playbook -i inventory/hosts first.yaml --tags virtual

Watch the output from the *ansible-playbook* command... do you see all of the
same lines that you did in the last lab?

2.	Back in the BIG-IP GUI, refresh the Virtual Servers list.

TASK 3 - Remove the configuration from the first playbook
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1. From the SSH or terminal session, examine the firstdel.yaml playbook:

  .. code-block:: bash

    $ less firstdel.yaml

.. NOTE:: You'll notice two main differences between this playbook and the 
  *first.yaml* playbook. First, you'll see that each task includes the 
  :code:`state: absent` parameter. This tells Ansible to remove the object
  defined in the task rather that create it. You'll also notice that the tasks
  are in the opposite order from the first playbook. This is because Ansible
  executes tasks in order, and it is necessary to delete objects in the correct
  order, i.e.: you cannot delete a pool if a virtual server is using it.

2. Execute the firstdel.yaml playbook:

  .. code-block:: bash

    $ ansible-playbook -i inventory/hosts firstdel.yaml

4. Back in the BIG-IP GUI, go back to the **Virtual Servers**, **Pools**, and
**Nodes** screens, and confirm that the configuration has been deleted.

.. NOTE:: Keep your SSH or terminal session open for the next lab.

.. |image4| image:: /_static/class1/image4.png

.. _Ansible Docs section on variables: https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html