# Cloud Project Guide
## [Quick start Vagrant](https://github.com/rancher/quickstart/tree/master/vagrant)

1. Clone Rancher Quickstart to a folder using `git clone https://github.com/rancher/quickstart`

2. Go into the folder containing the Vagrantfile by executing `cd quickstart/vagrant`

3. Optional: Edit config.yaml to:
   * Change the number of nodes and the memory allocations, if required. (node.count, node.cpus, node.memory)  
   * Change the password of the admin user for logging into Rancher. (default_password)
4. To initiate the creation of the environment run, `vagrant up --provider=virtualbox`

5. Once provisioning finishes, go to https://172.22.101.101 in the browser. The default user/password is admin/admin.
