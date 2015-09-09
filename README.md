# vagrant-puppet-hiera
Vagrantfile and directory structure that creates a vagrant box which can be provisioned with puppet and hiera.

To use:

* Create the puppet/modules directory:

	```shell
	mkdir puppet/modules
	```
* Populate modules dir with your chosen modules:

    ```shell
	puppet module install thing --modulepath puppet/modules
	```
* Edit the puppet/default.pp manifest to include whichever modules you want:

    ```puppet
    class { 'thing': }
	```
* Create and edit puppet/hieradata/common.yaml to set common hiera data or
  puppet/hieradata/hostname-of-box.yaml for per-machine data.

* Bring up the vagrant box:

    ```shell
	vagrant up
	```

* When you've made changes to the puppet code or hiera data, run the puppet provisioner:

    ```shell
	vagrant provision
	```
