<<<<<<< HEAD
# ansible-gitlab-ce

This ansible role covers the installation and configuring GitLab (CE) on a CentOS 7


vagrant plugin install vagrant-hostmanager
=======
# ansible-gitlab-ce

This ansible role covers the installation and configuring GitLab (CE) on a CentOS 7

# Pre-requisite


*  Change the IP in gitlabce/vars/main to a desired one

*  Change the IP in Vagrantfile to a desired one

# Vagrant Plugin Installation

`vagrant plugin install vagrant-hostmanager`

# Clone repo

```
git clone https://gitlab.com/peterjuma/ansible-gitlab-ce.git
cd ansible-gitlab-ce
vagrant up
```


# Accessing GitLab CE 

Access GitLab CE via browser using the IP configured in Vagrantfile
>>>>>>> 3660321bc71e557fd2b014986f1c423aa796cfb0
