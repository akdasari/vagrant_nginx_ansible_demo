# Prerequisites validation

## Vagrant version
Vagrant.require_version ">= 2.0.0"


## Variables
$app_name = "Anand-EE-Demo"
$vm_ip = "192.168.56.10"
$vm_memory = 512
$vm_cpu = 1



# Definitions	
Vagrant.configure("2") do |config|
  config.vm.provider :virtualbox do
  unless Vagrant.has_plugin?("vagrant-vbguest")
    raise "The vagrant-vbguest plugin is not installed. Run `vagrant plugin install vagrant-vbguest` then try again."
  end
end

  config.vm.box = "bento/centos-7.4"
  config.vm.hostname = $app_name
  config.vm.network "forwarded_port", guest: 8080, host: 80
  config.vm.network "private_network", ip: $vm_ip

  config.vm.provider "virtualbox" do |vb|
    vb.name = $app_name
    vb.customize ['modifyvm', :id, '--memory', $vm_memory, '--cpus', $vm_cpu]
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision/playbook.yml"
    ansible.verbose = true
  end

end


