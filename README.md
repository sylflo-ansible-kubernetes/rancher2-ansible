Role Name
=========

This role installs Rancher 2 (see rancher.com) on a custom server using Docker.
It also installs:
  - one cluster (see the Role variables section)
  - Cert manager with a cluster issuer (see cert-manager.io)
  - in the future it will also install Rook (see rook.io)
Requirements
------------

No Requirements

Role Variables
--------------

- docker_version: "18.03" => The docker version you want to install
- rancher_container_name: "rancher-server" => The name you want for the rancher docker container
- rancher_url: "https://yourserverurl" => The url of the rancher server
- rancher_admin_password: "admin_password" => The password you want
- rancher_cluster_name: "cluster_name" => The name you want for the cluster being created
- rancher_network_provider: "calico" => The network provider

Dependencies
------------

No Dependencies

Example Playbook
----------------

    - hosts: servers
      tasks:
      - include_role:
          name: '../../rancher2-ansible'
        vars:
          rancher_url: 'https://my_rancher.fr'
          rancher_admin_password: 'rancher_password'
          rancher_cluster_name: 'my_cluster'

License
-------

MIT

Author Information
------------------

If you have any issue with the project please open one on Github.
Any pull request or improvement idea is welcome.
