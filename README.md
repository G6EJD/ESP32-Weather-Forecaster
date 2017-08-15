# ESP32-Weather-Forecaster

Using an ESP32 to read air pressure from either a BMP085/180
or BME280 enables the weather to be forecasted using a set of rules based on
air pressure at your location (adjusted from sea level with a simple offset)
and then by monitoring changes over time weather can be predicted with a good
level of certainty.

Two versions are provided one for a 1.3" OLED display and the SH1106 driver and one for the 0.96" OLED display and SSD1306 Driver.

The code works equally well on an ESP8266 provided the time source is adjusted.

Change the code to suit your sensor either a BMP085 (now obsolete) or BMP180 or the three parameter and highly accurate BME280.

NOTE:
The Adafruit_BMP085 or Adafruit_BME280 libraries won't compile when using the ESP32 board, however you can either use the versions I've uploaded or edit the follwing lines to comment out the wire.begin() statements, then they work OK, enabling you to define with Wire.begin(SDA,SCL) the pins to be used on the ESP32 device.

Adafruit_BMP085 library, edit the file Adafruit_BMP085.CPP and comment out the wire.begin statement:
boolean Adafruit_BMP085::begin(uint8_t mode) {
  if (mode > BMP085_ULTRAHIGHRES) 
    mode = BMP085_ULTRAHIGHRES;
  oversampling = mode;
　//Wire.begin(); //***************** Comment out

Adafruit_BME280 library, edit the file Adafruit_BME280.CPP and comment out the wire.begin statement:
bool Adafruit_BME280::begin(uint8_t           addr)
{
    _i2caddr = addr;
　  // init I2C or SPI sensor interface
    if (_cs == -1) {
        // I2C
        //Wire.begin(); //***************** Comment out



