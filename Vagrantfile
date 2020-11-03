IMAGE_NAME = "ubuntu/xenial64"
N = 1

require 'yaml'

config_file = YAML.load_file("config.yml")
settings = config_file['passwords'];

Vagrant.configure("2") do |config|
    config.ssh.insert_key = false

    config.vm.provider "virtualbox" do |v|
        v.memory = 1024
        v.cpus = 2
    end
      
    config.vm.define "jenkins" do |jenkins|
        jenkins.vm.box = IMAGE_NAME
        jenkins.vm.network "private_network", ip: "192.168.2.10"
        jenkins.vm.hostname = "jenkins"
        jenkins.vm.provision "ansible" do |ansible|
            ansible.playbook = "setup/jenkins-playbook.yml"
            ansible.extra_vars = {
                node_ip: "192.168.2.10",
                admin_user_pass:settings["admin_user_pass"]
            }
        end
    end
#    (1..N).each do |i|
#        config.vm.define "server-#{i}" do |server|
#            server.vm.box = IMAGE_NAME
#            server.vm.network "private_network", ip: "192.168.2.#{i + 11}"
#            server.vm.hostname = "server-#{i}"
#            server.vm.provision "ansible" do |ansible|
#                ansible.playbook = "setup/server-playbook.yml"
#                ansible.extra_vars = {
#                    node_ip: "192.168.2.#{i + 10}",
#                }
            end
#        end
#    end
#    
#end