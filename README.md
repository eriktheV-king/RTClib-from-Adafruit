# RTClib-from-Adafruit
working code additions for issues #81 and #86 in RTClib.cpp as of 2018-01-09
https://github.com/adafruit/RTClib/issues

The corrected .cpp file adding the readSqwPinMode() function in the DS3231 part of the .cpp file as proposed in issue #81 bugged when I tried to compile.

I managed to get it working as follows:
-------------------------------------------------------------


Ds3231SqwPinMode RTC_DS3231::readSqwPinMode() {
int mode;

Wire.beginTransmission(DS3231_ADDRESS);
Wire._I2C_WRITE(DS3231_CONTROL);
Wire.endTransmission();

Wire.requestFrom((uint8_t)DS3231_ADDRESS, (uint8_t)1);
mode = Wire._I2C_READ();

//mode &= 0x93;//bug due to using ds1307 read mask
mode &= 0x1C;
if(mode == 0x04)
mode = DS3231_OFF;
return static_cast<Ds3231SqwPinMode>(mode); // instead of "return static_cast(mode);"
}
----------------------------------------------------

In the mean time, I also added the code for the .isrunning() function for DS3231 as proposed in issue # 86 and everything is now working perfectly well !
