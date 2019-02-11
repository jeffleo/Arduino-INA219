# TI INA219 Current Sensor firmware for Arduino

Modified version of [Adafruit_INA219 library](https://github.com/adafruit/Adafruit_INA219) to use DSSCircuits I2C libary for bus-lockup timeout, preventing freezing from failed I2C reads that occurs from Wire library used in the adafruit implementation. Only verified to maintains Arduino devices compatability Uno (ATmega328) and Mega2560 (ATmega2560). ARM based Arduinos (Due) are not supported like before.

# Library Functional Changes: 
- no longer freezes/crashes Arduino when I2C bus blocked
- begin() no longer sets default calibration so desired calibration must be called, e.g.
~~~~
Adafruit_INA219 ina_;

void setup(){
  ina_.begin();
  
  void setCalibration_32V_2A(void);
//  void setCalibration_32V_1A(void);
//  void setCalibration_16V_400mA(void);
//  void setCalibration_16V_400mA_11bit(void);        // allows faster sampling rate than 400mA at 12bit
}
~~~~
-  ina_.scanBus() added to scan for your hardware on the I2C line and print out its address for debugging

# Credit
- the original [Adafruit_INA219 library](https://github.com/adafruit/Adafruit_INA219), contains examples
- dsscircuits Arduino I2C library as described in [dsscircuits article](http://dsscircuits.com/articles/86-articles/66-arduino-i2c-master-library)

For additional examples, refer to (DC motor current controller)[https://github.com/jeffleo/DC-Motor-Controller] implementation in Mot_Ctrl.h header only class.
