# Design and Analysis of a Telescopic Cascode CMOS Operational Transconductance Amplifier

**Ballambettu Milan Shankar Bhat**                                       **Anirudha Jayaprakash**                                   
Dept. of Electronics and Communication Engineering                       Dept. of Electronics and Communication Engineering  
The National Institute of Engineering, Mysore, India                     The National Institute of Engineering, Mysore, India
2023ec_ballambettumilanshankarbhat_a@nie.ac.in                           2023ec_aniruddhjayaprakas_a@nie.ac.in
 
---

## Abstract

This report presents the design and analysis of a single-stage CMOS Operational Transconductance Amplifier (OTA) using the telescopic cascode topology. The design focuses on achieving high DC gain and output impedance while maintaining low power consumption and structural simplicity. The OTA consists of a differential input pair cascoded with NMOS and PMOS transistors, providing a significant boost in output resistance and gain without requiring additional amplifier stages. Performance metrics such as transconductance, frequency response, slew rate, and swing ranges are analyzed through hand calculations and verified through simulations. The telescopic cascode OTA is particularly suited for applications requiring precision analog amplification with power-efficient operation.

---

## I. INTRODUCTION

Operational Transconductance Amplifiers (OTAs) are widely used analog building blocks in systems such as data converters, filters, and sensor interfaces. Among various OTA topologies, the telescopic cascode OTA stands out for offering high intrinsic gain and wide bandwidth in a compact single-stage configuration. Unlike multi-stage amplifiers, the telescopic cascode OTA uses a differential pair with cascoded transistors to enhance output resistance and maintain stability without the need for compensation techniques such as Miller capacitors.

This report explores the architecture, working principle, and performance characteristics of the telescopic cascode OTA. The objective is to demonstrate how this topology efficiently balances gain, power, and simplicity, making it a strong candidate for low-power analog front-end applications. Detailed theoretical analysis is presented, supported by simulated results, and key application areas are discussed.

The OTA consists of two stages, as depicted in the circuit diagram:

The telescopic cascode Operational Transconductance Amplifier (OTA) is a single-stage amplifier topology known for its high gain and output impedance. It consists of a differential input pair (M1, M2), cascoded with transistors (M6, M7), and a PMOS cascode current mirror (M3, M4, M8, M9) as the active load. This structure enhances DC gain without requiring a second amplification stage, promoting power efficiency and simplicity in biasing.

---

## II. CIRCUIT ARCHITECTURE

![Screenshot 2025-05-09 223855](https://github.com/user-attachments/assets/9e04e682-2c84-471a-8f57-5c0d035de40f)

---

## III. WORKING PRINCIPLE

When a differential input voltage is applied between the inputs, transistors M1 and M2 steer the bias current accordingly. The resulting differential currents are mirrored via the cascode current mirror structure. Under zero differential input, symmetrical current flow results in no output swing. However, when a differential signal (vid) is applied, an output current proportional to the transconductance is generated and directed toward the load, providing voltage amplification.

The cascode configuration increases output impedance via the gain boosting effect of stacked transistors, improving the overall voltage gain.

---

## IV. DESIGN PARAMETERS

The telescopic cascode OTA is designed with the following targets:

- **Supply Voltage:** 10 V  
- **Transconductance (Gm):** gm of input pair M1, M2  
- **Output Resistance (rout):** Enhanced via cascoding  
- **DC Gain (Ao):** 30 to 40 dB  
- **Unity Gain Bandwidth (UGBW):** 50 kHz – 100 kHz

---

## V. STABILITY ANALYSIS

As a single-stage OTA, the telescopic cascode inherently exhibits a dominant single-pole frequency response. The high output resistance and limited capacitive loading result in a relatively low 3-dB bandwidth. However, the absence of additional compensation makes it suitable for applications requiring high DC gain and moderate bandwidth without complex stability considerations.

---

## VI. RESULTS

### 1. DC Characteristics

### 2. DC Gain and Bandwidth

An AC small-signal analysis was performed to determine the frequency response of the OTA. The magnitude plot shows a midband gain of approximately **34.05 dB**, which corresponds to a linear voltage gain of:


The 3-dB bandwidth (f₃dB), where the gain falls by 3 dB from its maximum, was observed at approximately **963.5 Hz**. The unity gain bandwidth (UGBW) can be estimated to fall between **50 kHz** and **100 kHz**, based on the roll-off characteristics.

### 3. Frequency Response

Transient simulation with a differential sinusoidal input of ±1 mV at 1 kHz shows the OTA outputting a clean sine wave of approximately ±50 mV, confirming a voltage gain of about 50 V/V, consistent with AC analysis. The output waveform exhibits linear operation within the small-signal range without distortion.

### 4. Input and Output Swing

- **Input swing:** ±1 mV (differential)  
- **Output swing:** ~±50 mV peak (≈100 mV peak-to-peak)  
- The circuit operates linearly within these limits, with sufficient headroom at both rails due to the telescopic structure.

### 5. Phase Response

The phase plot shows a typical roll-off behavior. The phase margin is not directly extracted due to the absence of a unity-gain phase cursor in the current plot, but stability is qualitatively inferred from the single-pole nature and moderate bandwidth.

---

## VII. APPLICATIONS

The telescopic cascode OTA is well-suited for:

- Low-power neural signal acquisition systems  
- High-gain front-end amplifiers  
- Switched-capacitor integrators  
- Precision analog computation circuits

---

## VIII. CONCLUSION

The telescopic cascode OTA offers an excellent trade-off between gain and simplicity. It achieves high output resistance and DC gain without requiring multiple amplification stages or complex compensation. Despite its narrower swing range compared to other OTAs, it remains a robust choice for analog front-end applications.

---

## IX. ACKNOWLEDGEMENT

We sincerely thank Dr. Remya Jayachandran of the Electronics and Communication Engineering Dept. at The National Institute of Engineering for giving us the chance as well as the support to write this paper. Without their active involvement and the right guidance this would not have been possible.

---

## X. REFERENCES

1. B. Razavi, *Design of Analog CMOS Integrated Circuits*, McGraw-Hill, 2001.  
2. P. R. Gray, P. J. Hurst, S. H. Lewis, and R. G. Meyer, *Analysis and Design of Analog Integrated Circuits*, Wiley, 2009.  
3. Y. Tsividis and C. McAndrew, *Operation and Modeling of the MOS Transistor*, 3rd ed., Oxford Univ. Press, 2011.  
4. D. A. Johns and K. Martin, *Analog Integrated Circuit Design*, Wiley, 1997.  
5. P. E. Allen and D. R. Holberg, *CMOS Analog Circuit Design*, 2nd ed., Oxford Univ. Press, 200.

---

