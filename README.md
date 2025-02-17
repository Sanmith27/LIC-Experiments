# Experiment-1
Question : Given that POWER, P=100µ W; Perform DC Analysis, Transient Analysis and AC Analysis for the Given Circuit Designs and also check what happens when the width is increased or decreased of each mosfet;

# Design-1 :

   ![Screenshot 2025-02-16 111936](https://github.com/user-attachments/assets/0b661ae7-5761-4b9b-bd75-93c0fc60eabb)

Aim : To find DC operating point,find gain using transient analysis and AC analysis.

Components : Mosfet,resistors,DC power supply.

Procedure :

• Make the circuit connection as show above.

• Connect the RD resistor to the drain terminal and DC power supply to the gate terminal as well as to the resistor.

• Connect the source terminal to the ground.

• Set the input voltage to 0.9 V and VDD to 1.8 V.

Using the Formula for Power, 

P=V*I

We will get the Values of Id as,

Id= 5.56 * 10^-5 A

we have to get the output current, Id for the given circuits by adjusting the values of L & W( Length and Width of the Channel of the MOSFET)

Length and Width of the Channel used to obtain the given Current is shown in the figure below;

   ![Screenshot 2025-02-16 120802](https://github.com/user-attachments/assets/109d353f-a954-4e08-b8d1-603ea40ea67c)

1) DC ANALYSIS:

   Procedure for Performing DC Analysis:
   we have to select the dc output print(DC op pnt) in the Edit Simulation Command and Run the Simulation

   ![Screenshot 2025-02-16 121422](https://github.com/user-attachments/assets/8dbd733e-f0a2-4165-8a8e-ebee3b28ace2)

   The Figure below shows the Values obtained from the DC Analysis : 

   ![Screenshot 2025-02-16 121045](https://github.com/user-attachments/assets/22bca609-a67e-4459-aa60-e584eb189442)

2) Transient Analysis:

   Procedure for Performing Transient Analysis:
   we have to select the Transient Analysis in the Edit Simulation Command,  Give the stop time as 1ms and Run the Simulation.

   ![Screenshot 2025-02-16 122038](https://github.com/user-attachments/assets/e43f0303-c135-4a82-bc71-12e6ae6000b9)

   The Graph below shows the Transient Response of the Given Design;

   ![Screenshot 2025-02-16 122339](https://github.com/user-attachments/assets/87da114b-e8f6-4981-823f-d8a504316454)
   
3) AC Analysis:
   
   Procedure for Performing AC Analysis:
   we have to select the AC Analysis in the Edit Simulation Command,  Give the values as shown in the figure beowl and Run th Simulation.

   ![Screenshot 2025-02-16 122508](https://github.com/user-attachments/assets/f67f362a-312c-45c6-869a-bd410a0e133a)

   The Graph below shows the AC Analysis of the Given Design;

   ![Screenshot 2025-02-16 122533](https://github.com/user-attachments/assets/b4141a4f-8031-4fb8-b5a9-40fe35f9c590)

# RESULT( Design-1):
 1) DC Analysis:
     1. The calculated drain current (Id) matches the expected value based on power and voltage, Id = 5.56*10^-5 A.
     2. By adjusting the MOSFET’s channel dimensions (L & W) where L=175nm and W= 178nm, The current requirement was succesfully achecived.
     4. The circuit behaves as expected under DC conditions.

 2) Transient Analysis:
     1. The transient response graph shows how the circuit behaves over time.
     2. The response is smooth, with no unexpected delays or distortions.
     3. The circuit reacts well to changes, confirming its stability.

 3) AC Analysis:
     1. The AC response graph confirms that the circuit remains stable at different frequencies.
     2. The gain(-9.94 dB) and phase shift(which is nearly 180deg) align with theoretical expectations.
     3. The circuit maintains its performance across the tested frequency range.

# INFERENCE( Design-1):
   1. The experiment confirms that by properly selecting the MOSFET dimensions, we can control the drain current effectively.
   2. Impact of Width Adjustments:
         1. M1 has a influence on Id, meaning its width affects the output current. Increase in Width increases Id and Vice-versa.
   3. The circuit performs well in all three analyses—DC, transient, and AC—demonstrating its reliability.
   4. Overall, the design works as intended, following theoretical predictions and proving its practical feasibility.



# Design-2

![Screenshot 2025-02-16 124234](https://github.com/user-attachments/assets/59e297de-ed5d-426c-8e40-92aee8d3e793)

Aim : To find DC operating point,find gain using transient analysis and AC analysis.

Components : Mosfets (M1 and M2),DC power supply.

Procedure :

• Make the circuit connection as show above.

• Connect DC power supply to the gate terminal.

• Connect the source terminal to the ground.

• Set the input voltage by obtaining VTC curve and VDD to 1.8 V.

Using the Formula for Power, 

P=V*I/n

We will get the Values of Id as,

Id= 5.56 * 10^-5 A

we have to get the output current, Id for the given circuits by adjusting the values of L & W of both the MOSFETS M1 & M2 ( Length and Width of the Channel of the MOSFET)
        
DC SWEEP Analysis: This analysis is done for obataing the value of Vin in Saturation range;

we have to select the DC SWEEP in the Edit Simulation Command,  Give the values as shown in the figure below and Run th Simulation.

![image](https://github.com/user-attachments/assets/b26e13fb-57be-4522-8e21-9b4730448512)

The Graph beow represents the VTC Curve and the value of the vin is selected as 0.8V as it is present in the saturation region of the VTC Curve

![Screenshot 2025-02-16 125157](https://github.com/user-attachments/assets/abddb50e-8287-42ad-9dcc-fc4e29b37ff7)

Then the input voltage parameters are given as;

![Screenshot 2025-02-16 125547](https://github.com/user-attachments/assets/f60a3923-74f3-4b7b-8bd2-f000b36797cf)

Length and Width of the Channel of the two MOSFETS used to obtain the given Current is shown in the figure below;

![Screenshot 2025-02-16 125820](https://github.com/user-attachments/assets/2197048a-07ff-4819-ae53-b6f496449d35)
![Screenshot 2025-02-16 125811](https://github.com/user-attachments/assets/a2eae298-1edc-49bc-a925-278ec1eee622)


Now we will be performing the DC, Transient and AC Anlaysis;

1) DC ANALYSIS:

   Procedure for Performing DC Analysis:
   we have to select the dc output print(DC op pnt) in the Edit Simulation Command and Run the Simulation

   ![Screenshot 2025-02-16 121422](https://github.com/user-attachments/assets/fe699e4e-be59-4a89-a524-8d88a54555c4)

   The Figure below shows the Values obtained from the DC Analysis :

   ![Screenshot 2025-02-16 125843](https://github.com/user-attachments/assets/dded314a-ede4-45dd-aa51-d8a5251a6ec2)

2) Transient Analysis:

   Procedure for Performing Transient Analysis:
   we have to select the Transient Analysis in the Edit Simulation Command,  Give the stop time as 1ms and Run th Simulation.

   ![Screenshot 2025-02-16 130048](https://github.com/user-attachments/assets/c3faea32-8fd7-4cdb-9d7b-0b454f8d626b)

   The Graph below shows the Transient Response of the Given Design;

   ![Screenshot 2025-02-16 130108](https://github.com/user-attachments/assets/7d25b588-1dd1-406c-98cd-8fa4fc5c6163)

3) AC Analysis:
   
   Procedure for Performing AC Analysis:
   we have to select the AC Analysis in the Edit Simulation Command,  Give the values as shown in the figure beowl and Run th Simulation.

   ![image](https://github.com/user-attachments/assets/80e2d1d3-f2f6-4ce8-b26e-0a803006303a)

   The Graph below shows the AC Analysis of the Given Design;

   ![Screenshot 2025-02-16 130145](https://github.com/user-attachments/assets/e24ddc06-ca3f-41da-b214-6e012222aa04)

# RESULT(DESIGN-2)
1.DC Analysis:

   1. The calculated drain current (Id) aligns with the expected value based on power and voltage, where the value of Id = 5.56*10^-5 A .
   2. By fine-tuning the channel dimensions (L & W) of both MOSFETs ( M1 & M2), the desired current was achieved,
         1. M1 : L= 500nm  , W= 950nm.
         2. M2 : L= 300nm  , W= 1020nm.      
   4. The circuit operates correctly within the selected DC parameters.

2.Transient Analysis:

   1. The transient response graph confirms that the circuit transitions smoothly over time.
   2. The circuit responds effectively to input variations, indicating stable operation.

3.AC Analysis:

   1. The AC response graph confirms that the circuit maintains stability over the tested frequency range.
   2. The gain(3.8 dB) and phase shift (which is nearly 180deg) align with theoretical expectations.
   3. The circuit functions as expected under AC conditions.

# Inference (Design-2):
  1. The experiment validates that by appropriately selecting the MOSFET dimensions (L & W), the drain current can be precisely controlled.
  2. The voltage transfer characteristics (VTC) helped in selecting the correct operating voltage (0.8V) for saturation.
  3. Impact of Width Adjustments:
     
     1. M2 has a stronger influence on Id, meaning its width significantly affects the output current. Increase in width increases Id drastically and vice-versa.
     2. M1 has a smaller influence, meaning changes in its width result in only minor variations in Id. Increase in qidth increases Id by small amounts and vice-versa.
  5. The design meets the expected performance criteria and follows theoretical predictions, demonstrating its feasibility in practical applications.
