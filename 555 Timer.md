# 555 Timer IC 

# 1) Monostable Multivibrator

 ## Objective
 To use the **555 timer IC** to design and build a **monostable multivibrator** that, when activated, produces an output pulse with a width of **0.5 milliseconds**.

 ---

 ## Theory

 There is just **one stable state** for a **monostable multivibrator** (also known as a one-shot timer).  The output changes from **LOW to HIGH** for a certain amount of time after receiving a **trigger pulse**, and then it returns to its initial **LOW** state.

 The circuit's **capacitor (C)** and **resistor (R)** values dictate this duration.
 -  When the voltage at pin 2 of the 555 falls **below 1/3 Vcc**, the timer starts.
 Until the voltage across the capacitor **exceeds 2/3 Vcc**, the output stays HIGH until resetting.

###  Formula for Pulse Width

T = (1.1 * R * C)

Where:
- *T* = output pulse width (in seconds)
- *R* = resistance (in ohms)
- *C* = capacitance (in farads)

---

##  Components Required

| Component        | Value / Description          |
|------------------|------------------------------|
| 555 Timer IC     | 1                            |
| Resistor (R)     | 454.54 Ω                     |
| Capacitor (C)    | 1 µF , 0.1 µF                |
| DC Supply        | +5V                          |
| Trigger Source   | Push button or pulse input   |
| Load             | LED / Oscilloscope           |

---

##  Calculation

Given:
- Pulse width T = 0.5 ms = 0.0005 s
- Capacitance C = 1 µF = 1×10⁻⁶ F

Using the formula:

R = (T/(1.1 * C)) = (0.0005/(1.1* 1 *10^(-6))) = 454.54 Ω



---

##  Circuit Diagram

> ![image](https://github.com/user-attachments/assets/33aa1723-d2ce-49bf-ad92-f86b3f31aadb)


---

##  Procedure

1. *Connect* the 555 timer IC in monostable configuration:
   - Pin 1 → GND
   - Pin 2 → Trigger (active LOW)
   - Pin 3 → Output
   - Pin 4 → Reset (connected to Vcc)
   - Pin 5 → Control Voltage (connected to GND via 0.01 µF)
   - Pin 6 → Threshold
   - Pin 7 → Discharge
   - Pin 8 → Vcc (+5V)

2. *Connect resistor (R)* between Vcc and pins 8 & 7.

3. *Connect capacitor (C)* between pins 6 & 1 (GND).

4. *Apply trigger pulse* to pin 2 using a push-button or signal generator.

5. *Observe the output* at pin 3 using an oscilloscope or LED.

---

##  Output Waveform

> ![image](https://github.com/user-attachments/assets/8ad28f52-511a-44d2-ad6c-78ddfc28f2f4)


- *First waveform:* Trigger pulse (input)
- *Second waveform:* Capacitor voltage (charging/discharging)
- *Third waveform:* Output pulse (~0.5 ms)

---

##  Inference

- The circuit *remains LOW* in stable state.
- On triggering, the output *switches to HIGH* for a calculated duration.
- After the pulse duration, it *returns to LOW* without requiring manual reset.
- The output pulse width closely matched the *0.5 ms target* using calculated RC values.

---

##  Conclusion

A *monostable multivibrator* was successfully completed using the *555 timer IC*. The circuit responded correctly to input triggers, generating a precise 0.5 ms output pulse as calculated using:

T = (1.1 * R * C)

This experiment demonstrated how the 555 timer IC can be used to implement a monostable multivibrator, and how these circuits can be used for precise time-delay applications. As a example, I demonstrated how the multivibrator circuit could be used for generating a pulse with a pre-determined width, such as might be used for digital timing applications.
---

# Astable Multivibrator
## Objective
Astable multivibrators, also known as "free-running" multivibrators, are circuits that continuously generate a rectangular waveform without the need for external triggering. Unlike a monostable multivibrator, it alters its output states on its own. The duration of its high and low output phases is controlled by a 555 timer integrated circuit connected to two external resistors and a capacitor.
Unlike an integrator circuit, a differentiator amplifier circuit has the resistor and capacitor positioned in the opposite directions. A resistor is utilized in the feedback path, and the capacitor is connected to the inverting operational amplifier's input. This arrangement enables the circuit to carry out the differentiation mathematical operation. More input current is produced when the input voltage varies quickly or dramatically, which causes a more noticeable voltage change at the output, frequently manifesting as a sharp spike. A key factor in determining how the differentiator behaves is the RC network, namely the reactance of the capacitor.
The purpose of a clipper circuit is to "clip" or remove particular portions of a waveform, like undesired negative voltage spikes. A monostable multivibrator is then activated by the clipped signal that results.
## Procedure
1.	Build the circuit as per the Circuit diagram.
2.	Calculate the resistor R and capacitor C for Astable multivibrator Differentiator, clipper and Monostable multivibrator.
3.	Analyze the capacitor charging and discharging Voltage per time.
4.	Analyze the ton period when input is triggered.
## Calculation

![WhatsApp Image 2025-05-26 at 19 22 47_aa4865f3](https://github.com/user-attachments/assets/71c8f508-ff1b-4fbc-844f-ef44d5e8a39f)

## Circuit Diagram:

![image](https://github.com/user-attachments/assets/fd60325d-b069-4f10-84c7-fe1e0f31741d)

## Waveform
### Case 1:
![image](https://github.com/user-attachments/assets/fe342c52-308e-42f3-851a-70c9c03589ea)
- **Waveform 1**: Output of an Astable Multivibrator.  
- **Waveform 2**: Output of a Differentiator Circuit.  
- **Waveform 3**: Output of a Positive Clipper Circuit.  
- **Waveform 4**: Output of a Monostable Multivibrator (pulse width = 0.5 ms).

### Case 2:
![image](https://github.com/user-attachments/assets/67fc881d-9c7d-474f-820b-ce097d4eb4fc)

- **Waveform 1**: Output of an astable multivibrator.
- **Waveform 2**: Output of a differentiator circuit (with capacitor value 0.1 μF).
- **Waveform 3**: Output of a positive clipper circuit.
- **Waveform 4**: Output of a monostable multivibrator with a pulse width of 0.5 ms.

### Case 3:
![image](https://github.com/user-attachments/assets/ae9e3512-c7a0-4558-b374-863a79764954)

![image](https://github.com/user-attachments/assets/eaabf927-36fd-4a83-a688-e3f012f7f605)


- If the third waveform requires **t<sub>ON</sub> < t<sub>OFF</sub>**, which is not achievable with a typical astable multivibrator configuration, an **inverter** can be used to invert the generated pulse.
- **Waveform 1**: This is the output of an **inverted astable multivibrator**.
- **Waveform 2**: This comes from a **differentiator circuit**, where the capacitor used is **0.1 μF**.
- **Waveform 3**: This is the output of a **positive clipper circuit**.
- **Waveform 4**: This is the output of a **monostable multivibrator**, and the pulse width is set to **0.5 ms**.

##  Inference

- **Tuning ON/OFF Times Isn’t Always Easy**  
  I tried changing resistor and capacitor values to adjust how long the signal stays ON or OFF. It works to an extent, but we can’t get all possible values with the standard 555 timer circuit.

- **The 555 Timer Has Some Limitations**  
  Especially in Case 3, where we wanted the OFF time to be longer than the ON time — the regular astable mode didn’t allow it. So, we had to flip the output using an inverter.

- **Inverters Help When 555 Can’t Do It Alone**  
  By adding a simple NOT gate (like using a transistor), we flipped the waveform. This gave us more flexibility and helped us get the timing we actually needed.

- **Tiny Pulses Need Accurate Components**  
  In Case 2, we dealt with super short pulses (in microseconds!). For that, we had to use small resistor and capacitor values. It showed us how important component accuracy is when working with tight timings.

- **Differentiator Circuits Detect Edges**  
  We used a differentiator to catch the rising edge of the signal (LOW to HIGH transition). That’s super useful when we only care about changes, not the full pulse.

- **Monostable Mode Gives Clean Output**  
  Using a monostable 555 with edge triggering gave us a consistent output every time. It’s a great way to get a fixed pulse width, no matter what the input looks


# Simulation in Virtual Lab
# Astable Multivibrator
## Procedure:
1.	Connect the components as mentioned below: L1-L12, L14-L12, L16-L12, L4-L9, L8-L9, L10-L19, L3-L17, L11-L13, L7-L19, L6-L13, L2-L13, L5-L15, L18-L9.(For eg. click on 1 and then drag to 12 and so on.)
2.	Click on 'Check Connection' button to check the connections.
3.	If connected wrong, click on the wrong connection. Else click on 'Delete all connection' button to erase all the connections.
4.	Intially set R a=3.3 kΩ, R b=6.8kΩ, C=0.1µf, Vcc=5 V.
5.	Click on "Calculate" button.
6.	Now note the output voltage.
7.	Click on "Plot" button to plot Output Voltage, Capacitance Voltage
8.	Click on "Clear" button to clear the data.
9.	Repeat the experiment for another set of resistance value.
10.	Set the Resistance (Ra) value (1 kΩ - 10 kΩ).
11.	Set the Resistance (Rb) value (1 kΩ - 10 kΩ).
12.	Set the Capacitance (C) value (0.1 µf - 10 µf) .
13.	Set supply voltage (Vcc).

## Circuit Diagram
![image](https://github.com/user-attachments/assets/f4f78504-d27d-411e-9c26-4689fe0bc509)

## Otuput Waveform
Voltage Across the Capacitor: 

![image](https://github.com/user-attachments/assets/2db90498-553e-4eda-b996-ef76d576d0c9)


Output Waveform: -

![image](https://github.com/user-attachments/assets/1ec6ba06-4a35-45d0-804e-2869928451cf)

