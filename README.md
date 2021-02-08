k8s-maste
=========

This role will configure master node of kubernetes multi node cluster on AWS Amazon linux

Requirements
------------

To successfully configure master node you must have an Amazon linux ec2-instance launched on AWS whose public IP uploaded on your inventory file under group-name master.

Role Variables
--------------

In /vars/main.yml update update the cidr block to initilize the kubeadm service.
 And download the flannel plugin playbook.yml and keep in template directory use jinja template to update the cidr block in network part.
[flannel-plugin](https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml)
Dependencies
------------

After this role run you can run slave node setup whole link given below
[k8s-slave-node-setup]()

Example Playbook
----------------

    - hosts: master
      roles:
         - { role: karanraj.k8s_master }

* See Also
  [k8s-slave-node-setup](https://galaxy.ansible.com/karanraj/k8s_slave)

