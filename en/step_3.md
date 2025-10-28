## Wire the Sensor Circuit

You will now connect your **HC-SR04P ultrasonic sensor** to the **Raspberry Pi Pico** using jumper wires on a breadboard.

### You will need:
- Raspberry Pi Pico  
- HC-SR04P ultrasonic distance sensor (3.3 V logic)  
- Breadboard  
- Jumper wires (male-to-male)

--- task ---
Place the Pico on the breadboard.  
Insert it so that the USB port faces outward and each side of pins sits on a separate breadboard row.
--- /task ---

--- task ---
Place the HC-SR04P sensor on the breadboard.  
Make sure its pins (VCC, TRIG, ECHO, GND) are accessible and not shorting to each other.
--- /task ---

--- task ---
Connect **VCC on the HC-SR04P** to **Pin36** on the Pico. This powers the ultrasonic sensor with safe 3.3 V.  
--- /task ---

--- task ---
Connect **GND on the HC-SR04P** to any **GND** on the Pico. 
This completes the power circuit.
--- /task ---

--- task ---
Connect **TRIG on the HC-SR04P** to **GP17** on the Pico.  
This pin sends the pulse signal to start a distance measurement.
--- /task ---

--- task ---
Connect **ECHO on the HC-SR04P** to **GP16** on the Pico.  
This pin receives the signal that returns from the water surface.
--- /task ---

--- task ---
Check all connections carefully.  
Your wiring should now match the table below:

| HC-SR04P Pin | Connect to | Function |
|---------------|-------------|-----------|
| VCC | 3V3(OUT) | Power (3.3 V) |
| GND | GND | Ground |
| TRIG | GP17 | Trigger output |
| ECHO | GP16 | Echo input |
--- /task ---

--- task ---
Inspect for safety.  
- Ensure all wires are firm and straight.  
- No bare wires should touch each other.  
- The HC-SR04P works directly with 3.3 V logic, so no voltage divider is needed.
--- /task ---

--- task ---
Optional quick test:  
Plug in your Pico.  
If everything is connected correctly, the sensor’s small onboard LED should light up, showing it has power.
--- /task ---
