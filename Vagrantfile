# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # ubuntu 18.04
  config.vm.box = "hashicorp/bionic64"

  config.vm.provider "virtualbox" do |vb|
    # Customize the amount of memory on the VM:
    vb.memory = "4096"
    vb.cpus = 2
    vb.name = "c2-b10-5_default_1644938505616_81675"
  end


  # install postgresql 8.4
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "vm-deploy.yml"
  end

  # Требование задания п.5 - выполнены ранее, не нужны (уже установлены), но так тоже можно было бы
  # config.vm.provision "shell", inline: <<-SHELL
  #   echo "Don't need - already installed via OS packages (ansible)"
  #   pip3 install django psycopg2
  # SHELL
end
