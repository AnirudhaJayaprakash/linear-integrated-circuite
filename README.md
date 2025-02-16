# linear-integrated-circuite
# CS Amplifier Analysis using LTSpice

## Aim
To perform DC analysis, Transient analysis, and AC analysis of a Common Source (CS) amplifier circuit and extract various parameters using LTSpice.

## Components Required
- MOSFET (cmosn, cmosp)
- Resistor (21.6kΩ)
- Voltage supply
- Connecting wires

## Theory
A **MOSFET (Metal-Oxide-Semiconductor Field-Effect Transistor)** is a type of field-effect transistor (FET) that controls the flow of current using an electric field. MOSFETs are widely used in amplifier circuits due to their high input impedance and fast switching characteristics.

A **Common Source (CS) amplifier** is a basic MOSFET amplifier configuration where the source terminal is common to both input and output. It provides voltage gain and is used in various analog applications.

### Important Parameters of CS Amplifier:
- **Voltage Gain (Av):** Ratio of output voltage to input voltage.
- **Input Impedance (Zin):** Resistance seen at the input terminal.
- **Output Impedance (Zout):** Resistance seen at the output terminal.
- **Cutoff Frequency:** Frequency at which gain drops by 3 dB from its mid-band value.
- **Phase Shift:** The difference in phase between input and output signals.

## Procedure
1. Design the CS amplifier circuit using LTSpice.
2. Connect the required components as per the circuit diagram.
3. Perform DC analysis to determine the biasing conditions.
4. Perform transient analysis to study the time-domain response.
5. Perform AC analysis to extract gain and frequency response characteristics.
6. Record observations and extract relevant parameters.

## Circuit 1

![Screenshot 2025-02-16 234215](https://github.com/user-attachments/assets/c42c9c18-4307-46a6-b3cf-a87158ad7bd3)

## DC Analysis

![Screenshot 2025-02-16 234243](https://github.com/user-attachments/assets/b2c545f6-2a6a-4ebb-9676-153865ea6ce9)

## Transient Analysis

![Screenshot 2025-02-16 234223](https://github.com/user-attachments/assets/e223a55a-c952-4780-b4b0-fb22bc2e4f9e)

## AC Analysis

![Screenshot 2025-02-17 005427](https://github.com/user-attachments/assets/4fb2c216-e137-4d78-8891-6be73ddbcd46)

- **Gain = 6 dB**


## Calculation
Given:

Power (P) = 100 µW

Supply voltage (VDD) = 1.8V

Assume VDS = 0.6V (since VDS > VOV and VOV = 0.9 - 0.35)

Step 1: Calculating Drain Current (ID)

Using the power equation:
P = VDD × ID
Rearrange to find ID:
ID = P / VDD
Substituting values:ID = 100 µW / 1.8V = 55.55 µA

Step 2: Calculating Drain Resistance (RD)

Using Kirchhoff’s Voltage Law:
VDD = ID × RD + VDS
Rearrange to find RD:
RD = (VDD - VDS) / ID
Substituting values:
RD = (1.8V - 0.6V) / 55.55 µARD = 1.2V / 55.55 µA = 21.6 kΩ



## Tabular Column
| Width (W) (µm) | Drain Current (I<sub>D</sub>) (µA) | Channel Length (L) (nm) |
|---------------|----------------------|-----------------|
| 1            | 78.7                 | 180             |
| 0.1          | 51.06                | 180             |
| 0.15         | 54.36                | 180             |
| 0.158        | 55                   | 180             |


## Results
1. The **DC analysis** determined the biasing conditions of the MOSFET, verifying that the operating point is correctly set with \( I_D \) = 55.5 µA.
2. So the qpoint whould be (0.61v,55µA)
3. The **Transient analysis** showed the time-domain response of the CS amplifier, confirming signal amplification.
4. The **AC analysis** revealed a voltage gain of **6 dB**.

## Inference
1.Current is directly Propotional to the Width of the Mosfet and the current varies with the change in width.

2.Mosfet saturation ensures the mosfet works as an amplifier and produces the desired negative gain as per the equation Av=-gm*Rd.

3.Q point stability is attained in saturation region thus helping in attaining linear amplification .

4.The Mosfet gain is increased in mid band frequency range (small signal analysis).

5.The Transient analysis reveleas the response of the circuit to time domain ssignal and determines how quickly the circuit responds to variation.

6.AC Analysis helps in designing circuits with desired gain and helps in impedance matching.
Also helps in understanding the frequency response and small signal behaviour of the circuit.


## Circuit 2

![Screenshot 2025-02-17 021058](https://github.com/user-attachments/assets/a42b557c-d83f-4fc3-8f57-298f17f72aaa)

## DC Analysis

![Screenshot 2025-02-17 021009](https://github.com/user-attachments/assets/bd13f5aa-f471-4110-b6fb-f21e85511a86)

## Transient Analysis

![Screenshot 2025-02-17 021046](https://github.com/user-attachments/assets/2b3c26f3-90ba-4b05-8ce4-ba7a159ba46e)

## AC Analysis

![Screenshot 2025-02-17 021148](https://github.com/user-attachments/assets/f6589f3c-2ac8-4ab8-a36f-8eead98aa748)

- **Gain = -8.4Db**

## Calculation
Given:

Power (P) = 100 µW

Supply voltage (VDD) = 1.8V

Assume VDS = 0.6V (since VDS > VOV and VOV = 0.9 - 0.35)

Calculating Drain Current (ID)

Using the power equation:
P = VDD × ID
Rearrange to find ID:
ID = P / VDD
Substituting values:
ID = 100 µW / 1.8V = 55.55 µA.
By trial and error we find for Id=55.5A and L=180nm for M1 transistor W=0.0812 µm
And for the m2
L=180nm ; W=0.2 µm is kept constant.



## Results
1. The **DC analysis** determined the biasing conditions of the MOSFET, verifying that the operating point is correctly set with \( I_D \) = 55.5 µA.
2. So the qpoint whould be (1.2v,55µA)
3. The **Transient analysis** showed the time-domain response of the CS amplifier, confirming signal amplification.
4. The **AC analysis** revealed a voltage gain of **-8.4 dB**.

## Inference
1. comparing the 2 circuits we can see that the gain is decreased in the second circuit this is because change in qpoint.
2. The change in the qpoint is due to changing Rd to a cmosp transistor













