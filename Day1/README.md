# Day 1

## Info - Hypervisor Overview
<pre>
- nothing but virtualization 
- with virtualization/hypervisor software, we can run multiple OS side by side on the same laptop/desktop/workstation/server
- there are 2 types of Hypervisors
  1. Type 1 
     - a.k.a Baremetal Hypervisor
     - is used in Workstation & Server
     - performance wise it offers almost near native performance ( 3% less performance as opposed to running a OS on direct H/W )
     - this can be installed directly on top of a H/W with no Operating System
     - examples
       1. VMWare vSphere(vCenter) - Paid
       2. Linux KVM ( opensource & Free )
       3. Microsoft Hyper-V
  2. Type 2
     - a.k.a Hosted Hypervisor
     - this can be installed only top of a Host Operating System ( Windows, Mac OSX, Linux, etc )
     - is used in Workstation, Desktops & Laptops
     - examples
       - Oracle VirtualBox ( Free - Windows/Linux/Mac )
       - VMWare Wokstation ( Free - after Broadcom acquired VMWare - Windows, Linux, Mac )
       - VMWare Fusion ( Mac OS-X - Need a commercial license )
       - Parallels ( Mac OS-X - Need a commercial license )
</pre>
