Vagrant.configure("2") do |config|
  config.vm.box = "gusztavvargadr/windows-11"
  config.vm.provision :ansible do |ansible|
    ansible.limit = "all"
    ansible.playbook = "playbook.yml"
    ansible.host_vars = {
      "default" => { "ansible_winrm_scheme" => "http" }
    }
  end
  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = true
    # Customize the amount of memory on the VM:
    vb.memory = "8192"
    vb.cpus = 4
  end
end
