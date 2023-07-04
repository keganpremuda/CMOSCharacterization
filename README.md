<h1>CMOS Characterization</h1>


<h2>Description</h2>
This project investigates the fundamental circuitry behind logic gates and their dynamic characteristics by using and understanding the basic structure of CMOS transistor logic. Theory, LTSpice, Analog Discovery multi-function instrument, an analog multimeter, and Excel will be used in order to study CMOS circuits including a CMOS inverter, and simple CMOS NAND and NOR gates. Analyzing the waveforms of each circuit, establishing operating points Q, finding the transfer characteristic gain, and determining the noise margins for each transistor will help to achieve a clear understanding of each digital circuit.
<br />


<h2>Equipment Used</h2>

- <b>Analog Discovery 2</b> - Digital waveform generator, oscilloscope, multimeter, etc.
- <b>AstroAI Analog Multimeter</b>

<h2>Environments Used </h2>

- <b>Waveforms</b> - Interface for Analog Discovery 2

<h2>Electrical Components Used</h2>

- <b>CD4007UBE</b> - Complementary Pair Plus Inverter IC 14-PDIP
- <b>Capacitors</b> - 1uF and 100pF
- <b>Breadboard</b>
- <b>Analog Parts Kit</b>

<h2>Program walk-through:</h2>

<p align="center">
<b>CD4007 MOSFET Array Diagram:</b><br><br/>
  <img src="https://i.imgur.com/y9KBwOS.png" height="70%" width="70%" alt="CD4007 Diagram"/>
<br />
<br />
<br />
<b>Determine the Noise Margin, Voltage Transfer Characteristic, and Gain:</b><br/></p>
  <p align="left">
  First, the noise margins were calculated as follows:<br><br>
  kp’(W/L) = 0.33mA/V^2<br>
  kn’(W/L) = 0.7605mA/V^2<br>
  Assume Vtn=|Vtp|=1.0V<br>
  <br>
  Equation – NMh=NMl=(3/8)(Vdd+(2/3)Vt)<br>
  <br>
  <b>NMh</b>=<b>NMl</b>= (3/8)(5V+(2/3)1V) = <b>2.125V</b><br>
  <br>
  The circuit was built on a breadboard, and the voltage was varied in steps from 0V to 5V using a waveform generator while measuring the corresponding Vout using an oscilloscope.</p><br>
  <p align="center">
  <img src="https://i.imgur.com/8CATQZ0.jpg" height="80%" width="80%" alt="CMOS Inverter Breadboard"/></p><br><br>
  <p align="left">
  The measurements recorded were plotted in Excel to obtain the voltage transfer characteristic of the CMOS Inverter. The slope of the transfer characteristic around the point Qn and Qp were designated by a red line in the saturation area, which represents the transfer characteristic gain. The noise margins were also determined from the plot to compare with calculated values.</p><br><br>
  <p align="center">
  <img src="https://i.imgur.com/0eri7G5.png" height="80%" width="80%" alt="Voltage Transfer Characteristic CMOS Inverter"/></p><br><br>
  <p align="left">
  Equation Obtained: y= -31.55x + 82.637<br>
  Gain = Slope = -31.55V/V<br>
  <br>
  Calculation of Noise Margins from Plot:<br>
  <b>NMh</b> = Voh – Vih = 5V-2.7V = <b>2.3V</b><br>
  <b>NMl</b> = Vil – Vol = 2.2V-0V = <b>2.2V</b><br>
  <br>
  The CMOS Inverter was built in LTSpice, and then a DC sweep was simulated to get the voltage characteristic plot, as well as the gain and noise margins.</p>
  <p align="center">
  <img src="https://i.imgur.com/10vAB83.png" height="80%" width="80%" alt="CMOS Inverter LTSpice"/><br><br>
  <img src="https://i.imgur.com/N6mreZv.png" height="80%" width="80%" alt="CMOS Inverter LTSpice Plot"/></p><br><br>
  <p align="left">
  <b>Gain</b> = Slope = <b>-27.6917V/V</b><br>
  <br>
  Calculation of Noise Margins from LTSpice Plot:<br>
  <b>NMh</b> = Voh – Vih = 5V-3.0V = <b>2.0V</b><br>
  <b>NMl</b> = Vil – Vol = 2.35V-0V = <b>2.35V</b><br>
  <br>
<br />
<br />
<br />
<b>Determine the Propagation Delay(tp), Power Dissipation(Pd), and the Delay-Power Product(DP)</b><br><br/>
  <img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
