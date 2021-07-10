# Si 7021 Tempature & Humidity Sensor Raspberry Pi Tutorial

Tutorial for https://www.adafruit.com/product/3251 

## 1. Connect to GPIO Pins

![temperature___humidity_Si7021_RasPi_I2C_breadboard_bb](https://user-images.githubusercontent.com/75696759/125170419-fb1b5980-e17c-11eb-9ef7-996ef2733ed8.jpeg)

## 2. Install Si 7021 Library

`sudo pip3 install adafruit-circuitpython-si7021`

## 3. Enable i2c

`sudo raspi-config`

Select option 3 (Interface Options)

Select option 5 (I2C)

Select 'Yes'

Press 'Finish'

## 4. Test out demo code 

### Initializes the sensor, gets and prints readings every two seconds.

```python
import time
import board
import adafruit_si7021

# Create library object using our Bus I2C port
sensor = adafruit_si7021.SI7021(board.I2C())

while True:
    print("\nTemperature: %0.1f C" % sensor.temperature)
    print("Humidity: %0.1f %%" % sensor.relative_humidity)
    time.sleep(2)
```
