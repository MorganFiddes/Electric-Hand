# Electric-Hand
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
