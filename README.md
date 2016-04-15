Stay With Me: Glowing Interactive Hands 
Morgan Fiddes-Waldon

-Designed as an exploration of long distance connections, experimenting with human methods of communication. Slow design that reduces communication to the notion of presence. The light is on or it's off, there is another presence or there is not. This design is intended to provoke consideration of our interactions with one another- how do we prioritize words over other forms of communication, and what happens when that hierarchy is questioned?

Bill of Materials:
-3 part 3D printed plastic enclosure 

-12 black momentary push buttons with washers

-1 arduino uno 

-1 escudo dos 

-1 3V inverter 

-3 white electroluminescent panels 

-3 aqua electroluminescent panels

-2 10Ohm resistors 

-1 Solderless Breadboard- 400 contacts

-1 predrilled single-sided circuitboard 

-1 5VDC AC/DC power adapter 

-2 petG molded plastic inserts 

-adhesive

Construction: 
(preparation) 

-upload code to arduino uno

-3D print 3 STL files, white filament 

-solder 2 wires on each push button, shrink wrap and screw into both STL components (2/3) 

-solder 3 sets of headers on escudo dos shield and connect to arduino uno

-re-solder all 6 electroluminescent panels to extend length- 3 should be longer than the other three to accomodate distance to
separate panel.

1. 
-solider push buttons from one panel to predrilled single-sided circuit board : one wire from the button is secured in one connecting path, the other in a separate one.
-attach one connecting wire to each side of the circuit board, connecting the two sides of the momentary pushbuttons
-extend the two connecting wires through the hole in the front of the box 

2. (panel 1/2) 
-secure escudo dos (along with arduino uno) in the box (STL 3/3) separate from the circuit board created in step 1
-secure solderless breadboard next to it 

3. (escudo dos) 
-attach connecting wires to digital ports 8 and 12 on escudo dos (2total)
-attach connecting wires to both ground ports and to 5V (3total) 
-connect ground wires along negative strip (breadboard) R of button switch
-connect ports 8 and 12 to repective switch circuits (1 on each) 
-1 5V powering both buttons , running along negative (1) 

4. (solderless breadboard- escudo dos, panel 1) 
-wire connecting positive horizontal panel to vertical (breadboard) 
-10Ohm resistor between the 5V cable and port (8 or 12- grounded to r of) 

5.(connections) 
-wires connecting first circuit to + and - strip, connect all button from panel 2 along this line
one button= 2 wires, 1 wire in each port (+and-) 
-longer wires connecting pushbutton input (panel 2) to all 6 buttons (panel 1) 

Working Final Code (April 15, 2016)

Credit to: Mike Grusin (of SparkFun) and Arduino Preset Tutorial

// Test sketch for El Escudo Dos
// Turn each EL channel (A-H) on in sequence and repeat
// Morgan Fiddes-Waldon, credits to Mike Grusin, SparkFun Electronics
char inputButtonState;
void setup() {                
  // The EL channels are on pins 2 through 9
  // Initialize the pins as outputs
  pinMode(2, OUTPUT);  // channel A  
  pinMode(3, OUTPUT);  // channel B   
  pinMode(4, OUTPUT);  // channel C
  pinMode(5, OUTPUT);  // channel D    
  pinMode(6, OUTPUT);  // channel E
  pinMode(7, OUTPUT);  // channel F
  pinMode(8, OUTPUT);  // channel G
  pinMode(9, OUTPUT);  // channel H
  // We also have two status LEDs, pin 10 on the Escudo, 
  // and pin 13 on the Arduino itself
  pinMode(10, OUTPUT);     
  pinMode(13, OUTPUT);   
  pinMode(8,INPUT);         // Initialize Arduino Digital Pins 8 as input for connecting Pushbutton
   pinMode(10, OUTPUT);     
  pinMode(13, OUTPUT);   
  pinMode(12,INPUT);         // Initialize Arduino Digital Pins 8 as input for connecting Pushbutton  
}

void loop() 

{
  inputButtonState = digitalRead(8); //Read the Pushbutton state.
 
  if (inputButtonState == HIGH) 
  {     
    digitalWrite(2, HIGH);  //Switch on LED
  } 
  else 
  {
    digitalWrite(2, LOW);   //Switch off LED
  }
    inputButtonState = digitalRead(12); //Read the Pushbutton state.
    inputButtonState = digitalRead(8); //Read the Pushbutton state.
 
  if (inputButtonState == HIGH) 
  {     
    digitalWrite(3, HIGH);  //Switch on LED
  } 
  else 
  {
    digitalWrite(3, LOW);   //Switch off LED
  }
    inputButtonState = digitalRead(12); //Read the Pushbutton state.
 
  if (inputButtonState == HIGH) 
  {     
    digitalWrite(4, HIGH);  //Switch on LED
  } 
  else 
  {
    digitalWrite(4, LOW);   //Switch off LED
  }
      inputButtonState = digitalRead(12); //Read the Pushbutton state.
 
  if (inputButtonState == HIGH) 
  {     
    digitalWrite(5, HIGH);  //Switch on LED
  } 
  else 
  {
    digitalWrite(5, LOW);   //Switch off LED
  }


}
 
Previous Working Code (2 outputs instead of 4) 
March 23, 2016
// Test sketch for El Escudo Dos
// Turn each EL channel (A-H) on in sequence and repeat
// Mike Grusin, SparkFun Electronics
char inputButtonState;
void setup() {                
  // The EL channels are on pins 2 through 9
  // Initialize the pins as outputs
  pinMode(2, OUTPUT);  // channel A  
  pinMode(3, OUTPUT);  // channel B   
  pinMode(4, OUTPUT);  // channel C
  pinMode(5, OUTPUT);  // channel D    
  pinMode(6, OUTPUT);  // channel E
  pinMode(7, OUTPUT);  // channel F
  pinMode(8, OUTPUT);  // channel G
  pinMode(9, OUTPUT);  // channel H
  // We also have two status LEDs, pin 10 on the Escudo, 
  // and pin 13 on the Arduino itself
  pinMode(10, OUTPUT);     
  pinMode(13, OUTPUT);   
  pinMode(8,INPUT);         // Initialize Arduino Digital Pins 8 as input for connecting Pushbutton
   pinMode(10, OUTPUT);     
  pinMode(13, OUTPUT);   
  pinMode(12,INPUT);         // Initialize Arduino Digital Pins 8 as input for connecting Pushbutton  
}

void loop() 

{
  inputButtonState = digitalRead(8); //Read the Pushbutton state.
 
  if (inputButtonState == HIGH) 
  {     
    digitalWrite(2, HIGH);  //Switch on LED
  } 
  else 
  {
    digitalWrite(2, LOW);   //Switch off LED
  }
    inputButtonState = digitalRead(12); //Read the Pushbutton state.
 
  if (inputButtonState == HIGH) 
  {     
    digitalWrite(3, HIGH);  //Switch on LED
  } 
  else 
  {
    digitalWrite(3, LOW);   //Switch off LED
  }


}

Original Code, escudo dos:
February 10, 2016
// Test sketch for El Escudo Dos
// Turn each EL channel (A-H) on in sequence and repeat
// Mike Grusin, SparkFun Electronics

void setup() {                
  // The EL channels are on pins 2 through 9
  // Initialize the pins as outputs
  pinMode(2, OUTPUT);  // channel A  
  pinMode(3, OUTPUT);  // channel B   
  pinMode(4, OUTPUT);  // channel C
  pinMode(5, OUTPUT);  // channel D    
  pinMode(6, OUTPUT);  // channel E
  pinMode(7, OUTPUT);  // channel F
  pinMode(8, OUTPUT);  // channel G
  pinMode(9, OUTPUT);  // channel H
  // We also have two status LEDs, pin 10 on the Escudo, 
  // and pin 13 on the Arduino itself
  pinMode(10, OUTPUT);     
  pinMode(13, OUTPUT);    
}

void loop() 
{

    digitalWrite(2, HIGH);   // turn the EL channel on
    delay(1000);              // wait for 1/10 second
    digitalWrite(2, LOW);    // turn the EL channel off 
    delay(100);              // wait for 1/10 second


}

  
/*  
  
  int x,status;
  // Step through all eight EL channels (pins 2 through 9)
  for (x=2; x<=9; x++)
  {
    digitalWrite(x, HIGH);   // turn the EL channel on
    delay(100);              // wait for 1/10 second
    digitalWrite(x, LOW);    // turn the EL channel off

    digitalWrite(10, status);   // blink both status LEDs
    digitalWrite(13, status);
    status = !status; 
  }  
}
*/

Initial Code: Pushbutton, arduino preset 
January 20, 2016
//Pushbutton switch demo: LED is connected to digital pin 8 and Pushbutton is connected to digital pin 12. 
//The LED glows when the button is pressed.
 
char inputButtonState;
 
void setup()   
{                
  pinMode(8, OUTPUT);        // Initialize Arduino Digital Pins 8 as output for connecting LED
  pinMode(12,INPUT);         // Initialize Arduino Digital Pins 12 as input for connecting Pushbutton
}
 
 
void loop()                     
{
  inputButtonState = digitalRead(12); //Read the Pushbutton state.
 
  if (inputButtonState == HIGH) 
  {     
    digitalWrite(8, HIGH);  //Switch on LED
  } 
  else 
  {
    digitalWrite(8, LOW);   //Switch off LED
  }
 
}



