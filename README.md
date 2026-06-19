Virtualization:
is the process of creating software-based (virtual) instances of computing resources, allowing multiple operating systems, applications, or services 
to run concurrently on a shared physical infrastructure while maintaining logical isolation and resource independence.

KVM:
it is virtualization solution/technology which contains both intel and AMD h/w virtualization properties.

Instllation:
first check that virtualization is enable on hardware level using below command

cat /proc/cpuinfo | grep vmx

If not enable reboot system and enable hardware virtualization from the BIOS seetions.

Packages:  Install below packages for kvm virtualization:

yum install kvm qemu-kvm python-virtinst libvirt libvirt-python virtmanager libguestfs-tools

Start Services:

systemctl start libvirtd

Networking:

Create Bridge network for Virtual Machine Networking.

package: yum install bridge-utilis

After package install configure birdge networking by using network interface along with firewall rule if required.

Create Virtual Machine using virt command:

Downlaod the iso file and keep in the document root path i.e /var/lib/libvert/images

or we can also refer the custom path of the .iso file

Command to create the virtual machine

virt-install \--name vm1 \--description "Test vm" \--os-type=Linux \--os-variant=rhel8 --\ram=1024 \--vcpu=2 \--disk path=/var/lib/libvirt/images/vm1.img,size=40 \--graphics vnc \--cdrom /home/admin/Downloads/centos-8.5.iso \--network bridge:br0

-- size=40 (in gb by default use TB for TB size)

Virtual Machine Configuration:

On succesfull creation of the virtual mahcine, configuration file with .xml extension is created in below path:

/etc/libvirt/qemu/vm1.xml

If we want to do any updation in VM we can done this by editing this file.






