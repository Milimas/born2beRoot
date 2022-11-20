# Born2BeRoot

## What is a Virtual Machine?

> **A VM is the `virtualization`/`emulation` of a `computer system`.**

### Virtualization:

>	The act of creating a virtual (rather than actual) version of somthing at the same abstraction level, including virtual computer hardware platforms, storage devices, and computer network resources.

### Emulation: 
	
-	In computing, an emulator is hardware orå software that enables one computer system (`called the host`) to behave like another computer system (`called the guest`).
	
-	An emulator typically enables the host system to run software or use peripheral devices designed for the guest system.
	
-	Emulation refers to the ability of a computer program in an electronic device to emuate (or imitate) an other program or device.

### Computer system:
	
-	A computer system is a "complete" computer that includes the hardware, operating system (main software), and peripheral equipment nedded and used for "full" operation.
	
-	This term may also refer to a group of computers that are linked and function together, such as a computer network or 
	computer cluster.
		
	-	A `computer cluster` is a set of computers that work together so that they can be viewed as a singe system. 
		
	-	The components of a cluster are usually connected to each other through fast local area networks, with each node (computer used as a server) running its own instance of an operating system.

## How a virtual machine works?

### Hypervisor:
	
-	A `hypervisor` (also known as a virtual machine monitor, VMM, or virtualizer) is a type of computer sooftware, firmware or hardware that creates and runs virtual machines.
	
-	A computer on which a hypervisor runs one or more virtual machines is called a host machine, and each virtual machne is called a guest machine.
	
-	The hypervisor presents the guest operating systems with a `virtaul operating platform` and manages the execution of the guest operating systems. Unlike an emulator, the guest executes most instructions on the native harware.

#### Hypervisors Types:

-	Hypervisor Type-1:

	-	native or bare-metal hypervisors
		
		-	These hypervisors run directly on the host's hardware and to manage guest operating systems.
	
-	Hypervisors Type-2:
	
	-	Hosted hypervisors
		
		-	These hypervisors run on a conventional operating system (OS) just as other comuter programs do.
		-	a virtual machine monitor runs as a `process` on the host.
		-	Type-2 hypervisors abstract guest operating systems from the host operating system.

> *The distinction between these two types is not always clear, For instance, `KVM` and `bhyve` are `kernel modules` that effectively convert the host operating system to a type-1 hypervisor. At the same time, since `Linux distributions` and `freeBSD` are still general-purpose operating systems, with application copeting with each other for VM resources, KVM and bhyve can also be categorized as type-2 hypervisors.*

## Oracle VM VirtualBox

> VirtualBox is a `type-2 hypervisor` for `x86 virtualization` developed by Oracle Corporation.
>
> It supports the creation and management of guest virtual machines running OS as well as limited virtualization of macOS guests on Apple hardware.

### Virtualization

> Users of `VirtualBox` can load multiple guest OSes under a single host operating-system (host OS). Each guest can be `started`, `paused` and `stopped` independently within its own virtual machine (VM).
>
> The user can independently configure each VM and run it under a choice of `software-based virtualization`, or `hardware assisted virtualization` if the underlying host hardware supports this.

### Devices and Periperals

#### Disk formats:

> VirtualBox emulates hard disks in three formats:

-	The native `VDI` (Virtual Disk Image)
-	The `VMDK` or `VMware`
-	The `VHD`

#### Disk image:

> `Disk iamge` is a computer file conatining the contents and structure of a `disk volume` or of an entire `data storage device`.
The size of a disk image can be large because it contains the contents of an entre disk. *To reduce storage requirements, if an imaging utility is filesystemaware it can omit copying unused space, and it can compress the used space.*

> VirtaulBox can also connect to `iSCSI` targets and to raw partitions on the host, using either as virtual hard disks.

> Both `ISO images` and physica devices connected to the host can be mounted as CD or DVD drives. VirtualBox supports running operating system from `live CDs and DVDs`

### Network:

> VirtualBox uses `NAT` through which internet software for end-users such as `Firefox` or `ssh` can operate.

> `NAT` or `Network addess translation is a method of mapping an IP address space into another by modifying network address information in the IP Header of packets while they are in transit across a traffic rounting device.

> `Secure Shell Protocol` (`ssh`) is a `cryptographic network protocol` for operating network services securely over an unsecured network. Its most notable applications are remote `login` and `command-line` execution.

## Linux

> Linux is an open-source `Unix-like` operating system based on the `Linux Kernel`, linux is typically packaged as a `Linux Distribution`.
>
> The `Linux Kernel is a `free and open-source`, `Unix-line` operating system `kernel`.
>
> A `Linux distribution` (often abbreviated as `distro`) is an operating system made from a software collection that includesthe `Linux kernel` and often a `package management system`.

### Destribution
	
> Almost one thousand `Linux Distributions` exist.

#### Debian
	
> `Debian` also known as *Debian GNU/Linux*, is a linux distribution, developed by the comunity-supported Debian Project, Debian is also the basis for many other distibutions.

*Developer :* `The Debian Project`

*Working state:* `current`

*Update method:* `Long-Term support` in stable edition, `rolling release` in unstable and testing editions

*Package manager:* `dpkg`
	
-	> `dpkg` is a package manager used to install, remove and provide information about `.deb` `packages`
-	> A `Package` format (`.deb`) is a type of archive containing computer programs and additional metadata needed by package mangers. It may contain either source code or executable files

#### CentOS

> `CentOS` also known as *CentOS Linux*, is a Linux distribution that provides a free and open-source community-supported computing platform. *In December 2020, Red Hat unilaterally terminnated CentOS development. CentOS founder `Gregory Kurtzer` created the `Rocky Linux` project as a successor to the original mission of CentOS.*

*Developer:* `The CentOS Project` (affiliated with `Red Hat`)

*Working state:* `Discontinued`

*Update method:* `Release Candidate`

*Package manager:* `dnf` (command line); `PackageKit` (graphical);, `.rpm` (binaries format)

-	> `DNF` or `Dandified YUM` is the next-generation version of the Yellowdog Updater, Modified (yum), a package manager for `.rpm`-based Linux distributions.
	> 
	> `DNF` performs package management tasks on top of `RPM`, and supporting libraries.
	>
	> `RPM Package Manager` (`RPM`) (originally `Red Hat Package Manager). The name RPM reffers to the `.rpm` file format and the package manager program itself.

-	> `PackageKit` is a suite of software application designed to provide a consistent and high-level `front end` for a number of different package management systems.

#### Basic difference between CentOS and Debian

|	`CentOS`				|	`Debian`	|
|---------------------------|---------------|
|	Doesnt support many different architecturs.	|	Has more packages.	| 
| 	Difficult to upgrade a version of CentOS locally. Official sources recommend installing a newer version then to upgrade an older one.	|	Upgrading Debian from one stable version to another is easy and not painful.	|
|	It does not have an easy GUI.	|	it has desktop friendly applications and GUI.	|
|	CentOS is a free downstream rebuild of the commercial Red Hat Enterprise Linux distribution	|	Debian is free upstream distribution that is base for other distributions	|
|	Uses the RPM package format and TUM/DNF as a package manager	|	Uses the DEB package format and dpkg/APT as the package manager	|

### LVM

> In Linux, `Logical Volume Manager` (`LVM`) is a `device mapper` framework that provides `logical volume management` for the  Linux kernel. *Most modern Linux distributions are LVM-aware to the point of being able to have their `root ffile system` on a `logical volume`.*
>
> LVM is used for the following purposes:
>
> -	Creating sigle `logical volume` of multiple physical voumes or entire  hard disks, allowing for dynamic volume resizing.
> - Managing large hard disk farms by allowing disks to be added and replaced without downtime or service disrution, in combination with how swapping.
> - **On small systems (like a desktop), instead of having to estimate at installation time how big a partition might need to be, `LVM` allows filesystems to be easily resized as needed.**
> - Performing consistent backups by taking snapshots of the logical volumes.
> - `Encrypting` multiple `physical partitions` with one password.
>
> `LVM` can be considered as a thin software layer on top of the hard disks and partitions, which creates an abstraction of continuity and ease-of-use for managing hard drive replacement, repartitioning and backup.
