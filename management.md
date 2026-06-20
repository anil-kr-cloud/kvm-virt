1) To list inventory of running VMs

# virsh list

2) To stop VM gracefully

# virsh sthutdown vm1

3) Stop VM forcefull

# Virsh destory vm1

4) Start VM

# virsh start vm1

5) Pause/suspend (save the current state of th a Virtual Machine) 

# virsh suspend vm1

6) To resume the suspended virtual machine

# virsh resume vm1

7) Check/knbow the detail of the created VM (enable autostart to automatically start the vm if the host server is rebooted.)

# virsh dominfo vm1

8) check/know the detail of the host server/node

# virsh nodeinfo

9) check vcpu assigned to the virtual machine

# virsh vcpuinfo vm1

10) Assign vcpu to virtual machine 

# virsh vcpuping 0 0,0  [format is vpcu cpulist]
# virsh setvcpu vm1 2

11) Assign the ram to the virtual machine, kvm support the overcommitment of the memory and disk, we can use the memory/disk greater then the avialble memory.
memory is used form the irtual ram on the disk/swap. memory management is so good archetected.

# virsh setmem vm1 1024

12) Edit/update the configuration of the created virtual machine. If we make changes in the config file, it won't reflected in the vm. we have to restart the virtual machine. kvm dosenot dynamically allocates resources on the fly.

# virsh edit vm1

13) display xml configuration of the virtual machine.

# virsh dumpxml vm1

14) check the network availble for Virtual Machine

# virsh net-list

15) Define/update network 

# virsh net-edit <networkname>

we can define ip address range/subnet for vms. add mac and ip address inside the <host mac> tag under the <dhcp> tag

16) destory/delte the netowrk

# virsh net-destory default


17) create Backup of the vm. Copy the vm disk (i.e .img file) to other location as 

# dd if=/var/lib/libvirt/images/vm1.img of =/home/admin/backup/vm1.img

18) Take backup in the compressed form

# dd if=/var/lib/libvirt/images/vm1.img | gzip -9 > /home/admin/backup/vm1.img.gz

# dd -if=/dev/vg1/lvm___name /home/admin/backup/vm1.img

19) Migrate the vm form one server to other server. mention path same as parent machine ( /var/lib/libvirt/images) in the other host. After complete migration start the vm and configure the ip as per the new host.

# virsh migrate --live vm1 qemu+ssh://<remote-host-ip>/var/lib/libvirt/images


20) watch logs for all activities (migration etc.). Every operaiton has log saved so that in future we can chek what is happened at partiuclar time. 

# /var/log/libvirt/libvirtd.log
