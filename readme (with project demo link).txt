Name: Harsh Rajoria
Student #: 43119247

Project demo link (Youtube): https://www.youtube.com/watch?v=frCqy6txH70

Construction:
I used the AVR Microcontroller System (Atmega) to build the metal detector. I built a colpitts oscillator using 
a 1 mH whose inductance would change upon proximity with a metal (coin). The oscillator reflects this 
as a change in frequency. Essentially, I compared this frequency with a reference frequency (when no coin 
is present) to detect a coin. To build the oscillator, I used a 330 ohm resistor, a 10nF and 100 nF capacitor
and two mosfets to build a not gate. The output of this not gate was fed into pin 15 of the microcontroller.
To integrate the speaker into the circuit, I drove it through a P-channel mosfet connected to a switch to 
make it louder and then connected the gate of the mosfet to pin 14 of the atmega microcontroller. 

Software:
I utilised the 'Period.c' Makefile example that uses timer 1 to measure the frequency from the colpitts
oscillator. I determined that the frequency from the oscillator hovers around 52350 Hz with some fluctuations
so to account for those fluctuations my threshold for frequency detection was 52400 Hz beyond which the speaker 
would sound - an if statement on this condition detected the coin. Within this if condition, I sounded the
speaker by creating a PWM signal for the speaker by repeatedly turning on and off the speaker pin every 1 millisecond.
With the atmega, I used the DDRB commands to configure certain pins to be inpout or output and set the states of these
pins using the PORTB command - these were use repeatedly to enable my bonus features and to control the speaker.

Operation of the metal detector:

Once a coin is brought to within 1 cm of the inductor, the speaker starts beeping and a red LED comes on.  
The speaker can be permanantly disabled using a mechanical switch. Turning the knob of a potentiometer can make 
the speaker beep slower/faster. 

Extra features:

- A potentiometer knob controls the speed of the beeps of the speaker - the knob can be turned clockwise or anticlockwise 
with a screwdriver to make it beep faster or slower. To do this, the potentiometer output is fed into the ADC channel 0 
at all times where analog input is read and a voltage is displayed on Putty. This voltage reading is fed into the speaker 
operation - the higher the reading,the faster the speaker beeps.I configured pin 23 before doing the necessary ADC conversion 
and reading the channel. The digital output was used to control the PWM signal for the speaker to give the user 
customizability. This is done to enhance customizability as the user can control the speaker sound by turning just a knob.

- A red LED lights up when a metal is detected to give viusal feedback as well.

- The speaker is driven through a mosfet where a mechanical switch controls the signal to the gate of the mosfet 
so the user can permanantly turn off the speaker if they only prefer the LED to light up and not the speaker to buzz.

- Visual aid: The putty screen indicates whether a coin is detected or not and continually displays the digital reading 
from the ADC channel so the user can keep track of how fast the speaker is currently beeping.

References:

https://www.elprocus.com/cmos-working-principle-and-applications/




