This shows an example vagrant file and an ansible playbook to provision it.

You'll need to install vagrant and virtualbox. 

Vagrant https://www.vagrantup.com

Virtualbox https://www.virtualbox.org/

The ansible docs can be found here:

http://docs.ansible.com/ansible/intro.html

This playbook installs a few packages (postgres, emacs, git,
python). Copies a file on the new host.  It also creates a user
account and an account in postgres.  The postgres account has a
password set of `verysecretpassword`.   

You should be able to ssh into the host (using `vagrant ssh` when
the host is finished being provisioned). 

`psql -U edbadmin -W -h localhost example_db`


If you want to change the password, you can create a new hash on the command
line using:

`echo md5$(echo -n verysecretpasswordedbadmin | md5)`

When you're done, you can run `vagrant destroy` and it will wipe out
the host and delete all the files.
