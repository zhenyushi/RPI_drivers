# RPI_drivers
Sample codes for driving different hardware with Raspberry Pi <br />
The name of the original package is commu

## Hardware
Raspberry Pi Zero Wireless<br />
- datasheet: https://cdn-learn.adafruit.com/downloads/pdf/introducing-the-raspberry-pi-zero.pdf

PCA9685 I2C 16 Channels PWM driver<br />
- datasheet: https://cdn-shop.adafruit.com/datasheets/PCA9685.pdf

MPU 9250 9 Axes Accelerometer<br />
- datasheet: https://www.invensense.com/wp-content/uploads/2015/02/PS-MPU-9250A-01-v1.1.pdf

TCA9548A 8 Channels I2C Multiplexer<br />
- datasheet: http://www.ti.com/lit/ds/symlink/tca9548a.pdf

28015 REV C PING))) Ultrasonic Distance Sensor<br />
- datasheet: http://users.ece.utexas.edu/~valvano/Datasheets/PingDocs.pdf

## Software
### Raspberry Pi
Raspbian Jessie Lite<br />
ROS packages:<br />
- rospy
- roscpp
- roslaunch
- sensor_msgs
- std_msgs
- visualization_msgs
- tf
### PC
putty: https://www.putty.org/ <br />
Winscp: https://winscp.net/eng/index.php <br />
Advanced IP Scanner: https://www.advanced-ip-scanner.com/ <br />
Win32DiskImager: https://sourceforge.net/projects/win32diskimager/ <br />

## Relvant Links
Raspberry Pi headless setup: https://hackernoon.com/raspberry-pi-headless-install-462ccabd75d0 <br />
I2C setup: https://learn.adafruit.com/adafruits-raspberry-pi-lesson-4-gpio-setup/configuring-i2c

## Relvant Issues
WIFI setup:<br />
- Add the following lines to `/etc/wpa_supplicant/wpa_supplicant.conf`:
~~~
network={
ssid="MySSID"
psk="MyPsk"
key_mgmt=WPA-PSK
}
~~~~
- Add the following lines to `/etc/network/interfaces`(for auto conntection, not default for Raspbian Stretch):
~~~
auto lo
iface lo inet loopback

iface eth0 inet manual

allow-hotplug wlan0
iface wlan0 inet manual
    wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf

allow-hotplug wlan1
iface wlan1 inet manual
    wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf
~~~~

Show all connected I2C devices:
~~~
$ sudo i2cdetect -y
~~~
Make the scripts executable:
~~~
$ chmod +x something.py
~~~

Show ip address:
~~~
$ ifconfig
~~~

Install smbus2:
~~~
$ sudo apt-get install -y python2-pip
$ sudo pip install smbus2
~~~

To add new ros packages, follow the section 4.2 in this link:<br />
http://wiki.ros.org/ROSberryPi/Installing%20ROS%20Kinetic%20on%20the%20Raspberry%20Pi

GPIO for Raspberry pi 3 and pi zero w:<br />
(Source page: http://www.raspberry-pi-geek.com/howto/GPIO-Pinout-Rasp-Pi-1-Model-B-Rasp-Pi-2-Model-B)<br />
![raspib-gpio_lightbox](https://user-images.githubusercontent.com/24307076/38147871-11d1443e-3422-11e8-8ede-98b4535786e0.png)

