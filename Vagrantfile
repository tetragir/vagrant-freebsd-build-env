$script = <<-'SCRIPT'
pkg install -y git
pkg upgrade -y
git clone https://git.FreeBSD.org/ports.git /usr/ports
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "generic/freebsd13"
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.box_check_update = true
  config.vm.provision "shell", inline: $script
  config.vm.provider :libvirt do |libvirt|
    libvirt.storage_pool_name = "Nyul"
    libvirt.disk_bus = "scsi"
    libvirt.nic_model_type = "virtio"
    libvirt.memory = "16384"
    libvirt.cpus = "6"
    libvirt.graphics_type = "spice"
    libvirt.video_type = "qxl"
  end
end
