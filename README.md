# ESP32-Weather-Forecaster

Using an ESP32 to read air pressure from either a BMP085/180
or BME280 enables the weather to be forecasted using a set of rules based on
air pressure at your location (adjusted from sea level with a simple offset)
and then by monitoring changes over time weather can be predicted with a good
level of certainty.

Two versions are provided one for a 1.3" OLED display and the SH1106 driver and one for the 0.96" OLED display and SSD1306 Driver.

The code works equally well on an ESP8266 provided the time source is adjusted.

Change the code to suit your sensor either a BMP085 (now obsolete) or BMP180 or the three parameter and highly accurate BME280.


