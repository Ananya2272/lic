# Expriment-1 <br>
**Differential Amplifier**

**Introduction**

<p> A differential amplifier is a type of electronic amplifier that amplifies the difference between two input voltages while rejecting any signals that are common to both inputs .For each differential amplifier we begin with qualitative analysis and Intuitive analysis . we assume perfect symmetry.</p><br>


**Aim**<br>
<p> Design differential amplifier for the following specifications </p><br>
<p>Vdon = 3.3v</p><br> <p>P<=3mw</p><br> <p>Vincm=1.72v</p><br> <p>Vocm=1.81v</p><br> <p>Vp=0.7v</p><br>
<p>perform DC analysis,Transient analysis and AC analysis and extract the required parameters</p><br>

**Circuit-1 with resistor**

**diagram**<br>



**Procedure**<br>
<p>Connect the circuit as shown above. In this circuit Resistor is connected at the source terminal.Consider the given parameters and calculate Iss,ID1,ID2,Rdand Rss.length of the MOSFET is 180nm.</p><br>

**Calculations**

<p>Iss=P/V= 3mw/3.3v= 0.909mA is the tail current .</p><br>
<p> ID1=ID2=Iss/2=0.454mA.</p><br>
<p> RD= Vdd-Vocm/ID= 3.3-1.8/0.454mA = 3.3kohms .</p><br>
<p> Rss = Vp/Iss = 0.7/0.909mA = 770ohms.</p><br>


# DC Analysis 

![Image](https://github.com/user-attachments/assets/ae6096de-da97-4383-906f-ba466761ce9d)

<p>The length of the MOSFET is 180nm. We need to adjust the width to get the desired Q point  we have already calculated the parameters.We got W=0.279u.Now select DC op pnt in edit simulation and check if ID1=Id2 , and Vout as expected. </p>
