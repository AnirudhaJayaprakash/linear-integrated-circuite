# linear-integrated-circuite
# MOS Differential Amplifier Experiment Report

## Aim
Design and analyze the MOS differential amplifier circuit for the given specifications:
- Supply Voltage (Vdd) = 3.3V
- Power Consumption (P) <= 3mW
- Input Common Mode Voltage (Vicm) = 1.72V
- Output Differential Common Mode Voltage (Vdcm) = 1.81V
- Threshold Voltage (Vp) = 0.7V

Perform:
- DC Analysis
- Transient Analysis
- AC Analysis
- Extract required parameters

## Components Required
- MOSFET (CMOSN)
- Resistors: 1.738 kΩ x 2, 770 Ω
- Voltage supply
- Connecting wires

## Theory
A MOS differential amplifier is a fundamental building block in analog circuits, extensively used in operational amplifiers and sensor interfaces. It consists of two MOSFETs sharing a common current source, allowing it to amplify the difference between two input signals while rejecting common-mode noise. This configuration enhances signal integrity and noise immunity, making it ideal for high-precision applications. 

Differential amplifiers exhibit excellent common-mode rejection ratio (CMRR) and can function in different modes depending on the biasing and load conditions. Their small-signal and large-signal behavior significantly influence the overall system performance in communication and control circuits. 

## Circuit 1

### Circuit Diagram:
![Screenshot 2025-03-04 215241](https://github.com/user-attachments/assets/cddd718a-9b82-4ec5-8a47-5937e61a272e)


The given circuit is a MOS differential amplifier, which consists of two NMOS transistors (CMOSN) configured as a differential pair. The circuit components and their roles are as follows:

- **Power Supply (V1 = 3.3V):** Provides the required operating voltage for the circuit.
- **Input Bias Voltages (V2 and V3 = 1.72V):** These are the common-mode input voltages applied to the gate terminals of the transistors.
- **Load Resistors (R1 and R2 = 1.738kΩ):** These resistors set the gain and output resistance of the circuit.
- **Current Source Resistor (R3 = 770Ω):** Determines the source current  I 


ss  and stability of the circuit.
- **NMOS Transistors (M1 and M2):** Act as the main amplifying elements, forming a differential pair that amplifies the difference between the two input signals.
- **Output Nodes (out1 and out2):** The differential output signals are taken from these points.


## Design
### Calculation:
1. **Determine Iss (Source Current):**  
   Iss = Power / Vdd  
   Iss = 3mW / 3.3V = 0.909mA  

2. **Calculate Rd (Drain Resistance):**  
   Rd = (Vdd - Vdcm - Vp) / Id  
   Id = Iss / 2 = 0.909mA / 2 = 0.4545mA  
   Rd = (3.3V - 1.81V - 0.7V) / 0.4545mA  
   Rd = 1738.2 Ω  

3. **Calculate Rss (Source Resistance):**  
   Rss = Vp / Iss  
   Rss = 0.7V / 0.909mA  
   Rss = 770.2 Ω  


## DC Analysis
### Steps to Perform DC Analysis in LTspice XVII
1. **Open LTspice XVII** and load the MOS differential amplifier circuit schematic.
2. **Set Up the Simulation Command:**
   - Click on **Simulate** > **Edit Simulation Cmd**.
   - In the **DC op pnt** tab, select **.op (DC Operating Point Analysis)**.
   - Click **OK**, and place the generated command on the schematic.
3. **Check the Component Parameters:**
   - Ensure that the MOSFET models and resistor values match the given specifications.
   - Verify that the power supply voltages (Vdd, Vicm) are correctly set.
4. **Run the Simulation:**
   - Click on **Run**.
![Screenshot 2025-03-04 215252](https://github.com/user-attachments/assets/8d4924cf-4227-4277-9d1b-68479982e87d)
   - By doing these steps we set the *Qpoint* for the given circuit 

## Transient Analysis

1. **Open LTspice XVII** and load the circuit schematic.
2. **Set Up the Simulation Command:**
   - Click on **Simulate** > **Edit Simulation Cmd**.
   - In the **Transient** tab, enter a stop time (e.g., 10ms) and a step time if needed.
   - Click **OK**, and place the generated command on the schematic.
3. **Apply an Input Signal:**
   - Set a sinusoidal or pulse voltage source at the input nodes.
   - Define the frequency and amplitude of the input signal.
4. **Run the Simulation:**
   - Click on **Run**.
5. **Analyze the Waveforms:**
   - Observe the output waveforms at the differential output nodes.
   - Verify the response and note the phase shift and signal gain.
     
![Screenshot 2025-03-04 215529](https://github.com/user-attachments/assets/daebfae3-4c65-426f-a769-aacece7c0e1b)


## AC Analysis
### Steps to Perform AC Analysis in LTspice XVII
1. **Set Up the Simulation Command:**
   - Click on **Simulate** > **Edit Simulation Cmd**.
   - In the **AC Analysis** tab, select **Type of Sweep Decade**.
   - Enter the number of points per decade and the frequency range ( 0.1Hz to 1THz).
   - Click **OK**, and place the generated command on the schematic.
2. **Set AC Parameters for Input Source:**
   - Ensure the input voltage source is set with an AC amplitude (1V).
3. **Run the Simulation:**
   - Click on **Run**.
5. **Analyze the Frequency Response:**
   - Observe the gain and phase plots.
   - Identify important parameters like bandwidth and gain margin.

![Screenshot 2025-03-04 215727](https://github.com/user-attachments/assets/e51d9c93-fd3a-40cd-8ab1-cc12dbf2a6f9)
   - From the above image we can see that there is a **Phaseshift** of 180° and **Gain** of  -3.45Db.



## Circuit 2

![Screenshot 2025-03-04 215855](https://github.com/user-attachments/assets/add8e3ae-cd77-4a47-a6c7-c8f3f2b785ab)

**In this we change the Rss resistor to a current source**
### Why These Changes Were Made
  - Introducing AC input signals allows us to study the amplifier’s dynamic response, including gain, bandwidth, and frequency behavior.
  - Using a current source (I1) instead of a resistor (R3) provides a more stable and controlled source current, reducing dependence on transistor parameters and improving matching and common-mode rejection.
  - Setting the AC magnitude of the input sources ensures that we can measure the amplifier's small-signal behavior for AC analysis.

## DC Analysis
**Do the sme steps as done for circuit 1**
![Screenshot 2025-03-04 215849](https://github.com/user-attachments/assets/eab7bf39-4f2e-4b9c-ab70-e2a5eeb79735)
## Transient Analysis
**Do the sme steps as done for circuit 1**
![Screenshot 2025-03-04 220113](https://github.com/user-attachments/assets/37b33a56-291a-40fb-9fcc-422175f747fc)
## AC Analysis
**Do the sme steps as done for circuit 1**
![Screenshot 2025-03-04 200305](https://github.com/user-attachments/assets/37687ea1-ff65-4e13-ab77-54238af552e7)
 - From the above image we can see that there is a **Phaseshift** of 180° and **Gain** of  -6.33Db.



## Circuit 3
![Screenshot 2025-03-04 221331](https://github.com/user-attachments/assets/00a5c910-6c4a-4362-8510-a32e7d5c3982)

## DC Analysis
**Do the sme steps as done for circuit 1**
![Screenshot 2025-03-04 221318](https://github.com/user-attachments/assets/18bd020b-bd55-4a37-8f53-3a42b4ebf3db)

## Transient Analysis
**Do the sme steps as done for circuit 1**
![Screenshot 2025-03-04 221544](https://github.com/user-attachments/assets/df6c37ac-cd95-481e-91da-d5f6338dc4c2)

## AC Analysis
**Do the sme steps as done for circuit 1**

![Screenshot 2025-03-04 221738](https://github.com/user-attachments/assets/b1db0454-300c-4b71-8b13-a89cc8040acd)
 - From the above image we can see that there is a **Phaseshift** of 180° and **Gain** of  -18.34Db.
# **Final Result**
| **Parameter** | **Circuit 1** | **Circuit 2** | **Circuit 3** |
|--------------|--------------|--------------|--------------|
| **V(out1)**  | 2.51007V  | 2.51008V  | 2.50994V  |
| **V(out2)**  | 2.51007V  | 2.51008V  | 2.50994V  |
| **V(vp) (Common Mode Voltage)** | 0.699939V | 0.699945V | 0.699867V |
| **Id(M1)** | 0.000454506 A | 0.0004545 A | 0.000454582 A |
| **Id(M2)** | 0.000454506 A | 0.0004545 A | 0.000454582 A |
| **Id(M3) (Tail Current Source)** | Not present | 0.000909(set with ideal current source) | 0.000909164 A |
| **Total Tail Current** | 0.000909012 A | 0.000909 A | 0.000909164 A |

   
# **Final Inference**
 ## Comparison of Differential Pair Circuits

| Feature               | **Circuit 1**                  | **Circuit 2**                  | **Circuit 3**                  |
|-----------------------|--------------------------------|--------------------------------|--------------------------------|
| **Current Source**    | Resistor (770Ω)               | Ideal Current Source (0.909mA) | Active Current Source (NMOS)   |
| **Practicality**      | Less Practical                | Suitable for AC Analysis       | Realistic for Circuit Design   |

- **Circuit 1:** Basic differential pair with a resistive current source. Good for simple analysis but lacks precise biasing control.
- **Circuit 2:** Uses an **ideal current source**, which improves biasing and stability.
- **Circuit 3:** Implements an **active current source using NMOS**, providing **best stability** and is more **practical** for real applications.
- **Circuit 3 is the preferred design** for real-world implementations.

### Tail Current Stability in a Differential Pair

| **Circuit** | **Tail Current Source** | **Tail Current Stability** | **Remarks** |
|------------|----------------------|-------------------------|------------|
| **Circuit 1** | **Resistor (770Ω)** | **Low** | Tail current depends on supply voltage and temperature variations. |
| **Circuit 2** | **Ideal Current Source (0.909mA)** | **High** | Provides a perfectly stable current, but not practical in real circuits. |
| **Circuit 3** | **Active Current Source (NMOS)** | **Highest** | **Best real-world implementation**, as it dynamically adjusts to maintain stability. |
- **Circuit 1 (Resistor-Based Source)**: Simple but suffers from supply voltage variations.  
- **Circuit 2 (Ideal Current Source)**: Good for theoretical analysis but not feasible in practical designs.  
- **Circuit 3 (Active Current Source - NMOS)**: **Best choice** as it provides a **stable tail current**, ensuring optimal amplifier performance in real-world conditions.

1. **Addition of M3 Transistor:**  
   - In Circuit 3, an additional MOSFET (M3) is added as a **current source** to improve the tail current stability.  
   - This ensures a more **balanced** current flow in the differential pair (M1 & M2).  

2. **Improved Current Stability:**  
   - In Circuit 1, the current through M1 and M2 is solely dependent on the resistors and supply voltage.  
   - In Circuit 3, M3 provides a **constant tail current**, reducing variations due to supply voltage fluctuations or transistor mismatches.  

3. **Voltage Levels Comparison:**  
   - **Circuit 1:** Output voltages at **out1** and **out2** = **2.51007V**  
   - **Circuit 3:** Output voltages at **out1** and **out2** = **2.50994V**  
   - The minor difference indicates **better regulation** of tail current in Circuit 2.  

4. **Current Distribution Changes:**  
   - **Circuit 1:** Drain current **Id(M1) = Id(M2) = 0.000454506 A**  
   - **Circuit 3:** Drain current **Id(M1) = Id(M2) = 0.000454582 A**, and **M3 handles 0.000909164 A**, indicating a **regulated tail current**.  

### **Final Conclusion:**  
Circuit 3, with the additional **current source (M3)**, provides **better stability, improved common-mode rejection, and ensures a constant tail current**, making it superior to Circuit 1 for differential pair applications.
















