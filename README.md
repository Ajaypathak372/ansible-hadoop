Setup Hadoop HDFS Cluster with Ansible
======================================

A role to setup a Hadoop HDFS Cluster. It configures specified systems(hosts) as NameNode and DataNodes and connect them to form a HDFS Cluster.

Requirements
------------

For this role, you have to make ```gather_facts``` true as behind the scene it uses some of the Facts of the host otherwise no requirements.

Role Variables
--------------

This role has 1 main variable ```hadoop_type_of_node``` that needs to be specified. So if you want to configure a system as Hadoop Master then the value of this variable can be ```namenode``` or ```master``` and similarly for DataNodes(or slaves) the value can be ```datanode``` or ```slave```.

Dependencies
------------

This role does not depends on any other Galaxy roles.

Example Playbook
----------------

    - hosts: namenode
      gather_facts: true
      roles:
        - { role: Ajaypathak372.ansible-hadoop ,vars: {hadoop_type_of_node: "namenode"}}

    - hosts: datanodes
      gather_facts: true
      roles:
        - { role: Ajaypathak372.ansible-hadoop ,vars: {hadoop_type_of_node: "datanode"}}


License
-------

BSD

Author Information
------------------

This role is created by Ajay Pathak. For any suggestions, corrections or any other queries you can contact me at [LinkedIn](https://www.linkedin.com/in/ajay-pathak372).
