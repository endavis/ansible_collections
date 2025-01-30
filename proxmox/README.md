# Ansible Collection - endavis.proxmox

This collection includes roles related to Proxmox:
- add_storage: add disks/mount points to an object
    - requires: proxmox_object_disks
    - Add mount points for LXC and Disks for VM
- create: creates an object
    - creates an lxc container if proxmox_object_type is "lxc"
    - creates a qemu VM if proxmox_object_type is "qemu"
- find: will find an object
    - sets the following facts:
      - proxmox_object_exists
      - proxmox_object_type
      - proxmox_object_name
      - proxmox_object_primary_node
      - proxmox_object_status
- get_ips: get the IPv4 IPs of an object
    - requirements:
      - Overall: object running
      - for qemu VMs: guest-agent running
    - sets the following facts:
      - proxmox_object_ip
      - proxmox_object_ips
- get_mac: get MAC address of net0
    - requirements:
      - Overall: object running
    - sets the following facts:
      - proxmox_mac
- start: starts or restarts an object
- update_cores:
    - Updates the cores on the object
- update_memory:
    - Updates the memory on the object
- update_vlan:
    - updates the vlan
      - For a qemu VM, the VLAN is updated on net0

## Variables
- [See variables in base role](roles/base/defaults/main.yml)

## Examples
- [Examples](docs/examples)
