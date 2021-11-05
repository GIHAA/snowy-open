#include <Servo.h>
#include <Oscillator.h>
char in = 0;
//-- Declare the oscillators
Oscillator osc_middle, osc_right, osc_left;

//-- Global parameters for the oscillators
unsigned int A = 40; // Amplitude (higher -> longer steps) set 10-40
unsigned int T = 4000; // Period (lower -> faster moves)

void setup()
{
  Serial.begin(9600);
  delay(1000); // Small startup delay, replace with start-button press (if present)

  //-- Attach the oscillators to the servos
  osc_middle.attach(4); // 2,3 and 4 are the digital pins
  osc_right.attach(3);
  osc_left.attach(2);

  //-- Set the parameters
  osc_middle.SetO(-8); // Correction for the offset of the servos
  osc_right.SetO(0);
  osc_left.SetO(0);

  osc_middle.SetA(10); // Middle motor needs a small amplitude (5-10)
  osc_right.SetA(A);
  osc_left.SetA(A);

  osc_middle.SetT(T); // Set the period of work
  osc_right.SetT(T);
  osc_left.SetT(T);

  //-- Refresh the oscillators
  osc_middle.refresh();
  osc_right.refresh();
  osc_left.refresh();

  //-- Set the phase difference
  //-- This defines the type of movement the robot makes
  osc_middle.SetPh(DEG2RAD( 90 ));
  osc_left.SetPh(  DEG2RAD( 0 ));
  osc_right.SetPh( DEG2RAD( 0 )); // For example, putting 180 here will make the robot spin clockwise

}

void loop()
{ 
        unsigned long time;
        time = millis(); // We use this to determine the duration of the movements


        if (time < 20000) { // Forward


          osc_right.SetPh( DEG2RAD( 0 ));
          osc_left.SetPh( DEG2RAD( 0 ));
        }




        /*} else if(time < 25000) { // Counter clockwise
          osc_right.SetPh( DEG2RAD( 0 ));
          osc_left.SetPh( DEG2RAD( 180 ));
          } else if(time < 30000) { // Backward
          osc_right.SetPh( DEG2RAD( 180 ));
          osc_left.SetPh( DEG2RAD( 180 ));
          } else if(time < 35000) { // Counter clockwise
          osc_right.SetPh( DEG2RAD( 0 ));
          osc_left.SetPh( DEG2RAD( 180 ));
          } else if(time < 40000) { // Idle position
          osc_right.SetPh( DEG2RAD( 90 ));
          osc_left.SetPh( DEG2RAD( 90 ));
          } else if(time < 45000) { // Forward
          osc_right.SetPh( DEG2RAD( 0 ));
          osc_left.SetPh( DEG2RAD( 0 ));
          } else if(time < 55000) { // It will slowly decelerate
          T = map(time,45000,55000,1000,10000);
          osc_middle.SetT(T); // Set the period of work (each time higher, from T=1000 to T=10000)
          osc_right.SetT(T);
          osc_left.SetT(T);*/

       else { // Until it stops, then we can stop the program
        while (1);
      }

      //-- Refresh the oscillators
      osc_middle.refresh();
      osc_right.refresh();
      osc_left.refresh();
    }
