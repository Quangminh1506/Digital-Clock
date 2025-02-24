# Digital Clock Using Integrated Circuits (ICs)

This project implements a 24-hour digital clock using discrete integrated circuits (ICs), designed and built as a logic design assignment by Group 3 (CC05) at Ho Chi Minh City University of Technology. The clock displays hours, minutes, and seconds on 7-segment displays, with manual time-setting capabilities, leveraging fundamental digital electronics principles.

## Overview

The digital clock uses a combination of ICs to generate a 1 Hz timing signal, count time units, and display them on 7-segment LEDs. It’s an educational demonstration of digital logic, showcasing pulse generation, counter cascading, and reset logic without reliance on microcontrollers.

## Features

- **24-Hour Time Display**: Shows hours (00-23), minutes (00-59), and seconds (00-59) on six 7-segment displays.
- **Manual Time Setting**: Buttons allow incrementing hours and minutes, with debouncing for reliable input.
- **Automatic Timekeeping**: Increments seconds, resets at 60 to update minutes, and resets minutes at 60 to update hours, with a full reset at 24 hours.
- **Modular Design**: Separate modules for signal generation, counting, reset logic, and display.

## Components

- **`IC 555`**: Generates a 1 Hz clock pulse in astable mode (R1 = 470Ω, R2 = 370kΩ, C = 1.5µF).
- **`IC 4026`**: Six units count seconds, minutes, and hours (units and tens), driving common-cathode 7-segment displays.
- **`IC 7411`**: Triple AND gate manages reset logic for seconds-to-minutes, minutes-to-hours, and 24-hour reset.
- **7-Segment Displays**: Six displays for real-time visualization of time.
- **Power Supply**: 5V regulated DC source with decoupling capacitors.
- **Resistors & Capacitors**: Limit current, stabilize power, and set timing.
- **Buttons**: For manual time adjustment with debouncing circuits.


## How It Works

1. **Clock Signal**: IC 555 generates a 1 Hz pulse as the time base.
2. **Counting**: IC 4026 counters increment seconds, minutes, and hours, cascading carry signals between units and tens.
3. **Reset Logic**: IC 7411 detects counts of 60 (seconds/minutes) and 24 (hours) to reset counters and increment the next unit.
4. **Display**: Each IC 4026 drives a 7-segment display, updating in real-time.
5. **Time Setting**: Buttons adjust hours and minutes, with debouncing to ensure stable input.
