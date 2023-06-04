# 723Assignment2
With a combination of esterel and C functions a system that emulates 
a cruise control system is developed for the University of Auckland's Compsys 723 Assignment 2

## Inputs
### Pure
    Off -> turns the cruise controller off
    On -> turns the cruise controller on
    Set -> sets the speed for the cruise controller to match
    Quick Accel -> increments the set speed by 2.5
    Quick Decel -> decrements the set speed by 2.5

### Floats
    Accel -> the user end acceleration
    Brake -> the user end brakes
    Speed -> the speed of the car

### Outputs
    CruiseControlSpeed -> The speed the cruise controller will maintain
    Accel -> the acceleration seen by the car
    State -> Indicates which state the cruise controller is operating in
   

## Operating description
   

    1) The system starts on state 1(OFF) after the first tick
    2) When the system is first turned on from state off the cruise speed is set to speed, and thereafter changed with 
        set, quickAccel, quickDecel
    3) From the On state the system will move into disable when Speed is <30, or >150, or when the accel parameter is greater than 
        pedMin representing the accelerator being actively pressed.
        and will return from disable to On when the parameters returned.
    4 From On or Disable, if brakes are greater than pedMin, the state moves into standby mode until reset is pressed,
        then depending on the parameters will return to either On, or Disable.

