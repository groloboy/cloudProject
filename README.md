# Cloud Project Guide
## Requirements

- [Vagrant](https://www.vagrantup.com)
- [VirtualBox](https://www.virtualbox.org)
- 6GB unused RAM

## [Quick start Vagrant](https://github.com/rancher/quickstart/tree/master/vagrant) *Official Rancher guide*

1. Clone the repository using `git clone https://github.com/groloboy/cloudProject.git`

2. Go into the folder containing the Vagrantfile by executing `cd rancher`

3. Optional: Edit config.yaml to:
   * Change the the memory allocations, if required. (node.cpus, node.memory)  
   * Change the password of the admin user for logging into Rancher. (default_password)

4. To initiate the creation of the rancher environment run `vagrant up --provider=virtualbox`

5. Once provisioning finishes, go to https://172.22.101.101 in the browser. The default user/password is admin/admin.

![Init page](https://github.com/groloboy/cloudProject/blob/main/images/welcome.png)

## Our first cluster

1. Create a virtual machine that'll be the master node, go to cluster folder `cd cluster`

2. See the Vagrantfile and verify that the ip of the virtual machine is `172.22.101.102`

3. Now create the virtual machine with `vagrant up master`

4. Once provisioning finishes, execute `vagrant ssh master` and after `curl -sfL https://get.k3s.io | sh -` this is to install a lightweight Kubernetes version

5. Go to Rancher and follow the images
   * Go to clusters
   ![Init page](https://github.com/groloboy/cloudProject/blob/main/images/go_cluster.png)
   * Go to add cluster
   ![Init page](https://github.com/groloboy/cloudProject/blob/main/images/add_cluster.png)
   * Go to import an existing cluster
   ![Init page](https://github.com/groloboy/cloudProject/blob/main/images/import_cluster.png)
   * Add a name for the cluster and click create
   ![Init page](https://github.com/groloboy/cloudProject/blob/main/images/name_cluster.png)
   * Copy the first command on the master virtual machine, if doesn't work copy and execute the second one
   ![Init page](https://github.com/groloboy/cloudProject/blob/main/images/comand.png)
   * Next click Done

6. In the master virtual machine execute `sudo kubectl get nodes` to refresh the cluster in Rancher



