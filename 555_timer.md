# Monostable multivibrator using 555 timer IC .
## Aim
### Generate pulse of width 0.5 ms using input triggers.
A monostable multivibrator is an electronic circuit that has one stable state and one temporary (quasi-stable) state. It remains in its stable state until an external trigger pulse is applied, upon which it switches to the quasi-stable state for a fixed period of time and then automatically returns to its stable state. This circuit is commonly used for generating precise time delays, single pulses, and debouncing mechanical switches. The duration of the output pulse is determined by external components, typically a resistor and a capacitor. One of the most common implementations is using the 555 timer IC in monostable mode, where the output pulse width is given by the formula T = 1.1 × R × C. Monostable multivibrators are widely used in digital electronics for timing applications, signal conditioning, and pulse generation.
## Working
<p> The 555 timer IC operates by charging and discharging a capacitor, switching between two stable states based on voltage comparisons with reference voltages. It uses two comparators, a flip-flop, and an internal transistor to control the output. The 555 timer can be configured in monostable (one-shot), bistable (flip-flop), or astable (oscillator) modes. </p>

![Image](https://github.com/user-attachments/assets/60de3b71-f37a-4ff7-966f-ab8b10186a7f)

<p> The duration of this output pulse, often denoted as T, is calculated by the formula:
T=1.1×R×C

where R is in Ohms (Ω) and C is in Farads.   
</p>

## Circuit Diagram

![image](https://github.com/user-attachments/assets/bb37f20b-66b4-4744-901d-e0262de2926d)

## Calculations 

<p> Given that T=0.5ms and assume c=.1uF.

T=1.1RC

R =  0.5mS/(1.1×1uF) = 4.5454 KΩ.</p>

### Procedure 
<p>1. Open LTspice and create a new schematic.Set up the circuit as per the circuit diagram.
2. Select the Resistor (R) and Capacitor(C) as per the given specifcation.
3. Simulation Command
   - Go to **Simulate** -> *Edit Simulation Cmd*
   - Choose **Transient**, and set thime as needed per case.</p>
   
   ### <ins>Case 1: Properly Spaced Triggers
- Trigger Pulse Source:
  VTrig PULSE(5 0 0.05m 0 0 0.01m 2m)
  - This generates a falling edge every 2 ms (well spaced).

## Output Waveform

![image](https://github.com/user-attachments/assets/aa0898bb-c1df-4b4f-8704-0ff9bd493922)

**Output Result**:
  - Each falling edge triggers the 555.
  - Output (VOUT) goes HIGH for approx. 0.5 ms on each trigger.
  - Multiple output pulses will be seen.

### Case 2: Rapid Repeated Triggers
- Trigger Pulse Source:
  VTrig PULSE(5 0 0.05m 0 0 0.01m 0.2m)
  - This generates a falling edge every 0.2 ms (faster than output duration).

- Run the simulation for 2 ms.

![image](https://github.com/user-attachments/assets/655dfb41-dfd8-4a42-9358-80fecba61d1f)
First waveform is the output of trigger input, Second is the output of capacitor voltage and third waveform is the output of monostable multivibrator with pulse width of 0.5 ms. 

**Output Result**:
  - First falling edge triggers the 555.
  - Output (VOUT) goes HIGH for 0.5 ms.
  - All triggers during this HIGH time are ignored.


## Inference:

<p> 1.When a negative trigger pulse is applied to pin 2 of the 555 timer IC, the circuit switches from its stable state to the quasi-stable state.

2.As a result, the output (pin 3) goes HIGH and remains in this state for a duration of 0.5 milliseconds.
3.This pulse duration is determined by the values of the external resistor (R) and capacitor (C) connected to the circuit, based on the formula T = 1.1 × R × C.

4.After 0.5 ms, the capacitor charges to 2/3 of the supply voltage, causing the timer to automatically reset and bring the output back to LOW.

5.The circuit then waits in its stable (LOW) state for the next trigger pulse.

6.This confirms that the 555 timer IC accurately generates short, timed output pulses in monostable mode.</p>




# Astable Multivibrator And Monostable Multivibrator Using 555 Timer ICs
###  AIM
Generate a waveform with pulse width of 0.5 ms under different trigger conditions using 555 timer IC.

###  THEORY
An Astable Multivibrator is a circuit that coontinuously switches between two unstable states without requiring any external triggering. It operates as a self-oscillating square wave output, which is ideal for applications like clocks, pulse generation, and frequency synthesis.

In most implementations, the 555 timer IC is often used to create an astable multivibrator. In this mode, the 555 timer works by charging and discharging a capacitor through resistors, which results in the generation of a periodic square wave.

### Logic Structure Used
To ensure proper, clean triggering of the monostable 555 timer, the following logic sequence is used:
- **Astable Multivibrator (Trigger Source)**: Produces regular square wave pulses.
- **Differentiator Circuit**: Converts edges of the sqaure wave into narrow spikes.
- **Clipper Circuit**: Allows only negative spikes to pass, rejecting positive ones.
- **Monostable Multivibrator (Main 555 Timer)**: Generates a fixed-output pulse (0.5 ms) on each valid trigger.
   
## Procedure
1.	Build the circuit as per the Circuit diagram.
2.	Calculate the resistor R and capacitor C for Astable multivibrator Differentiator, clipper and Monostable multivibrator.
3.	Analyze the capacitor charging and discharging Voltage per time.
4.	Analyze the ton period when input is triggered.

### Circuit Diagram
![image](https://github.com/user-attachments/assets/a9a873cf-9096-413b-804a-2c07477ed9f8)


#### <ins>Case 1:
Consider ton = 0.3 ms, toff = 0.2 ms and C2 = 0.01 µF

*R2 = 0.2 x 10^-3/0.69 x 0.01µ = 28.985k Ω*

*R1 = (0.3 x 10^-3/0.69 x 0.01µ) - 28.985k = 14.493k Ω*

#### <ins>Case 2:
Consider ton = 0.7 ms, toff = 0.3 ms and C2 = 0.01 µF

*R2 = 0.3 x 10^-3/0.69 x 0.01µ = 43.478k Ω*

*R1 = (0.7 x 10^-3/0.69 x 0.01µ) - 43.478k = 57.971k Ω*

#### <ins>Case 3:
Consider ton = 0.1 ms, toff = 0.4 ms and C2 = 0.01 µF
This is not possible as ton must be greater than toff in astable multivibrator. Thus consider ton = 0.4 ms and toff = 0.1 ms and invert the output

*R2 = 0.1 x 10^-3/0.69 x 0.01µ = 14.492k Ω*

*R1 = (0.4 x 10^-3/0.69 x 0.01µ) - 14.492k = 43.479k Ω*

### Differentiator Circuit
Let C4 = 0.1 µF, fa = 1k Hz and fb = 10k Hz

*fa = 1/2 x pi x R4 x C4*

*R4 = 1/2 x pi x 0.1µ x 10^3 = 1.59k Ω*

*fb = 1/2 x pi x R3 x C4*

*R3 = 1/2 x pi x 0.1µ x 10 x 10^3 = 159 Ω*

### Monostable Multivibrator
*T = 1.1 x R X C*

For pulse width,T= 0.5 ms and C = 1 µF

*R = 0.5/1.1 x 10^-6 = 454.54 Ω*

### Output Waveforms

![image](https://github.com/user-attachments/assets/20bf1383-c7e0-41ae-8bf5-d7a9151dcd26)

**Output Result**:
  - Monostable is triggered at every 0.5 ms.
  - Monostable pulse width = 0.5 ms.
  - This results in continuous high output, as each new trigger occurs before previous monostable pulse finishes.

## Inference
- Controlling ON and OFF Times Isn't Always Straightforward
We saw that changing resistor and capacitor values lets us control how long the signal stays ON and OFF. But it’s not always possible to get any values we want with the basic 555 timer setup.

- The 555 Timer Has Its Limits
In some cases (like when OFF time needs to be longer than ON), the normal 555 astable circuit can’t give us the result directly. That’s why in Case 3, we had to flip the signal using an inverter.

- Inverters Can Help Us Get the Waveform We Want
By adding a simple NOT gate (built using a transistor), we were able to reverse the timing — this gave us more flexibility in generating the waveform we needed.

- Very Short Pulses Need Precise Components
In Case 2, we worked with very fast pulses (just fractions of a millisecond). To do that, we needed low resistor and capacitor values — which also showed us the importance of accuracy and how component selection affects timing.

- We Can Detect Edges Using a Differentiator
A differentiator circuit helped us catch the exact moment the signal goes from LOW to HIGH. This is useful when we only want to react to changes, not the full pulse.

- Monostable 555 Gives Clean, Consistent Pulses
Finally, when we triggered a monostable 555 with those edges, we got clean, uniform pulses every time. This is super helpful when we need a reliable output regardless of input width.

# Virtual Lab Simulation of Monostable Multivibrator
### 1. AIM
- To perform a Monostable Multivibrator using 555 Timer
- To observe and plot the Trigger Input Voltage.
- To observe and plot the Output Voltage.
- To observe and plot the Capacitance Voltage.

### 2. PROCEDURE
1. Connect the components as mentioned below:
L1-L12, L14-L12, L16-L12, L4-L9, L8-L9, L9-L10, L3-L17, L11-L13, L7-L11, L6-L13, L5-L15.(For eg. click on 1 and then drag to 12 and so on.)
2. Click on 'Check Connection' button to check the connections.
If connected wrong, click on the wrong connection. Else click on 'Delete all connection' button to erase all the connections.
3. Intially set R a=10 kΩ, C=1 µf, Vcc=5 V, Tin = 20 msec.
4. Click on "Calculate" button.
5. Now note the output voltage.
5. Click on "Plot" button to plot, Trigger Input Voltage, Output Voltage, Capacitance Voltage
6. Click on "Clear" button to clear the data.
7. Repeat the experiment for another set of resistance value and capacitance value.
8. Set the Resistance (R a) value (1 kΩ - 10 kΩ).
9. Set the Capacitance (C) value .
10. Set supply voltage (Vcc).


### 3. CIRCUIT DIAGRAM

![Screenshot 2025-05-21 220423](https://github.com/user-attachments/assets/a4eb0e00-9dff-442b-862d-c2406f4e2ff4)

### <ins>Output Waveforms
#### Trigger Input Voltage

![image](https://github.com/user-attachments/assets/6d6ccfc7-9d76-4d5a-a3e3-14b32460d009)

#### Output Voltage

![image](https://github.com/user-attachments/assets/e31368af-5f61-45b5-84d3-05d6090ad213)

#### Capacitor Voltage

![image](https://github.com/user-attachments/assets/8bec8876-7cee-4575-aef3-9e4e60491a70)

# Virtual Lab Simulation of Astable Multivibrator
###  AIM
- To perform an Astable Multivibrator using 555 Timer
- To observe and plot the Output Voltage.
- To observe and plot the Capacitance Voltage.

###  PROCEDURE
1. Connect the components as mentioned below:
L1-L12, L14-L12, L16-L12, L4-L9, L8-L9, L10-L19, L3-L17, L11-L13, L7-L19, L6-L13, L2-L13, L5-L15, L18-L9.(For eg. click on 1 and then drag to 12 and so on.)
2. Click on 'Check Connection' button to check the connections.
If connected wrong, click on the wrong connection. Else click on 'Delete all connection' button to erase all the connections.
3. Intially set R a=3.3 kΩ, R b=6.8kΩ, C=0.1µf, Vcc=5 V.
4. Click on "Calculate" button.
5. Now note the output voltage.
6. Click on "Plot" button to plot Output Voltage, Capacitance Voltage
7. Click on "Clear" button to clear the data.
8. Repeat the experiment for another set of resistance value.
9. Set the Resistance (R a) value (1 kΩ - 10 kΩ).
10. Set the Resistance (R b) value (1 kΩ - 10 kΩ).
11. Set the Capacitance (C) value (0.1 µf - 10 µf) .
12. Set supply voltage (Vcc).

###  CIRCUIT DIAGRAM

![Screenshot 2025-05-21 215723](https://github.com/user-attachments/assets/634508ab-01c8-4ce9-b096-4934f8befa28)

### Output Waveforms
#### Output Voltage

![image](https://github.com/user-attachments/assets/845fba6c-71d6-47d4-bd30-719f84f3b4d6)

#### Capacitor Voltage

![image](https://github.com/user-attachments/assets/fc355c27-2f04-422e-9f73-81af28a811e2)


