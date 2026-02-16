#BSE SENSOR
The BSE input into the BSE Logic section of the BSPD has a maximum input range of up to 12V. A voltage input range between 527mV and 4.473V is considered to be the normal operating range (i.e. no hard breaking). Outside of these ranges the input is considered to be either nonfunctional for a voltage < 527mV or in a state of hard breaking for a voltage > 4.473V. The determination of the current braking is done by measuring the input voltage across an LM2903B dual comparator. If the input voltage falls outside the specified range, the car is determined to be hard braking and a signal is passed through the BSE logic.

#TRACTIVE SYSTEM LOGIC
The tractive system current is determined based on the current input voltage of the throttle pedal. With a current of a tractive system current of _____ around at ____kW supplied to the motors under the 403.2V tractive system voltage.

#BSPD LOGIC
Both the tractive system logic and the braking logic are passed through SN74AHC1G32DRLR OR gate to check whether the input signal is too low or too high from each logic block respectively. The logic of the two blocks are then checked with an SN74AHC08DR AND gate to determine if the vehicle is simultaneously undergoing acceleration and hard braking.

#RELAY
When both conditions are met, a signal is sent to an LTC6994 which only triggers after a calibrated 450ms delay. A G6CK-2114P-US-DC12 relay is then triggered and cuts off a signal to the shutdown circuit, disabling the car. The BSPD relay can be reset by power cycling the vehicle as a capacitor and leakage resistor is used to pulse the reset coil on shutdown.
