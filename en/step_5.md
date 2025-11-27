## Add the LED Indicator

--- task ---

Insert the LED into the breadboard. Place the LED so that its legs are in separate rows, allowing space to connect a resistor and jumper wires.
![Breadboard showing Raspberry Pi Pico H connected to an HC-SR04 ultrasonic sensor and an uncoonected LED](images/tank-sensor2.png)
--- /task ---

--- task ---

Confirm which leg of the LED is longer (anode, positive) and which is shorter (cathode, negative).

--- /task ---

--- task ---

Attach the shorter leg of the LED to the ground rail on the edge of your breadboard.
![Breadboard circuit with Raspberry Pi Pico H and HC-SR04 ultrasonic sensor; LED connected to GND](images/tank-sensor3.png)

--- /task ---

--- task ---
 
Attach the longer leg of the LED to one end of a **220 Ω resistor**; this resistor limits current through the LED.
![Breadboard circuit with Raspberry Pi Pico H and HC-SR04 ultrasonic sensor; LED short leg connected to GND and long leg connected to a 220 ohm resistor](images/tank-sensor4.png)

--- /task ---

--- task ---

Use a jumper wire to connect the resistor to **Pin 36** to make sure that the LED lights up. This pin is always putting out 3V.
![Breadboard circuit showing Raspberry Pi Pico H connected to an HC-SR04 ultrasonic sensor, with a brown jumper linking the LED to pin 36](images/tank-sensor6.png)

--- /task ---

--- task ---

If your LED doesn't light:
- Check you have the LED's long leg connected to the resistor and the short leg connected to GND; LEDs only work one way around.
- Check your LED is not damaged
- Ensure the LED and resistor wiring do not interfere with the sensor circuit and that no components are shorted.
- Replace the LED and check again.

--- /task ---

--- task ---

Move the jumper wire connected to the resistor from `Pin 36` to `Pin 14` on the Pico; this pin will control the LED signal.
![Breadboard circuit showing Raspberry Pi Pico H connected to an HC-SR04 ultrasonic sensor, with a brown jumper linking the LED to pin 14](images/tank-sensor5.png)

--- /task ---