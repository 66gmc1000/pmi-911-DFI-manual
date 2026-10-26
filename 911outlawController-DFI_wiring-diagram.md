========================================================================================

                                    VEHICLE POWER & GROUND

========================================================================================

Switched +12V Bus (Run/Start) ──┬──> [DFI Box 1 BIG RED (10A Fused)]

                                ├──> [DFI Box 2 BIG RED (10A Fused)]

                                ├──> [Spartan Controller 12V Power (5A Fused)]

                                ├──> [MCU Vin (via 500mA inline fuse or 7805 regulator)]

                                └──> [30k Resistor] ──┬──> MCU Pin A6 (VBAT Sense)

                                                      │

                                                 [7.5k Resistor]

                                                      │

CHASSIS / ENGINE COMMON GROUND ─┬──> [30k/7.5k Divider Ground]

                                ├──> [DFI Box 1 BIG BLACK Lead]

                                ├──> [DFI Box 2 BIG BLACK Lead]

                                ├──> [Spartan Power Ground & Electronics Ground]

                                ├──> [Fuel Pressure Transducer 0V / GND]

                                └──> MCU GND / AGND

========================================================================================

                          DFI CRANKFIRE IGNITION SIGNALS

========================================================================================

DFI Box 1 (Top Plugs):

   [ADV] Terminal ─────────────────────────────┬──> MCU Pin A0 (Top Timing Sense)

                                               │

                                          [0.1uF Cap]

                                               │

   [GND] Terminal ─────────────────────────────┴──> MCU Common GND

DFI Box 2 (Bottom Plugs):

   [ADV] Terminal ─────────────────────────────┬──> MCU Pin A1 (Bottom Timing Sense)

                                               │

                                          [0.1uF Cap]

                                               │

   [GND] Terminal ─────────────────────────────┴──> MCU Common GND

DFI Box 1 Tachometer Output:

   [TAC] Terminal ───> [1k to 2.2k Resistor] ──> [Optocoupler Anode (Pin 1)]

   [GND] Terminal ─────────────────────────────> [Optocoupler Cathode (Pin 2)]

   MCU +5V Rail  ────> [4.7k Pull-up] ──┬──────> [Optocoupler Collector (Pin 4)]

                                        │

   MCU Pin 2 (Interrupt) ───────────────┘

   MCU GND ────────────────────────────────────> [Optocoupler Emitter (Pin 3)]

========================================================================================

                         WIDEBAND, FUEL PRESSURE & INTERFACE

========================================================================================

14Point7 Spartan Lambda:

   [Linear Output 0-5V] ───────────────────────┬──> MCU Pin A2 (AFR/Lambda Input)

                                               │

                                          [0.1uF Cap]

                                               │

   [Signal Ground] ────────────────────────────┴──> MCU Common GND

Fuel Pressure Transducer:

   [+5V Power] ───────────────────────────────────> MCU +5V Rail

   [Ground] ──────────────────────────────────────> MCU Common GND

   [Signal Out 0.5-4.5V] ──────────────────────┬──> MCU Pin A3 (Fuel PSI Input)

                                               │

                                          [0.1uF Cap]

                                               │

                                              GND

16x2 I2C LCD Display:

   [VCC] ─────────────────────────────────────────> MCU +5V Rail

   [GND] ─────────────────────────────────────────> MCU Common GND

   [SDA] ─────────────────────────────────────────> MCU Pin A4 (or dedicated SDA)

   [SCL] ─────────────────────────────────────────> MCU Pin A5 (or dedicated SCL)

DS3231 RTC Module:

   [VCC] ─────────────────────────────────────────> MCU +5V Rail

   [GND] ─────────────────────────────────────────> MCU Common GND

   [SDA] ─────────────────────────────────────────> MCU Pin A4 (Parallel I2C Bus)

   [SCL] ─────────────────────────────────────────> MCU Pin A5 (Parallel I2C Bus)

UI Pushbutton:

   [Terminal 1] ──────────────────────────────────> MCU Pin 3

   [Terminal 2] ──────────────────────────────────> MCU Common GND
