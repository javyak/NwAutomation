Generates configuration files for a DC fabric made of Arista EOS devices based on an infrastructure data model file.

The playbooks creates device data models in variable files, configuration files for the fabric and configuration files for the services (just IP subnets and VLANs in this version).

Files that defines the fabric and services:

- infr_data_model.yml - infrastructure data model. Modify it with the appropriate DC fabric parameters.

- services_data_model.yml - defines the IP subnets and VLANs required by end systems. Modify it with the appropriate values for the end devices.

Ansible playbooks:

- create_host_vars.yml - creates the hosts files dinamically and the device data models in the group and host vars directories. Use this playbook first.

- create_configs.yml - creates the DC fabric configuration files and store them in the ./config directory. 

- create_service_configs.yml - creates the service configuration files for leaf switches and store them in the ./services directory.

Jinja2 templates:

- fabric2hosts.j2 - template for creating the dynamic hosts file.

- fabric2nodes_data_model.j2 - template that creates the device data models in the group and host variable files.

- services.j2 - template that creates the service configuration files for the leaf switches (end system subnets and VLANs).

- LEAF.j2 - template that creates the DC fabric configuration files for leafs.

- SPINE.j2 - template that creates the DC fabric configuration files for spines.