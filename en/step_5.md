## Add the LED indicator

--- task ---

Insert the LED into the breadboard: position the LED so that its legs are in separate rows and there is space to connect a resistor and jumper wires.
![The LED has been inserted into the breadboard with its legs in separate rows and space around it.](images/tank-sensor2.png){:width="300px"} 
--- /task ---

--- task ---

Check which leg of the LED is longer (anode, positive) and which is shorter (cathode, negative).

--- /task ---

--- task ---

Connect the shorter leg of the LED to one end of a **220Ω resistor**. This resistor will limit the current through the LED. 

Then, connect the other end of the resistor to the ground rail on your breadboard.
![A resistor has been connected to the shorter leg of the LED and the ground rail.](images/tank-sensor3.png){:width="300px"} 

--- /task ---

--- task ---

Use a jumper wire to connect the long leg of your LED to **3V3(OUT) (GP36)** to check that the LED lights up. This pin always puts out 3V.
![A jumper wire has been added between the long leg of the LED and GP36.](images/tank-sensor6.png){:width="300px"} 

--- /task ---

--- task ---

If your LED does not light:
- Check that you have connected the LED's long leg to the resistor and its short leg to the ground rail — LEDs only work one way around
- Check that the LED and resistor wiring are not interfering with the sensor circuit and that no components are shorted
- Replace the LED and check again

--- /task ---

--- task ---

Move the jumper wire connected to the LED from **GP36** to **GP13**. This pin will control the LED signal.
![The jumper wire connected to the long leg of the LED has been moved to GP13.](images/tank-sensor5.png){:width="300px"} 

--- /task ---