# vim: ts=2 sw=2 et ft=ruby

Vagrant.configure("2") do |config|
    config.vm.synced_folder ".", "/vagrant", disabled: true
    config.ssh.username = "root"
    config.ssh.insert_key = false
  
    config.vm.define "default" do |vm|
      vm.vm.provider "docker" do |docker|
        #docker.build_dir = "."
        docker.image = "jojees/dockertest:0.1"
        docker.has_ssh = true
      end
    end
  
    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yml"
      ansible.limit = "all"
    end
  end