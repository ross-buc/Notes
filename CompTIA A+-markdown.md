# CompTIA A+
## July 14, 2023 - 09:48 AM
PCIe, or PCI Express (Peripheral Component Interconnect Express), is a high-speed serial computer expansion bus standard designed to replace the older PCI, PCI-X, and AGP bus standards.

The terms "PCIe x1" and "PCIe x16" refer to the different sizes of the slots on a motherboard and the number of lanes they provide for data transfer. The "x" refers to the number of lanes the slot has. So, "x1" has one lane, and "x16" has sixteen lanes.

Here are the key differences:

1. Data Transfer Rate: Since a PCIe x16 slot has 16 lanes for data to flow, it has a higher data transfer rate than a PCIe x1 slot which only has one lane. This can be particularly important in applications where high data bandwidth is required, such as in graphics cards.

2. Physical Size: A PCIe x16 slot is physically larger than a x1 slot. This is because it needs to accommodate more lanes for data transfer. This also means that you can plug a smaller PCIe card (like a x1) into a larger slot (like a x16), but you can't fit a larger PCIe card into a smaller slot.

3. Usage: PCIe x1 slots are often used for devices that don't require high bandwidth, such as sound cards, network cards, or USB expansion cards. On the other hand, PCIe x16 slots are generally used for graphics cards, which require a lot of bandwidth to function optimally.

Network Interface Card (NIC)

SATA uses a 7-pin L-shaped data connector with one device per port. SATA operates at bandwidths of 1.5 Gbps, 3 Gbps, or 6 Gbps. SATA drives can also use a 15-pin power connector. 

CPU Virtualization is a hardware feature found in all current AMD & Intel CPUs that allows a single processor to act as if it was multiple individual CPUs. This allows an operating system to more effectively & efficiently utilize the computer's CPU power to run faster.

An x86 or 32-bit processor can address a maximum of 4GB of RAM

DDR stands for Dual Data Rate

If you see for example PC3-10600 on a DDR memeory stick it usually means the transfer speed measured in MB/s so this stick would have 10,600 MegaBytes per second of throughput

When using a multi channel configurations, use the same model, speed, and throughput of memory

**ECC - Error Correcting Code**
Detects and corrects an error

Non-Parity memory does not check for errors and allows data to be put in or taken out. Cheap to manufacture

Parity memory performs basic error checking and ensures the memory contents reliable

**BIOS** Basic Input/Output System up to 32bit systems

**CMOS** is a battery on the motherboard. It saves the bios settings 

**POST** Power-on Self-Test

**TPM** Provides encrytion and checks the UEFI has not been tampered with and provides a secure boot-up

12v, 5v, 3.3v dc are common voltages found in PCs

RAID 0 Striping of data, has no loss of space on the disks but offers no redundancy

RAID 1 provides mirroring and full redundancy

RAID 5 provides redundancy through parity and is heavily used in servers

RAID 6 Striping with Dual Parity

RAID 10 provides Mirroring and Striping and requires 4 disks

Failure Resistant RAIDS 1 & 5
Protection against the loss of erased data

Fault Tolerant RAIDS 1, 5 ,6. RAID can function even when a component fails

Disaster Tolerant RAID 10, with two independent zones with full data access

Type 1 Hypervisor (Bare Metal)
Runs directly on the host hardware and functions as the operating system.

Type 2 Hypervisor
Runs within the normal operating system

Each virtual machine runs its own operating system

Containerization. Type of virtualization applied by a host operating system to provision an isolated execution environment for an application. Each container relies on a common host OS as the base for each container

 Infrastructure as a Service (IaaS) is a cloud computing service that enables a consumer to outsource computing equipment purchases and running their own data center.

 SaaS - Software as a Service, application, data, runtime, middleware, o/s, virtualization, servers, storage, networking

 PaaS - Platform as a Service, runtime, middleware, o/s, virtualization, servers, storage, networking

 IaaS - Infrastructure as a Service, Virtualization, servers, storage, networking


SDN - Software defined network is broken up into 4 parts. Application layer, Control layer, Infrastructure layer and Management plane

 WAN = Wide Area Network (Countrywide, Worldwide)

 MAN = Metropolitan Area Network (City or Country)

 CAN = Campus Area Network (Campus or Business Park)

 LAN = Local Area Network (Room or Building)

 PAN = Personal Area Network (Around a person)

 SoHo LAN = Small office, Home office local area network. Uses a centralized server or simply provides clients access to local devices like printers, file storage, or the internet

 ### WIFI

 DSSS - Direct Sequence Spread Spectrum, not used very often, non overlaping channels

 FHSS - Frequency hopping spread spectrum, allows devices to hop between predetermined frequenices

OFDM - Orthogonal Frequency Division Multiplexing, multiple channels and frequencies

Channel Bonding - Allows for the creation of a wider channel by merging neighboring channels into one

### Wireless Standards

Need to know the 
- Standard
- Band
- Bandwidth

802.11a = 5 GHz = 54 Mbps

802.11b = 2.4GHz = 11 Mbps

802.11g = 2.4GHz = 54 Mbps

802.11n = 2.4 and 5 GHz = 150 Mbps/600 Mbps

802.11ac = 5 GHz = 3 Gbps

802.11ax = 2.4, 5 and 6 GHz = 9.6 Gbps

### Wireless Security
802.11i

Open = No security or protection

WEP = IV (initialization vectors)

WPA = TKIP and RC4 (weak dont use it)

WPA2 = CCMP and AES (strong and used today)

Good practice to disable SSID

### Fixed Wireless

Wi-fi  (802.11) creates point to point connections between buildings for examples

Cellular - Uses a larger antenna and larger hotspot within an office or home

Microwave - Creates point to point connection between two or more buildings and can transmit further distance than a wifi link

Satellite - long range, usually has a dish faced up towards a satellite in low earth orbit or geosynchronous

### NFC Near Field Communication

Mobile payments

POS point of sale

