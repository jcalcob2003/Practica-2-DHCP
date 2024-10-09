# Vagrantfile para crear tres máquinas: dhcp-server, c1, y c2 con IPs estáticas
Vagrant.configure("2") do |config|

  # Configuración de la máquina servidor DHCP
  config.vm.define "dhcp-server" do |server|
    server.vm.box = "ubuntu/bionic64"  # Usa Ubuntu 18.04 como base

  

    # Configuración de la red (IP estática en la red privada 192.168.57.10)
    server.vm.network "private_network", ip: "192.168.57.10"
  end

  # Configuración de la máquina cliente c1 (IP estática en la misma red)
  config.vm.define "c1" do |c1|
    c1.vm.box = "ubuntu/bionic64"


    # Configuración de la red (IP estática en la red privada)
    c1.vm.network "private_network", type: "dhcp"
  end

  # Configuración de la máquina cliente c2 (IP estática en la misma red)
  config.vm.define "c2" do |c2|
    c2.vm.box = "ubuntu/bionic64"

    # Configuración de la red (IP estática en la red privada)
    c2.vm.network "private_network", type: "dhcp"
  end

end