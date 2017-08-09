
A simple Ansible Galaxy role to handle filesystems

It maps all parameters of three modules from a list of dictionaries.

# Examples

## Parted

Partiton the device /dev/sdf with on partion as gpt.

```
blockdevice_partitions:
- device: /dev/sdf
  label: gpt
```

Changed defaults:
number: omit -> 1
state: info -> present

http://docs.ansible.com/ansible/latest/parted_module.html

## Filesystem

Format /dev/sdf1 with ext4.

```
blockdevice_filesystems:
- dev: /dev/sdf1
```

Changed defaults:
fstype: omit -> ext4

http://docs.ansible.com/ansible/latest/filesystem_module.html

## Mount

Mount /dev/sdf1 to /mnt/disk and add a entry in /etc/fstab

```
blockdevice_mounts:
- path: /mnt/disk
  src: /dev/sdf1
```

Changed defaults:
state: omit -> mounted

http://docs.ansible.com/ansible/latest/mount_module.html
