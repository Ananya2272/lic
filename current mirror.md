## Experiment -6 

**Aim : Design a current mirror circuit which has a gain of AV = -10V/V, power supply of Vdd = 1.8V, and power of P <= 1mW. Find reference current (Iref), output current (Id), and total current (Itotal). Perform DC and AC analysis for mirror ratio 1:1, 1:2. Vary length from 180nm -> 500nm -> 1µm and do the analysis.** <br>

**Introduction to Current Mirror**<br>

 <p> The current mirror circuits are simple current sources which gives constant current. The current mirror circuits are based on the principle that, if the gate to source voltage of two identical MOSFETs are equal then the drain current flowing through them is equal. The basic current mirror circuit is shown in Figure below.</p>

 ![Image](https://github.com/user-attachments/assets/a7293d41-62b4-46a2-8ce7-5bcd00543125)

 <ins>Observed Table</ins> <br>
For I<sub>ref</sub> = 100u <br>

  <table> 
<tr>
 <th><b>I<sub>out(expected)</sub>(A)</b></th>
 <th><b>I<sub>out(appeared)</sub>(A)</b></th>
 <th><b>(W/L)<sub>2</sub>(m)</b></th>
 <th><b>(W/L)<sub>1</sub>(m)</b></th>
 <th><b>V<sub>x</sub>(V)</b></th>
 <th><b>V<sub>out</sub>(V)</b></th>
</tr>
<tr>
    <td>100µ</td>
    <td>103.5µ</td>
    <td>(180n/180n)</td>
    <td>(180n/180n)</td>
    <td>1.275V</td>
    <td>1.715V</td>
</tr>
<tr>
    <td>100µ</td>
    <td>100.715µ</td>
    <td>(500n/500n)</td>
    <td>(500n/500n)</td>
    <td>1.4375V</td>
    <td>1.717V</td>
</tr>
<tr>
    <td>100µ</td>
    <td>100.648µ</td>
    <td>(1µ/1µ)</td>
    <td>(1µ/1µ)</td>
    <td>1.3972V</td>
    <td>1.71747V</td>
</tr>
<tr>
    <td>200µ</td>
    <td>197.637µ</td>
    <td>(1µ/1µ)</td>
    <td>(1µ/2µ)</td>
    <td>1.397V</td>
    <td>1.637V</td>
</tr>
    <tr>
      <td>50µ</td>
    <td>52.13µ</td>
    <td>(1µ/1µ)</td>
    <td>(1µ/0.5µ)</td>
    <td>1.3972V</td>
    <td>1.75725V</td>
    </tr>
    <tr>
      <td>100µ</td>
    <td>101.539µ</td>
    <td>(1µ/2µ)</td>
    <td>(1µ/2µ)</td>
    <td>1.08762V</td>
    <td>1.71674V</td>
    </tr>
     <tr>
      <td>100µ</td>
    <td>102.131µ</td>
    <td>(1µ/3µ)</td>
    <td>(1µ/3µ)</td>
    <td>0.95619V</td>
    <td>1.71625V</td>
    </tr>
</table> 
<br>

**Part - A**

## Case-1
**180nm**<br>
*1:1 aspect ratio**<br>
## DC analysis

<p> Vdd=1.8v</p><br>
<p> P <= 1mw</p><br>
<p> I = P/V = 1/1.8 = 0.55mA</p><br>
<p>ID1=ID2= 0.277mA</p><br>


![Image](https://github.com/user-attachments/assets/ab20f49b-39cb-4204-8bd2-152356b42753)

![Image](https://github.com/user-attachments/assets/e8508c33-aa2b-4eed-a81f-95e4393dcfb5)



 <table> 
<tr>
 <th><b>Parameters</b></th>
 <th><b>MOSFET1</b></th>
 <th><b>MOSFET2</b></th>
 <th><b>MOSFET3</b></th>
</tr>
<tr>
    <td>Model</td>
    <td>CMOSP</td>
    <td>CMOSP</td>
    <td>CMOSN</td>
</tr>
<tr>
    <td>Mosfet Length</td>
    <td>180nm</td>
    <td>180nm</td>
    <td>180nm</td>
</tr>
<tr>
    <td>Mosfet Width</td>
    <td>10µm</td>
    <td>10µm</td>
    <td>114.025µm</td>
</tr>

   <tr>
      <td>Current(I)</td>
      <td> I<sub>ref</sub> = 0.227mA </td>
      <td> I<sub>d</sub> = 0.227mA </td>
      <td> I<sub>d</sub> = 0.227mA </td>
    </tr>
    <tr>
      <td>Supply Voltage</td>
      <td> 1.8V</td>
      <td> 1.8V</td>
      <td> --- </td>
    </tr>
     <tr>
      <td>Biased Voltage</td>
      <td> --- </td>
      <td> --- </td>
      <td> 0.500V</td>
    </tr>
</table>
<br>

## Transient Analysis 


