# -*- mode: ruby -*-
# vi: set ft=ruby ts=2 sw=2 tw=0 et :

vmname = File.basename(File.expand_path(File.dirname(__FILE__)))

Vagrant.configure("2") do |config|

  config.vm.define "Debian-7.4.0" do |ap|
    ap.vm.box = "opscode-debian-7.4.0"
    ap.vm.box_url = "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_debian-7.4_chef-provisionerless.box"
    ap.vm.hostname = "Debian-7.4.0"

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

  config.vm.define 'Centos-65' do |ap|
    ap.vm.box = "Centos65"
    ap.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.3/centos65-x86_64-20140116.box"
    ap.vm.hostname = 'Centos-65'

    ap.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
      v.customize ["modifyvm", :id, "--memory", 512]
    end

    ap.vm.network :private_network, ip: "10.0.0.41"
    ap.vm.network :forwarded_port, guest: 2812, host: 2814

    ap.vm.provision "shell", inline: "ln -sf /sbin/service /usr/sbin/service"
    ap.vm.provision :ansible do |ansible|
      ansible.playbook = "vagrant.yml"
    end
  end

end
