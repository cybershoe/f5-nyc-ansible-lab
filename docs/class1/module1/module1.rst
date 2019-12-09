Lab 1: Installing Ansible in a Virtualenv
=====================================

F5 Recommends installing ansible on a python virtual environment (virtualenv). 
This is also a recommended way to use ansible within the ansible opensource 
community. 

*virtualenv* creates isolated Python environments to avoid problems caused by 
conflicting dependencies and differing versions. *virtualenv* works by simply 
creating a folder which contains all of the necessary executables and 
dependencies for a specific version of Python.


Objective:

-  Understand how to install *python-virtualenv* in Debian/Ubuntu Linux

-  Create a virtual environment in which to run Ansible

Lab Requirements:

-  SSH or Terminal access to the Ubuntu Jumpbox/Ansible Host

Estimated completion time: 5 minutes

TASK 1 ‑ Install the *python-virtualenv* package
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1.	Open an SSH session or Terminal window to the Ubuntu host

2.	Run the following command to install the *python-virtualenv* package:

  .. code-block:: bash

    $ sudo apt install python-virtualenv

.. NOTE:: You will be prompted for a password. Use the same password you
  used to log into the jumphost

.. NOTE:: In the lab environment, this package is already installed. Unless
  there has been a new version released since the lab was built, you should
  receive a message that the package is already at the newest version.

TASK 2 - Create the virtual environment
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1. Run the following command to create the new virutal environment:

  .. code-block:: bash

    $ virtualenv myansible

2. Run the following command to begin working in the virtual environment:

  .. code-block:: bash

    $ source myansible/bin/activate

.. NOTE:: Take a look at your command prompt: You'll see that it now shows
  the name of the active virtual environment. Any future python commands that
  change your environment (e.g.: instaling a package with *pip install*) will 
  take effect within this environment, and won't affect the system as a whole.

  |image1|

Task 3: Installing Ansible
~~~~~~~~~~~~~~~~~~~~~~~~~~

*pip* is a package manager for Python. We will be using it to install the
Ansible packages into our virtual environment

1. Run the following command to install Ansible via pip:

  .. code-block:: bash

    $ pip install ansible

.. NOTE:: Keep an eye on the console output. You can see that all of the
  dependencies for Ansible are installed for you automatically.

2. Check the installed version of Ansible with the following command:

  .. code-block:: bash

    $ ansible --version

  |image2|

.. NOTE:: Keep your SSH or terminal session open for the next lab.

.. |br| raw:: html

   <br />

.. |image1| image:: /_static/class1/image1.png
.. |image2| image:: /_static/class1/image2.png