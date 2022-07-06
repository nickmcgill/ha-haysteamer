# ha-haysteamer
Temperature monitor, switching off a steamer at a set temperature using ESPHome, a smart switch and HomeAssistant.

This uses a NodeMCU ESP8266, a DS18B20 (waterproof version), a smart socket and a 4k7 resistor.

![IMG_20220123_144526](https://user-images.githubusercontent.com/3117755/150775614-23b8a527-0ba9-44c2-a031-a43d625c66fd.png)


The wiring needed is well documented, so not repeated here.

![IMG_20220123_144532](https://user-images.githubusercontent.com/3117755/150775699-7420a2c5-d90e-471a-9efa-540615e5b08b.png)


(The prototype board was from https://www.amazon.co.uk/dp/B081QYPHHP and the tasmota smart socket from https://www.mylocalbytes.com/products/smart-plug-pm-uk )


Programming the NodeMCU was done using the ESPHome addon within HomeAssistant.

Getting the address of the sensor is documented here: https://esphome.io/components/sensor/dallas.html?highlight=dallas
It's noted in the yaml file where to initially comment the lines in order to get the address of the DS18B20

The tasmota smart socket (or any other smart socket) needs to be accessible by HomeAssistant.
The ha-automation was generated from the ha front end - when temp>80, switch off smart switch, call service to notify a phone app.

Now added pressure sensors to monitor water levels in the steamer and stop it boiling dry.
Pressure sensors from https://www.amazon.co.uk/gp/product/B07TWLP3X8 (other suppliers are available).

Data line from HX711 linked to D0, clock to D1, used 5V from the Vin pin, and adjacent ground pin.


