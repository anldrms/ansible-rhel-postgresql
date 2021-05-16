# ansible-rhel-postgresql

**Bootcamp Case: 1 postgresql installation**

      sudo yum -y update
      sudo yum -y install epel-release

We install the Ansible package.

    sudo yum -y install ansible

Finally, let's check our version.

      ansible --version

  
  And then we can run our playbook.
  
     ansible-playbook playbook.yml
