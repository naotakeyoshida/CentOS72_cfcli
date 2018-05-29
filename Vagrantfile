# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.box = "bento/centos-7.2"
    if Vagrant.has_plugin?("vagrant-cachier")
      config.cache.scope = :box
    end
  config.vm.hostname = "centos72"
  config.vm.network "private_network", ip: "192.168.33.100", virtualbox__intnet: "intnet"
  config.vm.provider "virtualbox" do |vb|
    vb.name = "centos72"
    vb.customize ["modifyvm", :id, "--memory", 1024]
  end
  config.vm.provision :shell, path: "bootstrap.sh"
  config.vm.provision :shell, path: "docker.sh"
end
