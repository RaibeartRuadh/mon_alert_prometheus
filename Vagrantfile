# -*- mode: ruby -*-
# vi: set ft=ruby :

ANSIBLE_NAME = "RaibeartPRO_GRA"
SERVER_IP = "192.168.10.10"
# PORT MAPPING
NODE_PORT_GUEST = 9100
NODE_PORT_HOST = 9100
PROM_PORT_GUEST = 9090
PROM_PORT_HOST = 9090
GRAFANA_PORT_GUEST = 3000
GRAFANA_PORT_HOST = 3000

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.box_check_update = false
    config.vm.define "server" do |server|
    server.vm.hostname = "server"
    server.vm.network "private_network", ip: SERVER_IP
  server.vm.network "forwarded_port", host: NODE_PORT_HOST, guest: NODE_PORT_GUEST
  server.vm.network "forwarded_port", host: PROM_PORT_HOST, guest: PROM_PORT_GUEST
  server.vm.network "forwarded_port", host: GRAFANA_PORT_HOST, guest: GRAFANA_PORT_GUEST
  server.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
  end
 end
end
