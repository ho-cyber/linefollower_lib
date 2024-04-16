# LineFollower Arduino Library

This library simplifies the process of making line follower robots using Arduino. It provides methods to set up the necessary pins and control the motors based on line sensor readings.

## Installation

1. Download the LineFollower library folder.
2. Place the `LineFollower` folder into the `libraries` directory of your Arduino IDE:
    - **Windows:** `My Documents\Arduino\libraries\`
    - **macOS:** `Documents/Arduino/libraries/`
    - **Linux:** `~/Arduino/libraries/`
3. Restart the Arduino IDE.

## Usage

### Initialization

```cpp
#include <LineFollower.h>

// Create an instance of LineFollower
LineFollower myLineFollower(ENA_pin, ENB_pin, ls_pin, rs_pin, m1_pin1, m1_pin2, m2_pin1, m2_pin2);

#Setup
In your setup() function, call the setup() method of the LineFollower instance.

```cpp
void setup() {
  myLineFollower.setup();
}

```scss
### Following Line

In your `loop()` function, call the `followLine()` method of the LineFollower instance.

```cpp
void loop() {
  myLineFollower.followLine();
}

#Parameters
ENA_pin: PWM pin for motor driver ENA
ENB_pin: PWM pin for motor driver ENB
ls_pin: Line sensor pin for left sensor
rs_pin: Line sensor pin for right sensor
m1_pin1, m1_pin2: Pins for motor 1 control (e.g., IN1 and IN2)
m2_pin1, m2_pin2: Pins for motor 2 control (e.g., IN3 and IN4)
Methods
setup(): Initializes the pins and sets them as inputs/outputs.
followLine(): Controls the motors based on line sensor readings to follow the line.

```cpp
#include <LineFollower.h>

LineFollower myLineFollower(9, 10, 2, 3, 5, 6, 7, 8);

void setup() {
  myLineFollower.setup();
}

void loop() {
  myLineFollower.followLine();
}

