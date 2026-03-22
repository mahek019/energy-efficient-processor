## Tinkercad Circuit Simulation
[Click here to view the hardware simulation](https://www.tinkercad.com/things/dPBi0SWMjfm-energyefficientprocessor?sharecode=uK3J7oKiJcOUCKheAnMksc3pydXQF9zEZlvgfp-GONY)
 
### What the Circuit Demonstrates
 
This Arduino-based LED circuit is a physical hardware model that visualizes the **Power vs Performance trade-off** and the **concept of switching between power modes** — similar to how ARM big.LITTLE switches between high-power and low-power cores.
 
### Components Used
 
| Component | Quantity | Purpose |
|---|---|---|
| Arduino Uno R3 | 1 | Microcontroller — acts as the processor |
| LED | 4 | Each LED represents a level of power consumption |
| Resistor (220 ohm) | 4 | Current limiting for each LED |
| Push Button | 1 | Simulates workload trigger (light vs heavy task) |
| Breadboard | 1 | Circuit assembly platform |

### Circuit Pin Connections
 
| Arduino Pin | Connected To | Description |
|---|---|---|
| Pin 8 | LED 1 (via 220Ω resistor) | Always ON — represents baseline power |
| Pin 9 | LED 2 (via 220Ω resistor) | ON in high performance mode only |
| Pin 10 | LED 3 (via 220Ω resistor) | ON in high performance mode only |
| Pin 11 | LED 4 (via 220Ω resistor) | ON in high performance mode only |
| Pin 2 | Push Button | Input with internal pull-up resistor |
| GND | All LED cathodes + Button | Common ground |
 
### How the Circuit Works
 
```
Button NOT pressed  →  LOW POWER MODE
    LED 1 = ON   (only 1 LED)
    LED 2 = OFF
    LED 3 = OFF
    LED 4 = OFF
    → Represents: Processor in standby / background task mode
    → Analogy: ARM LITTLE cores handling idle workload
 
Button PRESSED  →  HIGH PERFORMANCE MODE
    LED 1 = ON
    LED 2 = ON
    LED 3 = ON
    LED 4 = ON
    → Represents: Processor under full load (gaming / rendering)
    → Analogy: ARM big cores fully active under heavy workload
```
 
### COA Concept Mapping
 
| Circuit Element | COA Concept |
|---|---|
| Push button | Workload trigger — OS detecting task demand |
| 1 LED ON | Low power mode — DVFS reduces frequency and voltage |
| 4 LEDs ON | High performance mode — maximum clock speed and voltage |
| Switching between states | ARM big.LITTLE core switching via HMP scheduler |
| Number of LEDs lit | Represents power consumption level (P = CV²f) |
 

## Live Interactive Presentation
[Click here to view the animation](https://mahek019.github.io/energy-efficient-processor/)

## Key Learning Outcomes
 
After this demonstration, a student should be able to:
 
1. State and apply the dynamic power formula **P = C × V² × f**
2. Explain why reducing voltage has a quadratic effect on power savings
3. Describe how DVFS works — what the OS monitors, how P-states are selected, and what the frequency governor does
4. Differentiate between ARM big cores (high performance) and LITTLE cores (energy efficient)
5. Explain the role of the **HMP scheduler** in routing tasks to the correct core type
6. Map real-world chips (Snapdragon, Apple M4, Intel Core Ultra) to these architectural concepts
7. Relate a physical LED circuit to abstract processor power management concepts
 
---

