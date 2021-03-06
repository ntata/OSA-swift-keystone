`Home <index.html>`_ OpenStack-Ansible Installation Guide

=====================
Installation workflow
=====================

This diagram shows the general workflow associated with an
OpenStack-Ansible (OSA) installation.


**Figure 1.7. Installation workflow**

.. image:: figures/workflow-overview.png

#. :doc:`Prepare deployment hosts <deploymenthost>`
#. :doc:`Prepare target hosts <targethosts>`
#. :doc:`Configure deployment <configure>`
#. :doc:`Run foundation playbooks <install-foundation>`
#. :doc:`Run infrastructure playbooks <install-infrastructure>`
#. :doc:`Run OpenStack playbooks <install-openstack>`

=======

Network ranges
~~~~~~~~~~~~~~

For consistency, the following IP addresses and hostnames are
referred to in this installation workflow.

+-----------------------+-----------------+
| Network               | IP Range        |
+=======================+=================+
| Management Network    | 172.29.236.0/22 |
+-----------------------+-----------------+
| Tunnel (VXLAN) Network| 172.29.240.0/22 |
+-----------------------+-----------------+
| Storage Network       | 172.29.244.0/22 |
+-----------------------+-----------------+


IP assignments
~~~~~~~~~~~~~~

+------------------+----------------+-------------------+----------------+
| Host name        | Management IP  | Tunnel (VxLAN) IP | Storage IP     |
+==================+================+===================+================+
| infra1           | 172.29.236.101 | 172.29.240.101    | 172.29.244.101 |
+------------------+----------------+-------------------+----------------+
| infra2           | 172.29.236.102 | 172.29.240.102    | 172.29.244.102 |
+------------------+----------------+-------------------+----------------+
| infra3           | 172.29.236.103 | 172.29.240.103    | 172.29.244.103 |
+------------------+----------------+-------------------+----------------+
|                  |                |                   |                |
+------------------+----------------+-------------------+----------------+
| net1             | 172.29.236.111 | 172.29.240.111    |                |
+------------------+----------------+-------------------+----------------+
| net2             | 172.29.236.112 | 172.29.240.112    |                |
+------------------+----------------+-------------------+----------------+
| net3             | 172.29.236.113 | 172.29.240.113    |                |
+------------------+----------------+-------------------+----------------+
|                  |                |                   |                |
+------------------+----------------+-------------------+----------------+
| compute1         | 172.29.236.121 | 172.29.240.121    | 172.29.244.121 |
+------------------+----------------+-------------------+----------------+
| compute2         | 172.29.236.122 | 172.29.240.122    | 172.29.244.122 |
+------------------+----------------+-------------------+----------------+
| compute3         | 172.29.236.123 | 172.29.240.123    | 172.29.244.123 |
+------------------+----------------+-------------------+----------------+
|                  |                |                   |                |
+------------------+----------------+-------------------+----------------+
| lvm-storage1     | 172.29.236.131 |                   | 172.29.244.131 |
+------------------+----------------+-------------------+----------------+
|                  |                |                   |                |
+------------------+----------------+-------------------+----------------+
| nfs-storage1     | 172.29.236.141 |                   | 172.29.244.141 |
+------------------+----------------+-------------------+----------------+
|                  |                |                   |                |
+------------------+----------------+-------------------+----------------+
| ceph-mon1        | 172.29.236.151 |                   | 172.29.244.151 |
+------------------+----------------+-------------------+----------------+
| ceph-mon2        | 172.29.236.152 |                   | 172.29.244.152 |
+------------------+----------------+-------------------+----------------+
| ceph-mon3        | 172.29.236.153 |                   | 172.29.244.153 |
+------------------+----------------+-------------------+----------------+
|                  |                |                   |                |
+------------------+----------------+-------------------+----------------+
| swift1           | 172.29.236.161 |                   | 172.29.244.161 |
+------------------+----------------+-------------------+----------------+
| swift2           | 172.29.236.162 |                   | 172.29.244.162 |
+------------------+----------------+-------------------+----------------+
| swift3           | 172.29.236.163 |                   | 172.29.244.163 |
+------------------+----------------+-------------------+----------------+
|                  |                |                   |                |
+------------------+----------------+-------------------+----------------+
| log1             | 172.29.236.171 |                   |                |
+------------------+----------------+-------------------+----------------+

--------------

.. include:: navigation.txt
