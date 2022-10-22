
Vagrant.configure("2") do |config|
  config.vm.box = "geerlingguy/debian10"
  config.vm.hostname = "webserver"
  # config.vm.network :private_network, ip: "192.168.56.20"

  config.vm.provider :virtualbox do |v|
    v.memory = 1024
    v.name = "webserver"
    v.cpus = 2
  end

  # Ansible provisioning.
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "provision.yml"
    # ansible.install_mode = "pip"
  end
end