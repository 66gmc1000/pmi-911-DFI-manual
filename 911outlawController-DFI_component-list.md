### Component List

| **Component** | **Specification / Description** | **Qty** | **Notes / Purpose** |
| --- | --- | --- | --- |
| **Microcontroller Board** | Arduino Nano, Uno, or compatible ATmega328P / 5V MCU | 1 | Runs telemetry acquisition, ISR tach counting, and LCD rendering |
| **Alphanumeric Display** | 16x2 Character LCD with I2C Backpack (PCF8574, default addr `0x27`) | 1 | Visual telemetry and Spartan diagnostic stage readouts |
| **Real-Time Clock (RTC)** | DS3231 I2C RTC Module | 1 | Local 24-hr time display (`HH:MM:SS`) with coin-cell backup |
| **Optocoupler / Isolator** | PC817, 4N25, or 4N35 | 1 | Isolates MCU Pin 2 from inductive flyback on the DFI `TAC` pin |
| **Wideband Controller** | 14Point7 Spartan Lambda Controller (LSU 4.9) | 1 | Linear analog output ($0.0\text{--}5.0\,\text{V}$) to Pin A2 |
| **Fuel Pressure Sender** | 0--15 PSI or 0--100 PSI 3-wire gauge pressure transducer (0.5--4.5V output) | 1 | Analog 5V ratiometric pressure input to Pin A3 |
| **DFI Ignition Boxes** | Pacific Motorsports / Electromotive DFI units (Twin-Plug) | 2 |

Box 1 (Top Plugs) and Box 2 (Bottom Plugs)

 |
| **Pushbutton** | Momentary SPST tactile switch (normally open) | 1 | Screen cycle button between Pin 3 and GND (internal pullup) |
| **Resistors (Voltage Divider)** | $30\,\text{k}\Omega$ ($1/4\text{W}$, 1%) and $7.5\,\text{k}\Omega$ ($1/4\text{W}$, 1%) | 1 ea | 5:1 VBAT divider network ($15.0\,\text{V} \rightarrow 3.0\,\text{V}$) to Pin A6 |
| **Resistor (Tach Opto Input)** | $1\,\text{k}\Omega$ to $2.2\,\text{k}\Omega$ ($1/2\text{W}$) | 1 | Current-limiting resistor in series with optocoupler input diode |
| **Resistor (Opto Pullup)** | $4.7\,\text{k}\Omega$ to $10\,\text{k}\Omega$ ($1/4\text{W}$) | 1 | Collector pull-up resistor to +5V on MCU Pin 2 |
| **Decoupling Capacitors** | $0.1\,\mu\text{F}$ (100nF) Ceramic | 4 | Noise bypassing across A0, A1, A2, A3 to AGND |
