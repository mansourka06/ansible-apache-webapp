
Vagrant.configure("2") do |config|
  config.vm.box = "geerlingguy/debian10"
  config.vm.hostname = "web_server"
  config.vm.network :private_network, ip: "192.168.33.10"

  config.vm.provider :virtualbox do |v|
    v.memory = 512
  end

  # Ansible provisioning.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision.yml"
    ansible.become = true
  end
end