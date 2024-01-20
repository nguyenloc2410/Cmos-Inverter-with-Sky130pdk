# Cmos-Inverter-with-Sky130pdk
---
## Introduction
This is my first personal project using Sky130 for the purpose to research about MOSFET, CMOS Inverter.Hopefully if you have any question just mail to me "tanlocnguyen2410@gmail.com"
---
## Parts of project
- [1. Tool and PDK Setup](#1-Tools-and-PDK-Setup)
  - [1.1 Tools Setup](#11-Tools-setup)
  - [1.2 PDK Setup](#12-PDK-setup)
- [2. MOSFET Models](#2-MOSFET-Models)
---
## 1. Tools and PDK Setup
### 1.1 Tools setup
For the design and simulation of our Inverter.
- Spice netlist simulation - [Ngspice](http://ngspice.sourceforge.net/)
- Layout Design and DRC - [Magic](http://opencircuitdesign.com/magic/)
- LVS - [Netgen](http://opencircuitdesign.com/netgen/)
- Schematic Capture - [Xschem](http://repo.hu/projects/xschem/)

### 1.2 PDK setup
The PDK we are going to use for this BGR is Google Skywater-130 (130 nm) PDK.
![image](https://repository-images.githubusercontent.com/261898494/aad8d100-9079-11ea-8b72-8f2bc8363e36)


**Steps to download PDK** - Open the terminal and type the following to download sky130 PDK.
```
$  git clone https://github.com/RTimothyEdwards/open_pdks.git
$  cd open_pdks
$  ./configure [options]
$  make
$  [sudo] make install
```
**You should follow the instructions given at [this](http://opencircuitdesign.com/open_pdks/index.html) link**
---
## 2. MOSFET Models
### 2.1 Common characteristics of MOSFET
In this part I going to find Vth(threshold), gm(Transconductance parameter), rds(Linear resistor) by plot Ids vs Vds and Ids vs Vgs with NMOS_1V8 circuit below:

![NMOS CHAR SCHEMATIC](./Images/nfet_circuit.png)

Then you must see the plot below you, if you did a DC sweep on the VGS source for different values of VDS:

![NMOS CHAR SCHEMATIC](./Images/Vgs_Vds_plot_nmos.png)
In reality, the turn-on phenomenon is a gradual function of the gate voltage, making it difficult to define VTH unambiguously. In semiconductor physics, the VTH of an NFET is usually defined as the gate voltage for which the interface is “as much n-type as the substrate is p-type.” It can be proved that 


<div align="center">
<img src="/Images/threshold_formula.png">
</div>


