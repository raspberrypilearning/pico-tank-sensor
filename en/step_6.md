## Code the LED Indicator

Edit your program so it can use both the **distance sensor** and an **LED** to show when the bucket is too empty.

--- task ---
Note the distance from the sensor when the tank is empty.  
This will help set your 'empty' distance threshold. The example code uses a distance of 30cm.
![Ultrasonic sensor measuring variable distance above an empty tank](images/empty-tank.png){:width="300px"} 

--- /task ---

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
from picozero import DistanceSensor, LED      # import LED class too
from time import sleep                        # import delay function

sensor = DistanceSensor(echo=14, trigger=15)  # initialise sensor on GP 14 & 15

while True:                                   # repeat forever
    print(round(sensor.distance, 2), "m")     # show distance in metres
    sleep(0.5)                                # short pause
--- /code ---

--- /task ---

--- task ---
Add a new line below your sensor definition to create the LED on **Pin 13**.

--- code ---
---
language: python
filename: tank_sensor.py
line_numbers: true
line_number_start: 4
line_highlights: 5
---
sensor = DistanceSensor(echo=14, trigger=15)    # initialise sensor on GP 14 & 15
led = LED(13)                                   # initialise LED on GP 13

while True:                                   # repeat forever
    d = sensor.distance                       # set 'd' to sensor measurement value
    print("Distance:", round(d, 2), "m")      # show distance in metres
    sleep(0.5)                                # check every 0.5 seconds
--- /code ---

--- /task ---

--- task ---
Inside the loop, turn the LED **on** when the distance is more than 30 cm (0.30 m) and **off** otherwise.

--- code ---
---
language: python
filename: tank_sensor.py
line_numbers: true
line_number_start: 7
line_highlights: 11-14
---
while True:                                   # repeat forever
    d = sensor.distance                       # set 'd' to sensor measurement value
    print("Distance:", round(d, 2), "m")      # show distance in metres

    if d >= 0.30:      # Greater than 30 cm
        led.on()       # Turn LED on
    else:
        led.off()      # Turn LED on

    sleep(0.5)         # check every 0.5 seconds
--- /code ---

--- /task ---

--- task ---
Click **Run** to test your program.  
Move an object or the water surface closer or further away from the sensor to see the LED turn on when the distance exceeds 30 cm, and off when it’s nearer.
--- /task ---

### Test and Calibrate

--- task ---
Try the setup over your tank or barrel.  
Observe when the LED turns on as the water level changes.
--- /task ---

--- task ---
If needed, adjust the **threshold** (for example, change `if d>= 0.30` to `0.35`m or `0.25`m) to match the “too low” water level in your tank.
--- /task ---


