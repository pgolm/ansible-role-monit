# -*- mode: ruby -*-
# vi: set ft=ruby ts=2 sw=2 tw=0 et :

vmname = File.basename(File.expand_path(File.dirname(__FILE__)))

Vagrant.configure("2") do |config|

  config.vm.define "Debian-10" do |ap|
    ap.vm.box = "debian/stretch64"
    ap.vm.hostname = "Debian-10"

    ap.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
      v.customize ["modifyvm", :id, "--memory", 512]
    end

    ap.vm.network :private_network, ip: "10.0.0.40"
    ap.vm.network :forwarded_port, guest: 2812, host: 2813

    ap.vm.provision :ansible do |ansible|
      ansible.playbook = "vagrant.yml"
    end
  end

  config.vm.define 'Centos-7' do |ap|
    ap.vm.box = "centos/7"
    ap.vm.hostname = 'Centos-7'

    ap.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
      v.customize ["modifyvm", :id, "--memory", 512]
    end

    ap.vm.network :private_network, ip: "10.0.0.41"
    ap.vm.network :forwarded_port, guest: 2812, host: 2814


    #ap.vm.provision "shell", inline: "ln -sf /sbin/service /usr/sbin/service"
    ap.vm.provision :ansible do |ansible|
      ansible.playbook = "vagrant.yml"
    end
  end

end
