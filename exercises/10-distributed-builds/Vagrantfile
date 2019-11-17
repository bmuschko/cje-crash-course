# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"

  (1..2).each do |number|
    config.vm.define "jenkins-agent-#{number}" do |node|
      node.vm.network "forwarded_port", guest: 22, host: "909#{number}"
      node.vm.network "private_network", ip: "192.168.99.20#{number}"
      node.vm.hostname = "jenkins-agent-#{number}"
    end
  end

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end

  config.vm.provision "shell", inline: <<-SHELL
    sudo add-apt-repository ppa:openjdk-r/ppa -y
    sudo apt-get update
    sudo apt-get -y install openjdk-8-jdk
    sudo update-alternatives --config java
    sudo apt-get -y install git
    sudo useradd -m jenkins
    echo "jenkins:jenkins" | sudo chpasswd
    sudo keytool -importkeystore -srckeystore /etc/ssl/certs/java/cacerts -destkeystore /etc/ssl/certs/java/cacerts.jks -deststoretype JKS -srcstorepass changeit -deststorepass changeit -noprompt
    sudo mv /etc/ssl/certs/java/cacerts.jks /etc/ssl/certs/java/cacerts
    sudo /var/lib/dpkg/info/ca-certificates-java.postinst configure
  SHELL
end
