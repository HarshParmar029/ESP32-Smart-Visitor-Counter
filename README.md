# ESP32 Smart Visitor Counter & Energy Saver

Bi-directional visitor counter built on the ESP32 with a custom 2-layer KiCad PCB. Two IR sensors detect entry and exit using a sequential state machine; a 0.96" I2C OLED shows the live occupancy count; a 5V opto-isolated relay switches the AC load OFF automatically when the room is empty.

Non-profit student project by Harsh, B.Tech ICT, Marwadi University, Rajkot, India.

## How it works
- Entry: Sensor A then Sensor B -> count + 1
- Exit: Sensor B then Sensor A -> count - 1 (never below 0)
- Count > 0 -> relay ON, count = 0 -> relay OFF

## Hardware
ESP32, 2x IR sensors, 0.96" I2C OLED (128x64), 5V opto-isolated relay module, USB-C 5V power input.

## PCB
KiCad, 2-layer FR-4, 1 oz copper, HASL, 120.65 mm x 66.04 mm, copper ground pours on both layers, DRC 0 errors / 0 warnings. Fabricated with PCBWay sponsorship.

## Safety
The relay switches 220V AC mains. Keep mains wiring isolated from the low-voltage section and use proper enclosure and insulation.

## Future scope
Wi-Fi cloud logging (Blynk / AWS IoT) and ToF/LiDAR sensors for side-by-side entry detection.
