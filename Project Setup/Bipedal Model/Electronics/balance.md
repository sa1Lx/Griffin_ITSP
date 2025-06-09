This file emphasises the concept of balancing the robot and factors concerning it.

# Factors 

## Robots Size Selection

  For stability, Centre Of Mass (COM) is preferred to be as low as possible. Length selection is yet to be done.


## Degrees of Freedom (D.O.F)

  Human leg has Six Degrees of freedom (Hip 3 D.O.F, Knee 1 D.O.F, Ankle 2 D.O.F), but implementing all the Six D.O.F is difficult due to increase in cost of the project and complexity of controlling of the actuators.   
  Therefore 3 D.O.F per leg has been used. With these six degrees of freedom (both legs) the robot is capable of walking.
  I have used this reference: [Design, Modeling and Analysis of Bipedal Walking Robot by Using Fuzzy Logic Controller](https://www.ijert.org/design-modeling-and-analysis-of-bipedal-walking-robot-by-using-fuzzy-logic-controller-2#:~:text=hip%2C%20knee%20and%20ankle%20joints%20which%20are%20driven)

# Model 1: Elastic Ankles

## Electrical Connection

  1. Power Distribution

    11.1V Battery → Step-Down Converter (XL4016E1) → 5V Rail

    Use 14 AWG wire for main power lines, thinner wires for signal lines.

  2. Servos

    Connect all servo power (VCC) and ground (GND) to the 5V rail from the step-down converter.

    Each servo’s signal line connects to a dedicated PWM-capable pin on the Arduino Uno.

  3. Arduino Uno

    Powered by the 5V rail or via its VIN pin (if using a regulator).

    Receives signals from sensors (e.g., IMU) and outputs PWM to servos.

  4. IMU Sensor 

    Connect via I2C (SDA/SCL) or SPI to the Arduino for balance feedback.

## Control System

  1. Sensor Feedback

    Use an IMU (gyroscope + accelerometer) for tilt and acceleration sensing.

    Arduino reads IMU data to determine robot orientation.

  2. Balance Control

    Implement a simple PID controller in Arduino:

      a. Use IMU data to correct ankle roll servo for side-to-side balance.

      b. Adjust hip and knee servos for step movement and to keep the center of mass over the support foot.

  3. Walking Gait

    Pre-program a walking sequence:

      -> Shift weight to one leg (ankle roll)

      -> Swing the other leg forward (hip/knee pitch)

      -> Place foot down, shift weight, repeat

  4. Synchronization

    Ensure servo movements are coordinated to avoid tipping.

    Use delays or timed sequences in Arduino code for smooth transitions.

# Model 2: A Modification with Inverted Pendulum
Reference: [Development of a Reduced-Degree-of-Freedom (DOF) Bipedal Robot with Elastic Ankles](https://www.mdpi.com/2218-6581/13/12/172)

Yet to analyse for detailed electrical connections and control system, can refer to the article above for the gist of it.
