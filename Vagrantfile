# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.define :centos_7
  config.vm.box_check_update = false
  config.vm.network "forwarded_port", guest: 5432, host: 5432
  config.ssh.insert_key = false
  config.vm.provider "hyperv" do |vb|
    vb.memory = "2048"
    vb.cpus = 1
  end

  config.vm.provision "shell", inline: <<-SHELL
    yum install -y https://download.postgresql.org/pub/repos/yum/reporpms/EL-7-x86_64/pgdg-redhat-repo-latest.noarch.rpm
    yum install -y postgresql10-server
#	postgresql-10-setup initdb
#	systemctl enable postgresql-10 --now
  SHELL
end