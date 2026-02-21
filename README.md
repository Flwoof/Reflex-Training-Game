# Reflex-Training-Game
### This is a simple game that is intended to help train reflexes. The game increases in difficulty after each correct reaction.


### <ins>HOW TO RUN</ins>

_Files from here_ <br/>
  - Coding file titled "Reaction Game Code" <br/>

_Libraries you Need_ <br/>
  - Adafruit SSD1306 by Adafruit (install from Arduino IDE library manager) <br/>
  - Adafruit GFX by Adafruit (install from Arduino IDE library manager) <br/>
  
_Hardware Needed_ <br/>
  - Arduino Mega <br/>
  - 2-12 LEDs (any color) <br/>
  - 1 pushbutton (you can use more if you want different buttons to control reset/enter)
  - 2-12 TCRT5000 sensors <br/>
  - .09" OLED screen <br/>
  - 360 degree servo <br/>
  - 2 one-sided Servo arm bit. I cut one in half and glued it to the other to get my desired length.  <br/>
  
## **If you've never installed a library before:**
1. Open Arduino IDE
2. Click "Sketch" (top left of screen)
3. Click "Include Library"
4. Select "Library Manager"
5. Type name of desired library in search bar, **make sure the author name is the same**
  
**How to Play the Game** <br/>
The game should start as soon as you plug the Arduino in. <br/>
One LED should light up, you're trying to time your button press with when the arm passes over the sensor connected to that LED. <br/>
If you press at the correct time, the score counter on the OLED screen will increment by 1. The arm will now start to spin the opposite direction. <br/>
If you press at an incorrect time, the score will not go up and the game will end. <br/>
The game continues forever, although there is a speed cap after level 35.<br/>

### _Game Features_ <br/>
- Arm has 360 degree rotation <br/>
- Detection sensors can detect the arm accurately <br/>
- System is able to tell the difference between correct vs incorrect press <br/>
- OLED scoreboard displays and increments score accurately <br/>
- When the game ends the LEDs preform a "game-over" light sequence <br/>

## Known Issues <br/>
Every 360 degree servo is slightly different. While the resting point for most is intended to be 90, and any value greater or less than 90 should make the servo move, the one I used will not move Counter-Clockwise unless you pass in a value greater than 96 for Spinner.write(*put value here*). If your Servo isn't moving on the earlier levels or is moving too fast I'd reccomend changing the first few values in the spinSpeeds array. Closer to 90 = slower, further from 90 = faster. <br/>

The debounce time is currently at 150ms, which is optimal for this project. Regardless, if you spam the pushbutton while over the sensor your correct press can get counted as incorrect <br/>

The current code is intended for 2 LEDs instead of 12. To adjust the code for 12 LEDS (or your desired number) simply copy paste lines 78-90 (both inclusive) for each additional LED you would like. Adjust the number on line 78 to be the pin number for your additional LED(s). variable "reading" on line 80 to be reading3 if 3rd LED, reading4 if 4th LED, reading5 if 5th LED, etc.





