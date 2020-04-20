# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.hostname = 'rails-vagrant-dev-box'
  config.vm.box = 'ubuntu/eoan64' # 19.10
  config.vm.boot_timeout = 300

  config.vm.network :private_network, ip: '192.168.10.10'
  config.vm.synced_folder ENV.fetch('RAILS_VAGRANT_BOX_FOLDER', '.'), '/vagrant', type: :nfs

  config.vm.provision :ansible do |ansible|
    ansible.playbook = 'playbook.yml'
    ansible.become = true
    ansible.extra_vars = { ansible_python_interpreter: '/usr/bin/python3' }
  end

  config.vm.provider :virtualbox do |vb|
    vb.memory = ENV.fetch('RAILS_VAGRANT_BOX_RAM', 2048).to_i
    vb.cpus = ENV.fetch('RAILS_VAGRANT_BOX_CPUS', 2).to_i
  end
end
