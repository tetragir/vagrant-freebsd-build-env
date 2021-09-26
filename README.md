# Vagrant Setup

## Definition
This Vagrantfile contains a configuration for a FreeBSD VM on KVM with git installed and the ports tree checked out.
I use this setup to quickly create a FreeBSD to modify ports' Makefiles to update them.

## Instructions

### 1. Options
Change the Vagrantfile if needed:
* ```libvirt.storage_pool_name``` => Defines the name of the storage pool (default probably will do fine)
* ```libvirt.memory``` => Amount of memory in MB
* ```libvirt.cpus``` => Amount of CPU cores assigned to the VM

### 2. Validate
Once the Vagrantfile is modified, check the syntax with:
```shell
vagrant validate
```

### 3. Run
If there are no issues found, start up the VM:
```shell
vagrant up
```

### 4. Log in
Once the start-up is finished, enter the VM:
```shell
vagrant ssh default
```

### 5. Finish
Once finished, destroy (shut down and delete) the VM:
```shell
vagrant destroy -f
```
