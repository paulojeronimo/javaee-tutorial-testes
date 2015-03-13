# -*- mode: ruby -*-
# vi: set ft=ruby ts=2 sw=2 expandtab:

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "chef/fedora-21"
  config.vm.box_check_update = false

  # Desabilita a atualização automática do VirtualBox Guest Additions
  # feita pelo plugin vbguest - https://github.com/dotless-de/vagrant-vbguest
  config.vbguest.auto_update = false

  # Exporta portas utilizadas pelo WildFly
  config.vm.network :forwarded_port, guest: 8080, host: 8080
  config.vm.network :forwarded_port, guest: 9990, host: 9990

  # Exporta portas utilizadas pelo PostgreSQL
  config.vm.network :forwarded_port, guest: 5432, host: 5432

  config.vm.provider "virtualbox" do |v|
    v.gui = true
    v.memory = 2048
  end

  # Local comum para os diretórios compartilhados entre os ambientes
  config.vm.synced_folder "../javaee-tutorial-testes.backup", "/backup", create: true
end
