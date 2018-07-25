# INA219 Current Sensor Library

Modified from Adafruit_INA219 library to use DSSCircuits I2C libary for bus-lockup timeout, 
preventing freezing from failed I2C reads that occurs from Wire library. Exposes function to 
set I2C address. begin() no longer sets default calibration so desired calibration must be called

Refer to http://dsscircuits.com/articles/86-articles/66-arduino-i2c-master-library for 
full coverage of the I2C library for Arduino.