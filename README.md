<h1>* README *<br>
** JUNIPER JNCIP-DC EVPN/VXLAN &amp; CONFIGS **</h1>

This series of configurations were configured for the JUNIPER JNCIP-DC examination topics. They may be used to assist in studies or for production deployment assistance.

<b>HARDWARE | SOFTWARE SPECIFICATIONS </b><p>
<i> Virtualized Network Devices:</i>
<ul>
<li>Vendor:: Juniper</li>
<li>Model:: vQFX<</li>
<li>OS Version:: Junos: 18.4R1.8</li>
</ul><p>
<i>Virtualization Platform:: </i>
<ul>
<li>Application: EVE-NG PROFESSIONAL</li>
<li>Version: 5.0.1-20-PRO, QEMU 2.4.0</li>
</ul>
<p>
<i>System Hardware/Environment:</i>
<ul>
<li>Host: 	EVE-NG Kernel: 4.20.17-eve-ng-ukms+ x86_64 (64 bit) Console: tty 2 Distro: Ubuntu 16.04 xenial</li>
</ul>
<i>Machine Details:</i>
<ul>
<li>System: 	  LENOVO product: 30B5005XUS v: ThinkStation P510</li>
<li>Mobo: 	    LENOVO model: 102F Bios: LENOVO v: S00KT40A date: 05/04/2017</li>
<li>CPU:       	Hexa core Intel Xeon E5-1650 v4 (-HT-MCP-) speed/max: 1809/4000 MHz</li>
<li>Graphics:  	Card: NVIDIA GP106GL [Quadro P2000], Display Server: N/A driver: N/A tty size: 160x46 Advanced</li>
<li>Network:   	Card: Intel Ethernet Connection (2) I218-LM driver: e1000e</li>
<li>Drives:    	HDD Total Size: 1024.2GB<br></li>
</ul>
<i>Memory:</li><br>     
<li>Array-1 capacity: 1 TB (check) devices: 8 EC: Multi-bit ECC<br></li>
<li>Device-1: DIMM_1 size: 8 GB speed: 2400 MHz type: DDR4<br></li>
<li>Device-3: DIMM_3 size: 8 GB speed: 2400 MHz type: DDR4<br></li>
<li>Device-5: DIMM_2 size: 16 GB speed: 2400 MHz type: DDR4<br></li>
</ul>
<p>
This lab is based on a bare metal install of the EVE-NG Community Edition. It may be run within VMWare Workstation and other hypervisors. Resource utilization, on above server specifications, for this lab/system:

<p><blockquote>
  CPU: 		    17%<br>
  MEM: 		    32%<br>
  SWAP: 	    2%<br>
  QEMU Nodes: 24<br>
  VPCS Nodes: 12<br>
</blockquote>
<p>

<b>// CODE REQUIREMENTS \\</b>

To obtain the JUNOS code, you will need to create an account at <a target=_blank href="HTTPS://WWW.JUNIPER.NET" rel="nofollow">HTTPS://WWW.JUNIPER.NET</a>. Virtual code contains certain restrictions and is regulated by the vendor.
<p>
<b>//// LAB DESCRIPTION \\\\</b><p>
This topology contains a CLOS network topology with super spine to show expansion of east-west traffic in a data center. It's deployment uses eBGP for the underlay, iBGP for the overlay, and EVPN/VXLAN to provide connectivity across the Layer 3 transport. In the underlay, eBGP may be substituted with nearly any routing protocol as long as you are able to advertise the loopback interfaces for use in the overlay. 
<p>
<i>Lab Details:</i>
<p>
  <b><i>Management interfaces:</i></b>
<ul>
  <li>CSR1: 192.168.21.101<br></li>
  <li>CSR2: 192.168.21.102<br></li>
  <li>CSR3: 192.168.21.103<br></li>
  <li>CSR4: 192.168.21.104<br></li>
  <li>CSR5: 192.168.21.105<br></li>
  <li>CSR6: 192.168.21.106<br></li>
  <li>CSR7: 192.168.21.107<br></li>
  <li>CSR8: 192.168.21.108<br></li>
  <li>CSR9: 192.168.21.109<br></li>
  <li>CSR10: 192.168.21.110<br></li>
  <li>CSR11: 192.168.21.111<br></li>
  <li>CSR12: 192.168.21.112<br></li>
 </ul>
<p>
  <b><i>Subnet IP Scheme:</i></b>
<ul>
  <li>WAN Links: 172.16.255.0/24 (Subdivide to /30)</li>
  <li>Loopback Interfaces: 10.255.255.0/24 (Subdivide to /32)</li>
  <li>VLANs: 192.168.0.0/16 (Subdivide to /24)</li>
</ul>
<p>
<b><i>BGP ASN Assignment:</i><b>
<ul>
  <li>OVERLAY ASN: 65100</li><br>
  <li>UNDERLAY ASN:</li>
      <li>CSR1:  65001</li>
      <li>CSR2:  65002</li>
      <li>CSR3:  65103</li>
      <li>CSR4:  65104</li>
      <li>CSR5:  65105</li>
      <li>CSR6:  65106</li>
      <li>CSR7:  65107</li>
      <li>CSR8:  65208</li>
      <li>CSR9:  65209</li>
      <li>CSR10: 65210</li>
      <li>CSR11: 65211</li>
      <li>CSR12: 65212</li>
   </li>
 </ul>
 <p>
<b><i>Lab User Accounts (username / password)</b></i>
  <ul>
    <li>root / abc123</li>
    <li>admin / abc123</li>
  </ul><p>
<b>//// VENDOR GUIDES \\\\</b>
<p><a target=_blank href="https://support.juniper.net" rel="nofollow">Juniper Support </a></p>
<p><a target=_blank href="https://learningportal.juniper.net" rel="nofollow">Juniper Learning Portal</a></p>
<p><a target=_blank href="https://www.eve-ng.net/index.php/documentation/" rel="nofollow">EVE-NG Documentation</a></p>

<b>//// LAB IMAGE \\\\</b>
![Juniper-JNCIP-DC_Topology](https://user-images.githubusercontent.com/40407552/183499239-0d10b60e-1545-442d-ace8-9a0884e1f88a.png)
