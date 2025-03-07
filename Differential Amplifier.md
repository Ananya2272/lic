# Expriment-3<br>
**Differential Amplifier**

**Introduction**

<p> A differential amplifier is a type of electronic amplifier that amplifies the difference between two input voltages while rejecting any signals that are common to both inputs .For each differential amplifier we begin with qualitative analysis and Intuitive analysis . we assume perfect symmetry.</p><br>


**Aim**<br>
<p> Design differential amplifier for the following specifications </p><br>
<p>Vdon = 3.3v</p> <p>P<=3mw</p> <p>Vincm=1.72v</p>  <p>Vocm=1.81v</p> <p>Vp=0.7v</p><br>
<p>perform DC analysis,Transient analysis and AC analysis and extract the required parameters</p><br>

# Circuit-1 with resistor

**Circuit diagram**

![Image](https://github.com/user-attachments/assets/e82f931d-6a29-4944-b969-c493c1310631)


**Procedure**<br>
<p>Connect the circuit as shown above. In this circuit Resistor is connected at the source terminal.Consider the given parameters and calculate Iss,ID1,ID2,Rdand Rss.length of the MOSFET is 180nm.</p><br>

# Calculations

<p>Iss=P/V= 3mw/3.3v= 0.909mA is the tail current .</p><br>
<p> ID1=ID2=Iss/2=0.454mA.</p><br>
<p> RD= Vdd-Vocm/ID= 3.3-1.8/0.454mA = 3.3kohms .</p><br>
<p> Rss = Vp/Iss = 0.7/0.909mA = 770ohms.</p><br>


# DC Analysis 
![Image](https://github.com/user-attachments/assets/e9bb2d34-cbd8-4dbe-9b62-9143b0bf01e5)

![Image](https://github.com/user-attachments/assets/31e6b951-59d0-45fd-8de9-0f5b96ee49e4)


<p>The length of the MOSFET is 180nm. We need to adjust the width to get the desired Q point  we have already calculated the parameters.We got W=0.249u.Now select DC op pnt in edit simulation and check if ID1=Id2 , and Vout as expected. </p><br>

**Increase Vicm from 1.72v to +or- 5mv and observe Vocm and Vp** <br>
| **Common-Mode Input Voltage (V_ICM)** | **Output Voltage (V_out)** | **Voltage at Point P (V_P)** |
|--------------------------------------|--------------------------|--------------------------|
| **1.72V**                            | **1.8101v**             | **0.699524	V**                |
| **2.25vV**                            | **1.27156v**                 | **0.952378v**               |
| **1.25v**                              | ** 2.40145v**              | **0.42188v**                |

<p> As we increase Vincm Vout decreases and Vp increasesand Vp increases if we increase Vincm and decreases if we decrease .This causes increase in Id and shift in operating point. </p>


# Transient Analysis

<p> Now in edit simulation select transient analysis and select sine wave and give DC offset value as 1.72v on both side and observe the Waveform.</p>

![Image](https://github.com/user-attachments/assets/27c0382a-9f2a-4e71-aaa1-0ce45b607d1a)

<p> To perform transient analysiswe need to find the swing .Find Vincm maximum and minimum and take its average .</p><br>
**Input swing**
<p> Vincm (min)= Vt+Vp = 0.36+0.7 = 1.06v</p><br>
<p> Vincm (max) = Vdd-RD*Iss/2+Vt = 2.169v</p><br>
<p> swing = 1.06+2.169/2 = 1.614v .</p><br>

**Output swing**
<p> Voutcm(max) =Vdd-IDRd= 1.81v</p><br>
<p>Voutcm(min) = Vgs-Vt+Vp= 1.36v</p><br>
<p>swing = 1.81+1.36/2=1.585v</p><br>
<p> Now in edit simulation select transient analysis and select sine wave and give DC offset value as 1.614 on both side and observe the Waveform. </p><br>

![Image](https://github.com/user-attachments/assets/25327a71-ab3a-46cb-8369-b280a5c5ea69)



# AC analysis 

![Image](https://github.com/user-attachments/assets/30e5ee5b-0e8f-478f-ba3b-3d2954a70e0c)

<p> To perform AC analysis we need to select ac analysis in the edit simulator . and select the decade.Find the gain and observe the waveform obtained.</p><br>

![Image](https://github.com/user-attachments/assets/3c18195b-45b7-4535-93e0-93ec934f1a6f)

<p> Here we got BW= 10.5-0.34= 10.16.</p><br>
<p> 3db = 20log(4.512)</p><br>
<p> 3dB=13.08</p><br>

# Circuit-2 using current source

**Circuit**
![Image](https://github.com/user-attachments/assets/7dea724c-1209-4361-87bb-86d72e8e0a5e)

<P> Replece the resistor with a Current source and apply the value we obtained earlier (0.909mA) . It is also called as tail current. Current flowing from ID1 & ID2 must be equal to Iss. </P><br>

# DC analysis
![Image](https://github.com/user-attachments/assets/41364184-17aa-4aa6-8ef0-2edb81707694)

<p>The length of the MOSFET is 180nm. We need to adjust the width to get the desired Q point  we have already calculated the parameters.We got W=0.279u.Now select DC op pnt in edit simulation and check if ID1=Id2 , and Vout as expected.  </p><br>

# Transient analysis

![Image](https://github.com/user-attachments/assets/d525ebba-f689-4445-8575-d8c03e0dcccb)


<p>  Now in edit simulation select transient analysis and select sine wave and give DC offset value as 1.72v on both side and observe the Waveform.Give 180degree to one MOSFET and 0 degree to another MOSFET.ac AMPLITUDE AS 1V.</p><br>
<p> Now calulate the swing and observe the waveform.</p><br>

![Image](https://github.com/user-attachments/assets/ce247221-e01b-435a-bc0e-bc6f08e0748f)

# AC analysis

![Image](https://github.com/user-attachments/assets/d5aeb0fe-a602-4fd3-b925-19eb10c63584)

<p>  To perform AC analysis we need to select ac analysis in the edit simulator . and select the decade.Find the gain and observe the waveform obtained.
<p> the gain is increased because it raises the output resistance.</p><br>

# Circuit -3 with NMOSFET at source terminal
**Circuit**

![Image](https://github.com/user-attachments/assets/50c1ccd4-c51c-46fe-8e97-1cb364f139b5)


<p>Replace the current source with a NMOS at the source terminal .</p><br>

# DC analysis
![Image](https://github.com/user-attachments/assets/3aec564f-d3db-4f1d-a146-6b4545750849)
# DC sweep

![Image](https://github.com/user-attachments/assets/eb822faa-4efa-47ac-a4fb-55b383fef7a6)

# Transient analysis

![Image](https://github.com/user-attachments/assets/556b17e9-2a21-4072-addb-0d4ce1b65a9e)



# AC analysis

![Image](https://github.com/user-attachments/assets/4b8ac0e1-213c-4aad-a59f-9cc1b5b12828)


# Result 


# Inference

<p> 1. We must make sure that both transistors are symmetric.</p><br>
<p> 2. The gain changes in each circuit because of the output resistance.</p><br>
<p> 3. The current source enhances common-mode rejection, making the amplifier more effective at rejecting noise and interference.</p><br>
<p> 4. The DC operating point remains almost same in all the circuits </p><br>
<p> 5. Resistor limits the gain and current source stabilizes gain.</p><br>
<p> 6. Replacing current source with NMOS affects the gain ,biasing and input impedence.</p><br>
















