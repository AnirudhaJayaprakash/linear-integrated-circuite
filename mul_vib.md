# Experiment 14: Monostable Multivibrator

## Objective
Simulate and analyze  a **monostable multivibrator** circuit in LTspice. The goal is to observe how the circuit produces a single output pulse of fixed width in response to a trigger, and to compare the measured pulse duration with theoretical predictions.

## Theory
A monostable multivibrator has **only one stable state**; it remains in this state until an external trigger pulse drives it into a temporary (unstable) state. Upon triggering, the circuit switches to its unstable state and generates a single output pulse. After a time determined by its RC timing network, the circuit automatically returns to the stable state. The pulse width is set by the resistor-capacitor (RC) network in the feedback loop. For example, in a simple transistor monostable, the pulse duration `T` is approximately `T = ln(2) * R * C` (≈ `0.693 * R * C`). 

Monostable circuits are widely used as **one-shot pulse generators** and timing elements in electronics. Typical applications include timers, pulse stretching, and debounce circuits, where a precise output pulse width is required for each input trigger.

## Circuit Description
The LTspice circuit uses two cross-coupled NPN transistors to implement the one-shot. One transistor (Q2) is held in saturation by a bias resistor from VCC, while the other (Q1) is off in the stable state. A **timing capacitor** (CT) connects between the collector of the “on” transistor and the base of the “off” transistor, forming an RC network that determines the pulse length. A **diode** is placed in parallel with the capacitor to allow it to discharge quickly after each pulse. 

The output is taken from the collector of one transistor (usually the one that switches off on trigger). A DC power source (VCC) provides supply voltage, and the emitters of both transistors are grounded. To trigger the monostable, a pulse voltage source is connected (through a coupling capacitor or directly) to the base of Q1. A negative (or positive, depending on design) trigger pulse briefly drives Q1 on, which drives Q2 off for the duration of the timing interval.

## Components Used
- **Transistors:** 2× NPN BJTs (e.g., 2N3904)  
- **Resistors:** Bias resistors for each transistor (e.g., one between VCC and Q2 base, others as needed for base bias or collector load)  
- **Capacitor:** Timing capacitor (CT, value chosen for desired pulse width)  
- **Diode:** Fast switching diode (e.g., 1N4148) across CT for rapid discharge  
- **Voltage Sources:** DC supply (VCC, e.g., 5–12 V) and a pulse generator (voltage source providing trigger pulses)  
- **Ground:** Reference ground node for the circuit  

## Procedure
1. **Set up the schematic:** Open LTspice and create a new schematic. Place two NPN transistors and orient them for cross-coupling (emitters to ground).  
2. **Connect bias resistors:** Attach a resistor from VCC to the base of Q2, ensuring Q2 is on at rest. Add any necessary resistors to Q1’s base for bias.  
3. **Add the timing network:** Connect the timing capacitor between the collector of Q2 and the base of Q1. Place a diode in parallel with the capacitor (anode to Q1 base) to allow quick discharge.  
4. **Complete the collectors:** Tie the collector of Q2 directly to VCC (through a load resistor if needed), and take the output from the collector of Q1 (through a collector resistor to VCC if required).  
5. **Insert trigger source:** Connect a pulse-voltage source to Q1’s base. Often this is done through a small coupling capacitor so that a short pulse is injected. Configure the pulse source for a short duration (much shorter than the expected monostable pulse).  
6. **Configure component values:** Choose resistor and capacitor values based on desired pulse width. For example, R and C might be selected so that `T ≈ 0.693 * R * C`.  
7. **Run simulation:** Set up a transient analysis (e.g., for several milliseconds). Apply a trigger pulse from the source at a known time and run the simulation.  
8. **Observe outputs:** Use the waveform viewer to plot the output voltage (at Q1’s collector), the trigger input, and the capacitor voltage. Measure the pulse width and compare to calculation.

## Waveform Observation
On the simulated plots, the **trigger input** will appear as a brief pulse (e.g., a negative-going spike if using a coupling capacitor) at the chosen time. The **output waveform** (at the collector of Q1) should normally sit at one level (e.g., low) and then jump to the opposite level (e.g., high) when triggered. It will stay high for the duration of the timing interval and then return low. 

The **capacitor voltage** will show an exponential change: it is driven (via the coupling network) at the moment of trigger, then charges (or discharges) through the resistor until it reaches a threshold that ends the pulse. The measured pulse width on the output should roughly match the theoretical value `T = ln(2) * R * C` (≈ `0.693 * R * C`). No new trigger is observed in the output until the capacitor has fully recharged back to its stable value.

## Calculation
Theoretical pulse width `T` can be estimated from the RC time constant:


Where:
- R is the resistance in ohms
- C is the capacitance in farads

## Inference
The LTspice simulation confirms the expected monostable behavior. Each trigger produces exactly one output pulse, with a width close to the calculated `T`. The output amplitude is near the supply voltage during the pulse and low otherwise. The timing capacitor’s voltage waveform follows the expected exponential profile. 

Any small differences between measured and theoretical values may be due to transistor saturation voltages and component tolerances. The simulation illustrates that a new trigger cannot retrigger the circuit until the timing interval has completed, a key feature of monostable circuits.

## Conclusion
The monostable multivibrator simulation demonstrated how a one-shot circuit generates a single output pulse per trigger. By choosing appropriate resistor and capacitor values, the pulse width can be accurately controlled using the formula `T ≈ 0.693 * R * C`. 

The circuit has only one stable state and returns to it automatically after the time delay. This behavior is useful in applications such as timers, debouncing, and pulse generation. The LTspice simulation effectively validated the theoretical understanding of monostable multivibrators.
