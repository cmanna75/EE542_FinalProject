Trojan Care Cane and Bracelet!
EE542 Final Project
Running the Files:
- To run the files, please add the libxdot stable version to the active program.

Pinnouts:
- I2C and SCL and SDA pins are used for the accelerometer and pulse montior
- GPIO2 is used at the interuppt for the accelerometer
- GPIO3 is used as the "interuppt" for the MAX30102 (just makes sure we don't read data, while it is writing it)
- GPIO1 is used as the SOS button interuppt


Main.cpp:
- this is where the main loop is. In the main loop we constantly update heartrate as well as transfer the data to the Lora Gateway.
- interuppts are used to set flags for the sos button as well as the accerloemters fall detection

MPU6050:
- these files involve the basic functions used to communicate with the MPU6050
- The motion interrupt function is the key function for setting up the high pass filter threshold interuppt on the accelerometer

MAX30102:
- these files involve the basic functions used to communicate with the MAX30102
-  the maxim_max30102_read_fifo was the main function used, as it reads in 1 sample worth of raw red and ir values
- 200 samples are taken at a time which are they used for by the algorithms functions for cacluating bpm and 02 concentrate.


Algorithm:
- these files invovle all the funcitons invovled in determining the pulse through peak to peak detection as well as blood oxygen concentration through a lookup table.
