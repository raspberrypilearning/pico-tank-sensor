## Code the LED Indicator

Edit your program so it can use both the **distance sensor** and an **LED** to show when the bucket is too empty.

--- task ---

Add the `LED` class to the imports in your code, so the Pico can control it:

--- code ---
---
language: python
filename: tank_sensor.py
line_numbers: true
line_number_start: 1
line_highlights: 1
---
from picozero import DistanceSensor, LED
from time import sleep

sensor = DistanceSensor(echo=2, trigger=3)

while True:
    d = sensor.distance
    print("Distance:", round(d, 2), "m")
    sleep(0.5)
--- /code ---

--- /task ---

--- task ---
Add a new line below your sensor definition to create the LED on **Pin 15**.

--- code ---
---
language: python
filename: tank_sensor.py
line_numbers: true
line_number_start: 4
line_highlights: 5
---
sensor = DistanceSensor(echo=2, trigger=3)
led = LED(15)

while True:
    d = sensor.distance
    print("Distance:", round(d, 2), "m")
    sleep(0.5)
--- /code ---

--- /task ---

--- task ---
Inside the loop, add an `if` statement to turn the LED **on** when the distance is more than 30 cm (0.30 m) and **off** otherwise.

--- code ---
---
language: python
filename: tank_sensor.py
line_numbers: true
line_number_start: 7
line_highlights: 11-14
---
while True:
    d = sensor.distance
    print("Distance:", round(d, 2), "m")

    if d >= 0.30:      # Greater than 30 cm
        led.on()
    else:
        led.off()

    sleep(0.5)
--- /code ---

--- /task ---

--- task ---
Click **Run** to test your program.  
Move an object or the water surface closer or farther from the sensor to see the LED turn on when the distance exceeds 30 cm, and off when it’s nearer.
--- /task ---

### Test and Calibrate

--- task ---
Try the setup over your tank or barrel.  
Observe when the LED turns on as the water level changes.
--- /task ---

--- task ---
If needed, adjust the **threshold** (for example, change ` if d>= 0.30` to `0.35` m or `0.25` m) to match the “too low” water level in your tank.
--- /task ---


