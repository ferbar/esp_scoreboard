# esp_scoreboard
esp8266 / micropython / PCA9685

setup micropython am esp8266:
https://docs.micropython.org/en/latest/esp8266/tutorial/repl.html


http://micropython.org/webrepl/#192.168.178.165:8266/

IDE: thonny
zypper install python3-tk python3-websockets

pip3 install thonny

Workflow:
scoreboard + main.py aus diesem Repo öffnen, am Device speichern. Bei Änderungen "Save copy..." im git repo, "normales" Save. Sollte sich Thonny aufregen dass das Device busy ist unten in die Shell klicken und CTRL + C. [STOP] ist nicht notwendig

## Settings:
https://randomnerdtutorials.com/getting-started-thonny-micropython-python-ide-esp32-esp8266/

## tutorial:
https://docs.micropython.org/en/latest/esp8266/tutorial/index.html

## PCA9685 lib
- geht nicht (mehr), muss händisch kopiert werden
-tools-> manage packages for micropython
- micropython-adafruit-pca9685 

https://github.com/adafruit/micropython-adafruit-pca9685/blob/master/pca9685.py
runterladen und ins lib verzeichnis speichern
Docu dazu: https://micropython-pca9685.readthedocs.io/en/latest/pca9685.html

# urls

i2cscan - welche i2c Devices sind angehängt?

http://192.168.178.165/i2cscan

scannt alle I2C Adressen (0 -> 127) und listet sie auf

platine 1+2 initen mit I2C Adresse 42 und 40

http://192.168.178.165/initleds?66&64
http://192.168.178.165/initleds?0x42&0x40

2 zeichen string senden, startpos 0

http://192.168.178.165/setleds?p=0&s=11

. setzen / löschen
http://192.168.178.165/setleds?p=0&s=.1_1

&b=brightness (0...4095)
&c=0x20 => über hex die bits setzen (umgekehrte reihenfolge: A=höchstes bit, 1=punkt)

&s &c &b können gemischt und wiederholt werden
