# Control System

This page includes files for battery control system. 

## Hardware Spec
* Raspberry Pi 3 model B
* 4 channel relay module
* Sensors
  - DHT 22
  - INA 219

## Software Spec
* Python 3.6
https://gist.github.com/dschep/24aa61672a2092246eaca2824400d37f
* library
  - Adafruit_DHT
  
  - INA219
  https://www.rototron.info/raspberry-pi-ina219-tutorial/
  - RPi_GPIO
  - requests
  - urllib

### Contents

* control_system.py

The file is executed on Raspberry Pi.

### 
The below code should be appened on `~/.profile`.
```sh
tmux new-session -d -s control
tmux send-keys -t control:0 "python3.6 ~/Battery-24-7/control_system.py" C-m
```

## Quick Guide for tmux
Install
```sh
sudo apt-get install tmux
```

`C-b` means `Ctrl`+`b`

On main session
```
tmux                                        create new session
tmux new-session -s "Session Name"          create new session with "Session Name"   
tmux attach -s "Session Name"               attach to "Session Name" session with new window
tmux ls                                     show the tmux list
```

Session Control
```
C-b (                                       previous session
C-b )                                       next session
C-b &                                       close and exit the current session(kill the current session)
C-b d                                       detach the session(exit the current session and return to the main session)
```