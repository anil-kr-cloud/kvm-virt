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

After package install configure birdge networking by using network interface.


