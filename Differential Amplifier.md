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

![Image](https://github.com/user-attachments/assets/e92e56c2-a737-4d3d-a48c-a9fb6b0bcbf4)

<p>The length of the MOSFET is 180nm. We need to adjust the width to get the desired Q point  we have already calculated the parameters.We got W=0.279u.Now select DC op pnt in edit simulation and check if ID1=Id2 , and Vout as expected. </p><br>

# Transient Analysis

<p> Now in edit simulation select transient analysis and select sine wave and give DC offset value as 1.72v on both side and observe the Waveform.</p>

![Image](https://github.com/user-attachments/assets/376c4983-486d-4cb5-bcdf-e59c2dd3d7ee)

<p> To perform transient analysiswe need to find the swing .Find Vincm maximum and minimum and take its average .</p><br>
<p> Vincm (max)= Vt+Vp = 0.36+0.7 = 1.06v</p><br>
<p> Vincm (min) = Vdd-RD*Iss/2+Vt = 2.169v</p><br>
<p> swing = 1.06+2.169/2 = 1.64 .</p><br>
<p> Now in edit simulation select transient analysis and select sine wave and give DC offset value as 1.614 on both side and observe the Waveform. </p><br>

![Image](https://github.com/user-attachments/assets/25327a71-ab3a-46cb-8369-b280a5c5ea69)

<p> here the wave is clamped. </p><br>

# AC analysis 

![Image](https://github.com/user-attachments/assets/30fb14dd-be5d-4684-9240-20f9ff9829df)

<p> To perform AC analysis we need to select ac analysis in the edit simulator . and select the decade.Find the gain and observe the waveform obtained.</p><br>

![Image](https://github.com/user-attachments/assets/3c18195b-45b7-4535-93e0-93ec934f1a6f)
![Image](https://github.com/user-attachments/assets/36d17936-9595-46af-8097-68ce7cc9283f)

<p> Here we got BW= 10.16.</p><br>
<p> dB=13.08</p><br>

# Circuit-2 using current source

**Circuit**
![Image](https://github.com/user-attachments/assets/7dea724c-1209-4361-87bb-86d72e8e0a5e)

<P> Replece the resistor with a Current source and apply the value we obtained earlier (0.909mA) . It is also called as tail current. Current flowing from ID1 & ID2 must be equal to Iss. </P><br>

# DC analysis

![Image](https://github.com/user-attachments/assets/43161068-a219-42e9-a61d-5ad250f62af2)
<p>The length of the MOSFET is 180nm. We need to adjust the width to get the desired Q point  we have already calculated the parameters.We got W=0.279u.Now select DC op pnt in edit simulation and check if ID1=Id2 , and Vout as expected.  </p><br>

# Transient analysis

![Image](https://github.com/user-attachments/assets/d525ebba-f689-4445-8575-d8c03e0dcccb)

<p>  Now in edit simulation select transient analysis and select sine wave and give DC offset value as 1.72v on both side and observe the Waveform.Give 180degree to one MOSFET and 0 degree to another MOSFET.ac AMPLITUDE AS 1V.</p><br>

# AC analysis

![Image](https://github.com/user-attachments/assets/d5aeb0fe-a602-4fd3-b925-19eb10c63584)

<p>  To perform AC analysis we need to select ac analysis in the edit simulator . and select the decade.Find the gain and observe the waveform obtained.
<p> the gain is increased because it raises the output resistance.</p><br>

# Circuit -3 with NMOSFET at source terminal
**Circuit**

![Image](https://github.com/user-attachments/assets/50c1ccd4-c51c-46fe-8e97-1cb364f139b5)


<p>Replace the current source with a NMOS at the source terminal .</p><br>

# DC analysis


# Transient analysis


# AC analysis

![Image](https://github.com/user-attachments/assets/4b8ac0e1-213c-4aad-a59f-9cc1b5b12828)


# Result 
<p> 1. Iss=0.909mA</p><br>
<p> 2.ID=ID1=ID2= 0.454mA</p><br>
<p> 3.RD=3.3kohm</p><br>
<p> 4.Rss= 770ohm</p><br>
<p> 5.Av = 4.412</p><br>
<p> 6.dB= 13.08</p><br>
<p> 7.BW = 10.5-0.34=10.16</p><br>

# Inference

<p> 1. We must make sure that both transistors are symmetric.</p><br>
<p> 2. The gain changes in each circuit because of the output resistance.</p><br>
<p> 3. The current source enhances common-mode rejection, making the amplifier more effective at rejecting noise and interference.</p><br>
<p> 4. The DC operating point remains almost same in all the circuits </p><br>
<p> 5. Resistor limits the gain and current source stabilizes gain.</p><br>
<p> 6. Replacing gain affects the gain ,biasing and input impedence.</p><br>
















