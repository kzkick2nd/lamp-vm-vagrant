# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "boxcutter/centos67"
  config.hostsupdater.remove_on_suspend = true
  config.vm.network "forwarded_port", guest: 80, host: 8080, auto_correct: true
  config.vm.network "private_network", ip: "192.168.33.20"
  config.vm.hostname = "lamp.vg"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision/site.yml"
    ansible.sudo = true
    ansible.verbose = "v"
  end
end
