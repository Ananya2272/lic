#Expriment-1 <br>

**DC ,AC,Transient Analysis of Common Source Amplifier**

![Image](https://github.com/user-attachments/assets/9b7890b9-35e5-4e4b-8d58-871e2d13037b)

**1. Itroduction**
<p>
  In this experiment we do the Dc, Ac and Trancient analysis of the Common Source Amplifier. In this analysis we determine the DC biasing conditions , in Ac analysis we determine frequency response and in Transient analysis we determine gain and output. 
</p> <br>

**1.1 Components**
<p>
  This circuit consist of TSMC 180nm NMOS transistor (CMOSN) , drain resistor and voltage sources (V1 & V2) . 
  
**MOSFET length** : 180nm
**MOSFET width** : 0.2um
**Threshold voltage** : 0.36v
**Resistor** : 2.72k
**Supply voltage** : 1.8v
**Sgnal generator** : 
DC voltage :0.9v
Amplitude : 50mv
Frequency : 1KHz
</p><br>

**Procedure**

**1.2 DC Analysis**

![Image](https://github.com/user-attachments/assets/bc06afac-fd32-41b2-8125-d9cfa63907a3)
![Image](https://github.com/user-attachments/assets/5633f39b-564e-407a-910c-852ad87c4e54)


  From the analyis 

  Vout : 1.649v<br>
  Vin : 0.9v<br>
  Id : 
  <p>
  If the power dissipiation is 100um across the resistor , then the current through the resistor is given by<br>
  Id : power/Voltage = 100um/1.8 = 55.5um <br>

  The output load line equation is given by <br>
  Vout = Vdd-(Id-Rd)<br>
  Rd= (1.8-1.649)/55.5um<br>
  =2.72k ohms  <br>
  </p> <br>
<p>
  Now replace the resistor value by Rd = 2.72k ohms . since the calculated current does not match the simulated value maintain the mosfet length at 180nmby adjusting the width to get the desired current value.
</p><br>

<table>
  <tr>
    <td>Length</td>
    <td>Width</td>
    <td>Id</td>
  </tr>
  <tr>
    <td>180nm</td>
    <td>1um</td>
    <td>0.000148351</td>
  </tr>
  <tr>
  <td>180nm</td>
  <td>0.1um</td>
  <td>4.76342e-05	</td>
  </tr><br>
  <tr>
    <td>180nm</td>
    <td>0.19</td>
    <td>5.36419e-05	</td>
  </tr>
  
  <tr>
    <td>180nm</td>
    <td>0.21um</td>
    <td> 5.56616e-05</td>
  </tr>
</table><br>

<p>
  This DC operating point analysis confirms that NMOS operates in saturation region.<br>
  Vds = Vd-Vs= -0 =   <br>
  Vov = Vgs-Vth= 0.9-0.36= 0.54v<br>
  Vds>(Vgs-Vth)<br>
</p>



**1.3 AC analyis**

![Image](https://github.com/user-attachments/assets/4ec74b10-9171-4e79-84a1-7c68abb2483f)


<p>
  In AC analysis we determine the frequency response by applying the small signal analysis to the circuit . We do this analysis to check in which frequency the circuit acts as the linear amplifier.
  For type of sweep we select 'decade', starting frequency as 0.1Hz and stop frequency as 1THz.

  
</p><br>

**1.4 Transient Analysis**

![Image](https://github.com/user-attachments/assets/b3846411-67a7-4c9a-a889-fe92c9c556ac)


<p>
  In this analysis we determine the gain of the circuit. for input give sinusoidal voltage signal where the DC offset is 0.9v peak voltage Vpeak is 50mv, Frequency is 1kHz and Ac amplitude is 1v.select the stop time to 3ms.
</p><br>
<p>
  From the obtained output graph we can calculate the gain . 
</p><br>
<p>
  Gain = Vin/Vout<br>
  Av=   <br>
  This matches the theoritical value which is calculated by Av = gmRd.<br>
  where gm= KnVov<br>
  From the graph we can observe that there is 180 degree phase shift which is exhibited by Common Source Amplifier.
  
</p><br>









