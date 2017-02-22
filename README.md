Ansible Swap File Role
============

Easily edit and deploy simple SWAP space into your server on the fly with high-availability.

How does this works ?
------------

You can install it or change the swap file size whenever you need without the need of rebooting.

When you change the size of swap (or install the role then provision) there's what happens :

 1. Creates new swap file with the new specified size, then enable it
 2. Transfert the old swap file contents to the new one
 3. Delete the old swap file to free space on the hard drive


Safety first
------------

When you change the swap file size, while transferring swap pages into the new one, it can cause temporary hard drive load and server latency, but not much.

If you want to change the swap file size, we do recommend to wait when the server's load is relatively low.

System requirements
------------

* Any Linux-family operating system (Debian, CentOS etc..)
* Ansible 2.0+ installed on the deployment host


Installation procedure
------------

Simply add this role into your Ansible file, change the "swapfile_size_mb" (in megabytes) as your need, and then run provision.

```
---
- hosts: all
  roles:
    - role: swapfile
      swapfile_size_mb: 512

```
