# -*- mode: ruby -*-
# vi: set ft=ruby :
@ansible_home = "/home/vagrant/.ansible"

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.ignore_private_ip = false
  config.hostmanager.include_offline = true
 
  config.vm.define 'gitlabce' do |node|
    node.vm.hostname = 'gitlabce.example.com'
    node.vm.network :private_network, ip: '172.28.128.20'
    node.hostmanager.aliases = %w(gitlabce.example.com)
  end

  config.vm.synced_folder "gitlabce/", "#{@ansible_home}/roles/gitlabce", type: 'rsync'
  config.vm.provision "shell", inline: "chown vagrant:vagrant #{@ansible_home}"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "gitlabce.yaml"
  end

  config.vm.provider "virtualbox" do |vb|
    vb.customize [ "modifyvm", :id, "--uartmode1", "disconnected" ]
    vb.memory = 4096
    vb.cpus = 1
  end  

end