# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANT_NFS_DIR = "/vagrant-nfs"
VAGRANT_WORKSPACE_DIR = "/home/vagrant/workspace"
PRIVATE_IP = "192.168.112.112"
host_workspace_directory = Dir.pwd + "/../workspace"

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"

  config.disksize.size = "50GB"

  config.vm.network "private_network", ip: PRIVATE_IP

  config.vm.synced_folder host_workspace_directory, VAGRANT_NFS_DIR, type: :nfs
  config.bindfs.bind_folder VAGRANT_NFS_DIR, VAGRANT_WORKSPACE_DIR

  config.vm.provider 'virtualbox' do |vb|
    # Customize the amount of memory on the VM
    vb.memory = "4096"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
