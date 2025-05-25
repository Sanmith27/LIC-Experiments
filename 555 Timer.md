# 555 Timer IC Monostable Multivibrator

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

A *monostable multivibrator* was successfully completed using the *555 timer IC*. The circuit responded correctly to input triggers, generating a **precise 0.5 ms output pulse* as calculated using:

T = (1.1 * R * C)

This experiment demonstrated how the 555 timer IC can be used to implement a monostable multivibrator, and how these circuits can be used for precise time-delay applications. As a example, I demonstrated how the multivibrator circuit could be used for generating a pulse with a pre-determined width, such as might be used for digital timing applications.
---
