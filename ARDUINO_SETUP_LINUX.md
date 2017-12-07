# Arduino Setup Linux

## Install the Arduino IDE

### Download

<http://arduino.cc/en/main/software>

### Install

```shell
sudo apt-get remove arduino #remove older version if necessary
mkdir ~/ArduinoIde
mv ~/Downloads/arduino-X.Y.Z-linuxXX.tar.xz ~/ArduinoIde/
cd ~/ArduinoIde/
tar -xf arduino-X.Y.Z-linuxXX.tar.xz
cd arduino-X.Y.Z-linuxXX
echo "alias arduino='$(pwd)/arduino'" >> ~/.bashrc
source ~/.bashrc
```

You may need to add yourself to the group 'dialout' in order to have write
permissions on the USB port:

```shell
sudo usermod -aG dialout $USER
sudo reboot
```

### Run

```shell
arduino
```

### Setup

```shell
# after Arduino starts, go to File : Preferences
# verify Sketchbook location:
# /home/<yourusername>/Arduino/
```

## Install Teensyduino

### Download

<https://www.pjrc.com/teensy/td_download.html>

### Run Installer

```shell
mv ~/Downloads/TeensyduinoInstall.linux64 ~/ArduinoIde/
cd ~/ArduinoIde/
chmod 755 TeensyduinoInstall.linux64
./TeensyduinoInstall.linux64
#select folder ~/ArduinoIde/arduino-X.Y.Z/
#select 'None' additional libraries to install
```

### Setup udev Rules

#### Download

<https://www.pjrc.com/teensy/td_download.html>

Right-click 'Linux udev rules'

Save Link As...

#### Copy to udev

```shell
sudo cp ~/Downloads/49-teensy.rules /etc/udev/rules.d/
```
