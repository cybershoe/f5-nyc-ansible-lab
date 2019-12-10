Getting Started
===============

Lab Network Setup
~~~~~~~~~~~~~~~~~

In the interest of focusing as much time as possible configuring and
performing lab tasks, we have provided some resources and basic setup
ahead of time. These are:

-  Cloud-based lab environment complete with Jump Host, Virtual BIG-IP
   and Lab Server

-  Duplicate Lab environments for each student for improved
   collaboration

-  The Virtual BIG-IP has been pre-licensed and provisioned with Local Traffic
   Manager (LTM) and Application Security Manager (ASM)

-  Pre-staged configurations to speed up lab time, reducing repetitive
   tasks to focus on key learning elements.

If you wish to replicate these labs in your environment you will need to
perform these steps accordingly. 

Accessing the Lab
~~~~~~~~~~~~~~~~~

Each student has been provided a Ubuntu-based jumphost, which, in this lab,
also serves as the Ansible host that will be used to run your Ansible
playbooks. You can access this host using your computer's RDP client.

Once you are logged into the jumphost, you will have access to a web browesr
and terminal emulator to access the other systems in the lab. 

If you prefer, you can also connect directly to the jump host and BIG-IP GUI
using your own SSH client and web browser.

Timing for labs
~~~~~~~~~~~~~~~

The time it takes to perform each lab varies and is mostly dependent on
accurately completing steps. This can never be accurately predicted but
we strived to provide an estimate based on several people, each having a
different level of experience. Below is an estimate of how long it will
take for each lab:

+------------------------------------------------------+--------------------+
| **Lab Description**                                  | **Time Allocated** |
+======================================================+====================+
| LAB 1 (Installing Ansible in a Virtualenv)           | 5 minutes          |
+------------------------------------------------------+--------------------+
| LAB 2 (Running the first playbook)                   | 25 minutes         |
+------------------------------------------------------+--------------------+
| LAB 3 (Using tags with Ansible)                      | 25 minutes         |
+------------------------------------------------------+--------------------+
| LAB 4 (Using Variables)                              | 25 minutes         |
+------------------------------------------------------+--------------------+
| LAB 5 (Importing an ASM Policy from an XML Template) | 10 minutes         |
+------------------------------------------------------+--------------------+

Authentication – Credentials
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following credentials will be utilized throughout this Lab guide.

+------------------------------------------+----------------+----------------+
| **Credential Use**                       | **User ID**    | **Password**   |
+==========================================+================+================+
| BIG-IP Configuration Utility (GUI)       | admin          | |bigippass|    |
+------------------------------------------+----------------+----------------+
| BIG-IP CLI Access (SSH)                  | root           | |rootpass|     |
+------------------------------------------+----------------+----------------+
| Jump Host Access                         | |jumpuser|     | |jumppass|     |
+------------------------------------------+----------------+----------------+

