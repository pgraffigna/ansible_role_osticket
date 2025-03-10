ENV['VAGRANT_DEFAULT_PROVIDER'] = 'libvirt'
IMAGEN = "generic/ubuntu2204"
HOSTNAME = "help.home.local"

Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/home/vagrant", type: "rsync", disabled: true

  config.vm.define :server do |s|
    s.vm.box = IMAGEN
    s.vm.hostname = HOSTNAME
    s.vm.provider :libvirt do |v|
      v.disk_bus = 'virtio'
      v.memory = 2048
      v.cpus = 2
      v.graphics_type = 'none'
    end
  end
end

## todo
# crear role apache
# importar role apache en cada version de osticket