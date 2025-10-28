## Code the LED Indicator

--- task ---
Edit your program to include both the sensor and the LED.

--- code ---
---
language: python
filename: tank_sensor.py
line_numbers: true
---

from picozero import DistanceSensor, LED
from time import sleep

sensor = DistanceSensor(echo=16, trigger=17)
led = LED(15)

EMPTY_DISTANCE = 0.40   # in meters
BUFFER = 0.02       # in meters - this allows for movement in the water surface

while True:
    d = sensor.distance
    print("Distance:", round(d, 2), "m")

    if d >= EMPTY_DISTANCE:
        led.on()
    elif d < (EMPTY_DISTANCE - BUFFER):
        led.off()

    sleep(0.5)
--- /code ---

--- /task ---

--- task ---
Click **Run** again.  
Move an object or water surface closer or farther from the sensor to see the LED change.
--- /task ---

### Test and Calibrate

--- task ---
Try the setup over your water barrel.  
Fill and empty the tank while watching when the LED turns on.
--- /task ---

--- task ---
Adjust `EMPTY_DISTANCE` to match your “too empty” water level.
--- /task ---

--- task ---
If the LED flickers near the threshold, increase `BUFFER` slightly (for example, 0.03 m).
--- /task ---
