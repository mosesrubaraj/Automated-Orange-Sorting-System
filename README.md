# Smart Light Control System
This project aims to detect human presence using a PIR sensor and measure sunlight illuminance with an LDR (Light Dependent Resistor). Based on the readings from these sensors, an LED light is controlled by an Arduino Uno, optimizing indoor lighting based on occupancy and ambient light levels.

## Flowchart
![image](https://github.com/user-attachments/assets/15faec6b-2d6a-4541-a287-b0559c2e9e87)

Project consists of two main cases. In the first case, a PIR sensor detects the presence of a person in the room and sends signals to an Arduino. If a person is detected, it proceeds to the second case. In the second case, an LDR (Light Dependent Resistor) measures the sunlight level in the room. If sunlight presence is low, this case is successful.

The LED will turn on only if both conditions are met:

If no one is in the room, the LED will not glow.
If a person is present but sunlight levels are high, the LED will also remain off.
The LED will only light up if a person is present and the sunlight in the room is low.

## Circuit Diagram
![image](https://github.com/user-attachments/assets/b88c2b80-daad-4577-86b8-11f9d4ce3310)

1)PIR 				                  2) LDR				 3) Arduino UNO
4)Resistor                      5) LED


## PROGRAM 
int buttonState = 0;
int value=0;

void setup()

{

  pinMode(2, INPUT);
  pinMode(13, OUTPUT);  
  pinMode(A0, INPUT);
  
}

void loop()

{

  // read the state of the pushbutton
  value= analogRead(A0);
  buttonState = digitalRead(2);
  // check if pushbutton is pressed. if it is, the
  // button state is HIGH
  
  if (buttonState == HIGH) {
    if(value<10)
    {
     digitalWrite(13, HIGH);
     Serial.println("Light ON");
     Serial.println(value);
    }
    else
    {
     digitalWrite(13, LOW);
     Serial.println("Light OFF");
     Serial.println(value);
     } 
  }
  else {
    digitalWrite(13, LOW);
  }
  delay(2); // Delay a little bit to improve simulation performance
}






https://github.com/user-attachments/assets/2dcc9120-6c94-4cc0-8125-f32590869159


