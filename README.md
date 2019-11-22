/* RTClib-from-Adafruit

history:

// Original Code by JeeLabs http://news.jeelabs.org/code/
// Released to the public domain! Enjoy!
// Merged DS3231 functions from: github/coobro/RTClib  by  MrAlvin 2012-02-27
// and Alarm code for DS3231 heavily used/modified from Eric Ayars DS3231 library  by  Coobro
// Corrections for DS3231 by eriktheV-king on 2018-01-09 (lines 494 and 509)
   working code additions for issues #81 and #86 in RTClib.cpp as of 2018-01-09
   https://github.com/adafruit/RTClib/issues
   The corrected .cpp file adding the readSqwPinMode() function in the DS3231 part of the .cpp file as proposed in issue #81 bugged when I  tried to compile.
// Brought back read_i2c_register and write_i2c_register functions
// to keep compatibility with lostPower, readSqwPinMode, writeSqwPinMode functions
// due to previous heavy rewrite
// Mods by Vking on 2019-04-28:
//  added DS3231 functions RTC_DS3231:: setBBSQW getBBSQW setINTCN getINTCN setA1F 
//   to get and to set BBSQW pin to on to enable batterybacked SQW-INT function
//                     (is OFF on first powerup),
//   to get and to set INTCN pin to on to enable batterybacked INT function,
//                     (is ON on first powerup)
//   to clear the A1F flag in SQWINT (set it to false)

*/
