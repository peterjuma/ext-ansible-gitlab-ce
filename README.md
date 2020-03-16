# ansible-gitlab-ce

This ansible role covers the installation and configuring GitLab (CE) on a CentOS 7


vagrant plugin install vagrant-hostmanager
=======
# ansible-gitlab-ce

This ansible role covers the installation and configuring GitLab (CE) on a CentOS 7

# Pre-requisite


*  Change the IP in gitlabce/vars/main to a desired one

*  Change the IP in Vagrantfile to a desired one

# Vagrant Plugin Installation [https://www.rubydoc.info/gems/vagrant-hostmanager/1.7.0]

`vagrant plugin install vagrant-hostmanager`

# Clone repo

```
git clone https://gitlab.com/peterjuma/ansible-gitlab-ce.git
cd ansible-gitlab-ce
vagrant up
```

If running the ansible provisioner on the host, create a symbolic link to the gitlabce role directory

`ln -s gitlabce /etc/ansible/roles/gitlabce`


```
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "gitlabce.yaml"
  end
```

Otherwise, if running the ansible provisioner on the guest:

```
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "gitlabce.yaml"
  end
```

# Accessing GitLab CE 

Access GitLab CE via browser using the IP configured in Vagrantfile