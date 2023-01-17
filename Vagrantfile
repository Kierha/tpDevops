Vagrant.configure("2") do |config|
  vm_names = ["Database Server", "Web Server"]
  (0..1).each do |i|
    config.vm.define "vm#{i+1}" do |vm|
      vm.vm.box = "ubuntu/trusty64"
      vm.vm.provider :virtualbox do |vb|
        vb.name = vm_names[i]
      end
    end
  end
end
