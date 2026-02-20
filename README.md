# Reflex-Training-Game
### This is a simple game that is intended to help train reflexes. The game increases in difficulty after each correct reaction. To build this circuit, you will need one 360 degree servo, 12 LEDs, 1 pushbutton (you need at least 1, but I am using a seperate one for resetting the game), 12 TCRT5000 sensors, and one .09" OLED screen.


### <ins>HOW TO RUN</ins>

_Files from here_ <br/>
  - Coding file titled "Reaction Code" <br/>

_Libraries you Need_ <br/>
  - Adafruit SSD1306 by Adafruit (install from Arduino IDE library manager) <br/>
  - Adafruit GFX by Adafruit (install from Arduino IDE library manager) <br/>
  
_Hardware Needed_ <br/>
  - Arduino Mega <br/>
  - 12 LEDs (any color) <br/>
  - 1 pusbutton (you can use more if you want different buttons to control reset/enter)
  - 12 TCRT5000 sensors <br/>
  - .09" OLED screen <br/>
  - 360 degree servo <br/>
  - 2 servo one arm bits. I cut one in half and glued it to the other to get the desired length. <br/>
  
## **If you've never installed a library before:**
1. Open Arduino IDE
2. Click "Sketch" (top left of screen)
3. Click "Include Library"
4. Select "Library Manager"
5. Type name of desired library in search bar, **make sure the author name is the same**
  
**How to Play the Game** <br/>
The game should start as soon as you plug the Arduino in <br/>
One LED should light up, you're trying to time your button press with when the arm passes over the sensor connected to that LED <br/>
If you press at the correct time, the score counter on the OLED screen will increment by 1. The arm will now start to spin the opposite direction. <br/>
If you press at an incorrect time, the score will not go up and the game will end <br/>
The game continues forever, although there is a speed cap after level 35.<br/>

_Game Features_ <br/>
- Arm has 360 degree rotation<br/>
- Detection sensors can detect the arm accurately <br/>
- System is able to tell the difference between correct vs incorrect press <br/>
- OLED scoreboard displays and increments score accurately <br/>
- When the game ends the LEDs preform a "game-over" light sequence <br/>

## Known Issues <br/>
Every 360 degree servo is slightly different. While the resting point for most is around 90, the one I used will not move Counter-Clockwise unless you pass in a value greater than 96 for Spinner.write(*put value here*). If your Servo isn't moving on the earlier levels I'd reccomend changing the first few values in the spinSpeeds array <br/>
<br/>
The debounce time is currently at 150ms, which is optimal for this project. Regardless, if you spam the pushbutton while over the sensor your correct press can get counted as incorrect <br/>





