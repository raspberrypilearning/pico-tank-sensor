## Measure distance with PicoZero

To program the Raspberry Pi Pico, you will need the [Thonny IDE](http://thonny.org/){:target="_blank"} and MicroPython packages installed. 

[Instructions for this process are available here.](https://learning-admin.raspberrypi.org/en/projects/getting-started-with-the-pico/2){:target="_blank"}  

--- task ---
Open Thonny and create a new file called `tank_sensor.py`.
--- /task ---

--- task ---
Add code to measure distance using the ultrasonic sensor.

--- code ---
---
language: python
filename: tank_sensor.py
line_numbers: true
---

from picozero import DistanceSensor
from time import sleep

sensor = DistanceSensor(echo=2, trigger=3)

while True:
    d = sensor.distance
    print("Distance:", round(d, 2), "m")
    sleep(0.5)
--- /code ---

--- /task ---

--- task ---
Click **Run**.  
Move your hand below the sensor — the distance values should change.

--- collapse ---

---

title: TypeError: can't convert NoneType to float

---

Tip: If you see the error `TypeError: can't convert NoneType to float`

This usually means the distance sensor did not give a proper reading.
The most common cause is a loose connection, but it could be something else stopping the sensor from working.

Check these things:

- Check that no jumper wires are loose or leaning in the breadboard/circuit.
- Make sure the sensor is facing an object that is not too close (2cm) or too far away (4m).
- Check your voltage divider resistors are properly connected
- Do you have the right `trigger` and `echo` pins set?

--- /collapse ---

--- /task ---

--- task ---
Note the distance from the sensor when the tank is empty.  
This will help set your threshold in the next step.
![Ultrasonic sensor measuring variable distance above an empty tank](images/empty-tank.png){:width="300px"} 

--- /task ---
