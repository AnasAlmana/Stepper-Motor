# Stepper-Motor
## Arduino code to run Stepper-Motor

1- Login to tinkercad

2-Choose Stepper-Motor circuit and drag it to the workspace.

3-Write the code to operate the Stepper-Motor circuit
```
#include <Stepper.h>

const int stepsPerRevolution = 120;
Stepper myStepper(stepsPerRevolution, 8, 9, 10, 11);
int stepCount =0;

  
void setup()
{
  
  Serial.begin(9600);
  
  
}

void loop()
{
  
  int sensorReading = analogRead(A0);
  int motorSpeed = map(sensorReading, 0, 1023, 0, 250);
  if (motorSpeed > 0){
    myStepper.setSpeed(motorSpeed);
    myStepper.step(stepsPerRevolution / 100);
    Serial.println(sensorReading);
  }
  
  
}
```


![66C4DE80-2D02-4DA7-BA9F-3EFC4041BAEB_1_201_a](https://user-images.githubusercontent.com/80279479/180820070-913fb396-1741-4933-a27e-0213e1c65dfc.jpeg)
