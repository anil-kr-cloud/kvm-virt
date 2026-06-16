Virtualization:
is the process of creating software-based (virtual) instances of computing resources, allowing multiple operating systems, applications, or services 
to run concurrently on a shared physical infrastructure while maintaining logical isolation and resource independence.

KVM:
it is virtualization solution/technology which contains both intel and AMD h/w virtualization properties.

Instllation:
first check that virtualization is enable on hardware level using below command
cat /proc/cpuinfo | grep vmx
If not enable reboot system and enable hardware virtualization from the BIOS seetions.

Packages:
Below are the packages need to be installed for kvm virtualization:

yum install kvm qemu-kvm python-virtinst libvirt libvirt-python virtmanager libguestfs-tools

KVM: This package enables Linux to function as a hypervisor by utilizing hardware virtualization extensions such as Intel VT-x or AMD-V. KVM converts the Linux kernel into a virtualization platform capable of running virtual machines.
qemu-kvm	Provides the QEMU emulator integrated with KVM acceleration. QEMU emulates hardware components (CPU, memory, disks, network interfaces), while KVM accelerates execution using the host CPU's virtualization capabilities. Together, they provide high-performance virtualization.
python-virtinst	Contains the Virt-install utility and Python libraries used to create and configure virtual machines from the command line. It simplifies VM deployment by automating guest operating system installation.
libvirt	A virtualization management framework that provides a common API for managing virtual machines, networks, and storage pools. It acts as an abstraction layer between management tools and hypervisors such as KVM, QEMU, Xen, and others.
libvirt-python	Python bindings for the Libvirt API. It allows developers and administrators to write Python scripts to automate VM lifecycle management, storage management, and network configuration.
virt-manager	A graphical desktop application used to create, configure, monitor, and manage virtual machines through the Libvirt framework. It provides a user-friendly interface for KVM/QEMU administration.
libguestfs-tools	A collection of tools for accessing and modifying virtual machine disk images offline. It enables administrators to inspect, edit, resize, recover, or troubleshoot VM filesystems without starting the virtual machine.
