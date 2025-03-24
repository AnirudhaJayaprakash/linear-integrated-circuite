# **CURRENT MIRROR**
## Aim
Design and analyze the given current mirror circuit with the following specifications:
- **Voltage Gain (Av) > 10 V/V**
- **Supply Voltage (Vdd) = 1.8V**
- **Power Consumption (P) <= 1W**
- **Design for 1:1 and 1:2 current ratios**
- **Consider three cases for channel length (L):**
  - **L = 180 nm**
  - **L = 500 nm**
  - **L = 1 μm**
  - Maintain the same W/L ratio for all cases.

## Theory
The current mirror is a fundamental building block in analog circuit design, primarily used for biasing and current amplification. It ensures that the output current closely follows the reference current, making it useful in differential amplifiers, operational amplifiers, and voltage regulators. 

A basic current mirror consists of two MOSFETs operating in saturation mode. The reference current is set by a biasing resistor or a current source, and the output current is mirrored with minimal variation. 

Key properties of a current mirror include:
- **High output resistance**, which ensures accurate current replication.
- **Low input resistance**, allowing efficient current sourcing.
- **Matching of transistor characteristics**, which influences performance and accuracy.
- **Design considerations**, such as channel length modulation and Early voltage effects, which impact current stability.

## Procedure
- Reffer Experiment_2 for LTspice procedurs for DC, AC and Trancient analysis. 

## Calculation

### Given:
- **Supply Voltage**: V<sub>dd</sub> = 1.8V  
- **Power Consumption**: P ≤ 1mW  

### Total Current:
I<sub>total</sub> = P / V<sub>dd</sub> = 1mW / 1.8V = 0.555mA  

### 1:1 Ratio:
I<sub>total</sub> = I<sub>ref</sub> + I<sub>x</sub>  
Since I<sub>ref</sub> = I<sub>x</sub>:  
I<sub>ref</sub> = I<sub>total</sub> / 2 = 0.2775mA  

### 1:2 Ratio:
I<sub>total</sub> = I<sub>ref</sub> + I<sub>x</sub>  
Given I<sub>x</sub> = 2 × I<sub>ref</sub>:  
I<sub>ref</sub> = I<sub>total</sub> / 3 = 0.185mA  
I<sub>x</sub> = 2 × I<sub>ref</sub> = 0.370mA  

## MAX output swing 
![Screenshot 2025-03-24 215834](https://github.com/user-attachments/assets/b1b364d4-0919-4675-900e-fea959b0ad9a)
- As we can see the wave is cut at +1.8v and 61.789mV as the input voltage is 1.8v(V<sub>DD</sub>) the max output headroom and legroom is can't exeed 1.8v and would be similar for all L value. 

## L = 180 nm
### 1:1 W/L Ratio
![Screenshot 2025-03-23 100040](https://github.com/user-attachments/assets/dc126297-68cd-444b-9fd7-d2d4c5e92f02)
#### DC Analysis
![Screenshot 2025-03-23 100056](https://github.com/user-attachments/assets/9dde0e14-5826-4171-88f3-96dc7273cd21)
- Measured drain current: **Id = 0.0002769 A**

#### Transient Analysis
![Screenshot 2025-03-23 145031](https://github.com/user-attachments/assets/33032405-d34d-401b-8953-a6d55a45376f)
- The waveform shows amplification, confirming proper current mirroring.

#### AC Analysis
![Screenshot 2025-03-24 193744](https://github.com/user-attachments/assets/54154034-e8e8-46e4-8d99-7a88cc447468)
- The measured **-3dB voltage gain (Av) = 17.5 dB**

### 1:2 W/L Ratio
![Screenshot 2025-03-23 145056](https://github.com/user-attachments/assets/489c0a7b-942d-446b-9e5e-1e5e4d03af63)
#### DC Analysis
![Screenshot 2025-03-23 145051](https://github.com/user-attachments/assets/6a09d7b0-9c07-4cdc-81c4-d1a29e1eba4e)
- Measured drain current: **Id = 0.00037 A**

#### Transient Analysis
![Screenshot 2025-03-23 100143](https://github.com/user-attachments/assets/90a858f0-8825-4611-b537-b4d5abeddde5)
- The waveform shows further amplification due to the 1:2 ratio.

#### AC Analysis
![Screenshot 2025-03-23 160619](https://github.com/user-attachments/assets/f1712368-3be6-48b4-910d-3e674a100f67)
- The measured **-3dB voltage gain (Av) = 21 dB**

### Inference for L = 180 nm
- The 1:2 ratio results in a higher gain due to the increased transconductance (gm).
- The transient response confirms that the circuit amplifies the signal appropriately.
- DC analysis verifies correct mirroring of current values.

## Comparison Table for L = 180 nm
| Parameter | 1:1 Ratio (L = 180 nm) | 1:2 Ratio (L = 180 nm) |
|-----------|------------------------|------------------------|
| **Id (A)** | 0.0002769 | 0.00037 |
| **-3dB Gain (dB)** | 17.5 | 21 |

## L = 500 nm
### 1:1 W/L Ratio
![Screenshot 2025-03-23 153233](https://github.com/user-attachments/assets/409d0f9d-8f15-40d4-9bed-f16c3417e18d)
#### DC Analysis
![Screenshot 2025-03-23 151351](https://github.com/user-attachments/assets/cf83b071-d6c3-440a-aa0f-8095fa97afe6)
- Measured drain current: **Id = 0.000274 A**

#### Transient Analysis
![Screenshot 2025-03-23 153125](https://github.com/user-attachments/assets/8c131f5d-e25f-4604-879f-d01f484c4356)
- The waveform shows amplification, confirming proper current mirroring.

#### AC Analysis
![Screenshot 2025-03-23 155846](https://github.com/user-attachments/assets/65e79d5c-d3ef-451c-bf11-d9b36f27a418)
- The measured **-3dB voltage gain (Av) = 17.5 dB**

### 1:2 W/L Ratio
![Screenshot 2025-03-23 154601](https://github.com/user-attachments/assets/f3b0471f-f9c2-4767-9019-3c929cf64cc1)
#### DC Analysis
![Screenshot 2025-03-23 154529](https://github.com/user-attachments/assets/063bd85a-409b-4803-b57b-61718d55594e)
- Measured drain current: **Id = 0.00037 A**

#### Transient Analysis
![Screenshot 2025-03-23 155012](https://github.com/user-attachments/assets/afb1eb82-8b97-4280-a9b8-3cfef9475189)
- The waveform shows further amplification due to the 1:2 ratio.

#### AC Analysis
![Screenshot 2025-03-23 234324](https://github.com/user-attachments/assets/fc4673c6-132f-44ed-a8bb-c001de8d5a47)
- The measured **-3dB voltage gain (Av) = 18.6 dB**

### Inference for L = 500 nm
- The 1:2 ratio again results in higher gain due to increased transconductance (gm).
- The slightly lower gain compared to L = 180 nm suggests increased output resistance.
- The transient response confirms that the circuit amplifies the signal appropriately.

## Comparison Table for L = 500 nm
| Parameter | 1:1 Ratio (L = 500 nm) | 1:2 Ratio (L = 500 nm) |
|-----------|------------------------|------------------------|
| **Id (A)** | 0.000274 | 0.00037 |
| **-3dB Gain (dB)** | 17.5 | 18.6 |

## L = 1 μm
### 1:1 W/L Ratio
![Screenshot 2025-03-23 221625](https://github.com/user-attachments/assets/5300706d-1f59-49ac-864c-792d2f2e8bd0)
#### DC Analysis
![Screenshot 2025-03-23 221605](https://github.com/user-attachments/assets/9b5fba75-59c2-437c-aad1-48f1ae2fb435)
- Measured drain current: **Id = 0.000277 A**

#### Transient Analysis
![Screenshot 2025-03-23 221756](https://github.com/user-attachments/assets/49684e7c-0773-42e4-bc6f-1caf52b4e202)
- The waveform shows amplification, confirming proper current mirroring.

#### AC Analysis
![Screenshot 2025-03-23 222039](https://github.com/user-attachments/assets/31858b96-2313-4fe4-96e3-0ba49bc3e8e6)
- The measured **-3dB voltage gain (Av) = 20.3 dB**

### 1:2 W/L Ratio
![Screenshot 2025-03-23 222455](https://github.com/user-attachments/assets/9f89a288-07d3-4574-880a-26f6596ef5be)
#### DC Analysis
![Screenshot 2025-03-23 222445](https://github.com/user-attachments/assets/ec56772a-6dda-4478-a7b8-f451a024abc6)
- Measured drain current: **Id = 0.00037 A**

#### Transient Analysis
![Screenshot 2025-03-23 222711](https://github.com/user-attachments/assets/6945e913-d36b-4bad-95e8-c49c9adce00c)
- The waveform shows further amplification due to the 1:2 ratio.

#### AC Analysis
![Screenshot 2025-03-23 223005](https://github.com/user-attachments/assets/ea922b4c-dd11-4253-827b-2acc1c90fa6e)
- The measured **-3dB voltage gain (Av) = 27.6 dB**

### Inference for L = 1 μm
- The highest gain is observed in the **L = 1 μm** case, particularly for the 1:2 ratio.
- The transient response confirms proper signal amplification.
- Increasing L increases gain due to reduced short-channel effects and higher output resistance.

## Comparison Table for L = 1 μm
| Parameter | 1:1 Ratio (L = 1 μm) | 1:2 Ratio (L = 1 μm) |
|-----------|---------------------|---------------------|
| **Id (A)** | 0.000277 | 0.00037 |
| **-3dB Gain (dB)** | 20.3 | 27.6 |

## Inference
- Comparing all gain values, we observe that the gain increases as the channel length (L) increases. The highest gain is seen in the **L = 1 μm** case, confirming that longer channel lengths contribute to improved voltage gain.
- The increase in L results in **better current mirroring** due to reduced short-channel effects and increased output resistance. This leads to a more stable and accurate current replication.
- The **1:2 ratio consistently provides higher gain** compared to the 1:1 ratio due to the increase in transconductance (gm), which enhances the amplification capability.
- **Transient Analysis Comparison:**
  - As we compare the transient analysis waveforms across different values of L, we observe that the **width of the sine wave increases** when L is increased.
  - This occurs because **the transient response becomes slower** with increasing L. The increased channel length results in **higher output resistance**, which leads to **lower bandwidth** and a longer time constant for circuit response.
  - The slower transient response means that the circuit takes more time to settle to steady-state values, which can be seen as a widening of the waveform in the time domain.
  - This behavior is expected since **a higher L leads to lower drain-source conductance (gds), reducing the speed at which current changes in response to voltage variations**.

### Result
| Parameter | 1:1 Ratio (L = 180 nm) | 1:2 Ratio (L = 180 nm) | 1:1 Ratio (L = 500 nm) | 1:2 Ratio (L = 500 nm) | 1:1 Ratio (L = 1 μm) | 1:2 Ratio (L = 1 μm) |
|-----------|------------------------|------------------------|------------------------|------------------------|---------------------|---------------------|
| **Id (A)** | 0.0002769 | 0.00037 | 0.000274 | 0.00037 | 0.000277 | 0.00037 |
| **-3dB Gain (dB)** | 17.5 | 21 | 17.5 | 18.6 | 20.3 | 27.6 |

- From the table, we confirm that  **generaly both Id and gain improve as L increases**, validating the theoretical expectations of current mirroring performance with longer channel lengths.
- Additionally, the **slower transient response at higher L values** indicates a trade-off between gain and speed, which should be considered in practical circuit designs.


# MOS Differential Amplifier With Current Mirror
## Aim

Design and analyze the MOS differential amplifier circuit for the given specifications:

- **Supply Voltage (Vdd):** 3.3V
- **Power Consumption (P):** ≤ 3mW
- **Input Common Mode Voltage (Vicm):** 1.72V
- **Output Differential Common Mode Voltage (Vdcm):** 1.81V
- **Threshold Voltage (Vp):** 0.7V
- **Current Mirror Implementation:** Used for biasing the differential amplifier

## Theory

A **current mirror** is a circuit that replicates (mirrors) the current from one active device to another, ensuring a constant current source or sink. In the context of a **MOS differential amplifier**, the current mirror plays a crucial role in biasing and ensuring proper operation.

### Key Insights into Current Mirror with Differential Amplifier:

1. **Current Biasing:** The current mirror provides a stable biasing current, ensuring consistent operation.
2. **Improved Common-Mode Rejection:** The differential amplifier rejects common-mode noise, and the current mirror enhances this performance.
3. **Matching Considerations:** The transistors used in the current mirror must be well-matched to ensure accurate current mirroring.
4. **Voltage Headroom:** Proper design ensures that the circuit operates within the given supply voltage constraints.
5. **Load Considerations:** The output impedance of the current mirror affects the gain and performance of the differential amplifier.

## Calculation

- **Determine Iss (Source Current):**\
  Iss = Power / Vdd\
  Iss = 3mW / 3.3V = 0.909mA

## Circuit 

![Screenshot 2025-03-24 234316](https://github.com/user-attachments/assets/49249614-f17f-4b81-890a-8fe5d7a3681f)

## DC Analysis

![Screenshot 2025-03-24 234328](https://github.com/user-attachments/assets/9e0c06ad-e09a-439d-9a5d-adbff2425cdd)

## Transient Analysis
![Screenshot 2025-03-24 234402](https://github.com/user-attachments/assets/2ea344f8-40b4-4a46-a28f-565a534f19aa)


## AC Analysis
![Screenshot 2025-03-25 001855](https://github.com/user-attachments/assets/d3ae10f8-5ae0-4248-9e66-eb1282e93ae4)

## Comparison of Differential Amplifier Circuits With privious Experiment

## Infernce

| Parameter                  | Ckt without Current Mirror | Ckt with Current Mirror | Inference |
|----------------------------|---------------------------|-------------------------|-----------|
| Tail Current Stability     | Varies with temperature and supply changes | Constant due to current mirror | Improved bias stability |
| Common Mode Rejection Ratio (CMRR) | Lower due to mismatch | Higher due to better matching | Reduced common-mode noise |
| Gain Stability             | Unstable, varies with tail current | More predictable | Better signal amplification |
| Output Swing               | Limited by tail current variations | Improved with regulated current | Enhanced signal integrity |
| Frequency Response         | Affected by mismatch and instability | Wider bandwidth with stable biasing | Better high-frequency performance |

### Justification for Each Change

#### Tail Current Source:
- **Ckt without Current Mirror:** Used a simple current source, possibly a resistor or a fixed current bias.
- **Ckt with Current Mirror:** Implemented a current mirror, ensuring constant tail current, improving overall performance.  
**Inference:** Better bias stability, reducing variations due to temperature or power supply fluctuations.

#### Common Mode Rejection Ratio (CMRR):
- **Ckt without Current Mirror:** Without a precise current source, mismatches in transistors cause lower CMRR.
- **Ckt with Current Mirror:** Current mirror ensures better matching, reducing common-mode signal impact.
**Inference:** Ckt with Current Mirror rejects common-mode noise more effectively, improving differential operation.

#### Gain Stability:
- **Ckt without Current Mirror:** Gain fluctuates due to variations in tail current and process mismatches.
- **Ckt with Current Mirror:** With a constant current mirror, gain is more predictable.
**Inference:** Consistent differential gain, improving signal amplification quality.

#### Output Swing:
- **Ckt without Current Mirror:** Limited by variations in tail current.
- **Ckt with Current Mirror:** With a well-regulated current mirror, the circuit operates more linearly.
**Inference:** Improved output swing and signal integrity.

#### Frequency Response:
- **Ckt without Current Mirror:** Dependent on device mismatches and unstable biasing.
- **Ckt with Current Mirror:** Current mirror ensures proper biasing, reducing parasitic effects.
**Inference:** Higher bandwidth and better high-frequency response in Ckt with Current Mirror.

---




































