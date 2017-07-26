# SamyKamTools

SamyKam - A set of pentesting tools to test Mag-Stripe readers and tokenization processes

Code and hardware integration by [Salvador Mendoza] (https://salmg.net)

PCB design and advisory by Team work with [electronicats] (https://twitter.com/electronicats)

Named the tool in honor of Samy Kamkar (http://samy.pl)
For his hard work and community support

##Features
It is a MagSpoof but specfically designed for Raspberry Pi:
- OLED for prepared attacks
- Rotary endoder for navigation menu

Support:
Mini-shell for basic commands implementing Bluetooth and Webserver independently
- change parameters without ssh
- change wifi configuration [ssid/pass] *
- send any shell command using Bluetooth

##Installation 

###Recommendations

Speeding Up the Display
For the best performance, especially if you are doing fast animations, you'll want to tweak the I2C core to run at 1MHz. By default it may be 100KHz or 400KHz

To do this edit the config with sudo nano /boot/config.txt
and add to the end of the file
dtparam=i2c_baudrate=1000000

More details: https://learn.adafruit.com/adafruit-pioled-128x32-mini-oled-for-raspberry-pi/usage

###Manual

```
apt-get update 
apt-get install python-dev python-setuptools swig python-bluez gcc-avr binutils-avr avr-libc

# gdata-2
curl -L https://pypi.python.org/packages/a8/70/bd554151443fe9e89d9a934a7891aaffc63b9cb5c7d608972919a002c03c/gdata-2.0.18.tar.gz#md5=13b6e6dd8f9e3e9a8e005e05a8329408 | tar xzf -
cd gdata-2.0.18
python setup.py install

# WiringPi
git clone git://git.drogon.net/wiringPi
cd wiringPi
./build


# WiringPi-Python
git clone --recursive https://github.com/ElectronicsCats/WiringPi-Python
cd WiringPi-Python
./build.sh
python setup.py install


# SPIDEV
git clone https://github.com/doceme/py-spidev
cd py-spidev
python setup.py install


# Adafruit_SSD1306
git clone https://github.com/adafruit/Adafruit_Python_SSD1306
cd Adafruit_Python_SSD1306
sudo python setup.py install

# py-gaugette
git clone https://github.com/guyc/py-gaugette
cd py-gaugette
sudo python setup.py install

#SamyKamTools
git clone https://github.com/ElectronicsCats/SamyKamTools
cd SamyKamTools
sudo python SamyKam.py
```

###Automatic Experimental

```
curl https://raw.githubusercontent.com/ElectronicsCats/SamyKamTools/master/install.sh | sudo sh
```

##License
