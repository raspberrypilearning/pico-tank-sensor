## Code the LED indicator

Edit your program so that it can use both the **distance sensor** and an **LED** to show when the tank is too empty.

--- task ---
Get the measurement you took earlier for the distance from the sensor to just above the bottom of the tank. This will help set your 'too empty' distance threshold. The example code uses a distance of 30cm.
![An ultrasonic sensor measuring the distance to the bottom of an empty tank.](images/empty-tank.png){:width="300px"}

--- /task ---

--- task ---

Add the `LED` class to the imports in your code, so the Raspberry Pi Pico can control the LED:

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

sensor = DistanceSensor(echo=14, trigger=15)  # initialise sensor on GP14 and 15

while True:                                   # repeat forever
    print(round(sensor.distance, 2), "m")     # show distance in metres
    sleep(0.5)                                # short pause
--- /code ---

--- /task ---

--- task ---
Add a new line below your sensor definition to create the LED on **GP13**.

--- code ---
---
language: python
filename: tank_sensor.py
line_numbers: true
line_number_start: 4
line_highlights: 5
---
sensor = DistanceSensor(echo=14, trigger=15)    # initialise sensor on GP14 and 15
led = LED(13)                                   # initialise LED on GP13

while True:                                   # repeat forever
    d = sensor.distance                       # set 'd' to sensor measurement value
    print("Distance:", round(d, 2), "m")      # show distance in metres
    sleep(0.5)                                # check every 0.5 seconds
--- /code ---

--- /task ---

--- task ---
Inside the loop, turn the LED **on** when the distance is 30cm (0.30m) or more and **off** otherwise.

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

    if d >= 0.30:      # 30cm or more
        led.on()       # turn LED on
    else:
        led.off()      # turn LED off

    sleep(0.5)         # check every 0.5 seconds
--- /code ---

--- /task ---

--- task ---
Click on **Run** to test your program. Move an object or the water surface closer to or further away from the sensor to see the LED turn on when the distance is 30cm or more, and off when the object is nearer.
--- /task ---

### Test and calibrate

--- task ---
Try the setup over your tank or barrel. Observe when the LED turns on as the water level changes.
--- /task ---

--- task ---
If you need to, adjust the **threshold** (for example, change the value in `if d>= 0.30` to `0.35`m or `0.25`m) to match the water level that is 'too low' for your tank.
--- /task ---


