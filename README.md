<h1>CMOS Characterization</h1>


<h2>Description</h2>
This project investigates the fundamental circuitry behind logic gates and their dynamic characteristics by using and understanding the basic structure of CMOS transistor logic. Theory, LTSpice, Analog Discovery multi-function instrument, an analog multimeter, and Excel were used in order to study CMOS circuits including a CMOS inverter. Analyzing the waveforms of the CMOS Inverter circuit, establishing operating points Q, finding the transfer characteristic gain, and determining the noise margins for each transistor will help to achieve a clear understanding of each digital circuit.
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
  The circuit was built on a breadboard, and the voltage was varied in steps from 0V to 5V using a waveform generator while measuring the corresponding Vout with an oscilloscope.</p><br>
  <p align="center">
  <img src="https://i.imgur.com/8CATQZ0.jpg" height="80%" width="80%" alt="CMOS Inverter Breadboard"/><br>
  <b>Breadboard CMOS Inverter Circuit</b></p><br><br>
  <p align="left">
  The recorded measurements were plotted in Excel to obtain the voltage transfer characteristic of the CMOS Inverter. The slope of the transfer characteristic around the point Qn and Qp were designated by a red line in the saturation area, which represents the transfer characteristic gain. The noise margins were also determined from the plot to compare with calculated values.</p><br><br>
  <p align="center">
  <img src="https://i.imgur.com/0eri7G5.png" height="80%" width="80%" alt="Voltage Transfer Characteristic CMOS Inverter"/></p><br><br>
  <p align="left">
  Equation Obtained: <b>y= -31.55x + 82.637</b><br>
  <b>Gain</b> = Slope = <b>-31.55V/V</b><br>
  <br>
  Calculation of Noise Margins from Plot:<br>
  <b>NMh</b> = Voh – Vih = 5V-2.7V = <b>2.3V</b><br>
  <b>NMl</b> = Vil – Vol = 2.2V-0V = <b>2.2V</b><br>
  <br>
  The CMOS Inverter was built in LTSpice, and a DC sweep was simulated to get the voltage characteristic plot, as well as the gain and noise margins.</p>
  <p align="center">
  <img src="https://i.imgur.com/10vAB83.png" height="80%" width="80%" alt="CMOS Inverter LTSpice"/><br>
  <b>LTSpice Schematic</b><br><br>
  <img src="https://i.imgur.com/N6mreZv.png" height="80%" width="80%" alt="CMOS Inverter LTSpice Plot"/><br>
  <b>LTSpice Simulation and Voltage Transfer Characteristic Plot</b></p><br><br>
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
  <br />
<p align="center">
<b>Determine the Propagation Delay(tp), Power Dissipation(PD), and the Delay-Power Product(DP)</b></<br><br><br/>
  <p align="left">
  The propagation delay, power dissipation, and the delay-power product were calculated as follows:<br><br>
  <b>Propagation Delay</b> = tp = 0.5(tPHL + tPLH)<br>
  <br>
  High-to-Low Propagation Delay = tPHL = αnCload/k’n(W/L)Vdd * Assume λ=0<br>
  Low-to-High Propagation Delay = tPLH = αpCload/k’p(W/L)Vdd * Assume λ=0<br>
  <br>
  αn = αp = 1.7<br>
  Vdd = 5V<br>
  Cload = 90pF<br>
  k’n(W/L) = 0.759mA/V^2<br>
  k’p(W/L) = 0.33mA/V^2<br>
  <br>
  tPHL = (1.7)(90x10^-12F)/(0.759x10^-3A/V^2)(5V) = 40.32ns<br>
  tPLH = (1.7)(90x10^-12F)/(0.33x10^-3A/V^2)(5V) = 92.73ns<br>
  <br>
  <b>tp</b> = 0.5(40.32ns + 92.73ns) = <b>66.53ns</b><br>
  <br>
  <b>Power Dissipation</b> = <b>PD</b> = Cload*Vdd*f = (90x10^-12F)(5V)(1000Hz) = <b>2.25µW</b><br>
  <br>
  <b>Delay-Power Product</b> = <b>DP</b> = PD*tp = (2.25x10^-6J/s)(66.53x10^-9s) = <b>0.1497pJ</b><br>
  <br>
  <br>
  A square wave input signal of 0V to 5V at 1kHz frequency was applied to the circuit using a waveform generator, and the outputs and inputs were measured using an oscilloscope.</p>
  <br />
  <br />
  <p align="center">
  <img src="https://i.imgur.com/GV8oLlI.png" height="80%" width="80%" alt="ADK Oscilloscope"/><br>
  <b>Oscilloscope Reading</b><br><br></p>
  <p align="left">
  The fall delay time(tf), and rise delay time (tr) for the input and output voltage were recorded and used to calculate high-to-low propagation delay (tpHL), low-to-high propagation delay     
  (tPLH), and propagation delay (tp). The calculations were as follows:<br><br>
  trVin = 48.34ns<br>
  tfVin = 91.14ns<br>
  trVout = 86.28ns<br>
  tfVout = 42.07ns<br>
  <br>
  <b>tPLH</b> = 0.5(tfVin + trVout) = 0.5(91.14ns+86.28ns) = <b>88.71ns</b><br>
  <b>tPHL</b> = 0.5(trVin + tfVout) = 0.5(48.34ns+42.07ns) = <b>45.205ns</b><br>
  <br>
  <b>Propagation Delay</b> = <b>tp</b> = 0.5(tPLH + tPHL) = 0.5(88.71ns+45.205ns) = <b>66.958ns</b><br>
  <br>
  <br>
  The circuit was then simulated using a transient analysis in LTSpice, and the values of tpHL, tpLH, tr, tf, and tp were determined.</p><br>
  <p align="center">
  <img src="https://i.imgur.com/ZR0qRRY.png" height="80%" width="80%" alt="LTSpice Transient Analysis"/><br>
  <b>LTSpice Transient Analysis and Data Log File</b></p><br><br>
  <p align="left">
  The <b>propagation delay</b> for this simulation was <b>55.36ns</b>.</p>
  <br />
  <br />
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
