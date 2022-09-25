# Elegoo Neptune 3 extended

https://www.youtube.com/c/Crydteam

This is a extended Neptune 3 Klipper / Mainsail Config

This Files are only compatible together!


### Link for tutorial: published soon

#### Discord: https://discord.gg/kBdeP3ZtCY


#1 Install
 - Flash the mainsailOS Image to the raspberry (i use the raspberry pi imager)
 - Make the bin with the "make config"
 - Flash the printer

#2 Settings
- download printer.cfg and macros.cfg and upload it to the raspberry
- Change the SuperSlicer / Cura Start and End GCode

#3 Calibration
- Calibrate rotation distance (E-Steps)
- Calibrate PID 
- Calibrate Pressure Advance

#4 Input Shaping 

https://www.klipper3d.org/Measuring_Resonances.html

Shortlist Commands:
```
~/klippy-env/bin/pip install -v numpy
```
```
sudo apt update
```
```
sudo apt install python3-numpy python3-matplotlib
```
```
sudo reboot
```
```
cd ~/klipper/
```
```
sudo cp "./scripts/klipper-mcu-start.sh" /etc/init.d/klipper_mcu
```
```
sudo update-rc.d klipper_mcu defaults
```
```
sudo raspi-config            #enable SPI in interfacing options
```
```
sudo reboot
```
```
cd ~/klipper/
```
```
make menuconfig              #Microcontroller: Linux process
```
```
sudo service klipper stop
```
```
make flash
```
```
sudo service klipper start
```
```
sudo usermod -a -G tty pi
```
```
ACCELEROMETER_QUERY          #Testing the Sensor if there is a Invalid adxl then check the wireing or the offical klipper site
```
```
TEST_RESONANCES AXIS=X
```
```
TEST_RESONANCES AXIS=Y
```

To create the graph:

```
~/klipper/scripts/calibrate_shaper.py /tmp/resonances_x_*.csv -o /tmp/shaper_calibrate_x.png
```
```
~/klipper/scripts/calibrate_shaper.py /tmp/resonances_y_*.csv -o /tmp/shaper_calibrate_y.png
```

Have fun and join our discord!
