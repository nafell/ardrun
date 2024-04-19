# ardrun
arduino-cli QoL script for Debian environments.

Official Documentation:  https://arduino.github.io/arduino-cli/0.21/commands/arduino-cli/  
Referenced: https://tech.144lab.com/entry/arduino-cli  

## Setup
### Installation
```bash
mkdir ~/bin
```
```bash
curl -fsSL https://raw.githubusercontent.com/arduino/arduino-cli/master/install.sh | BINDIR=~/bin sh
```
```bash
export PATH=$HOME/bin:$PATH
```
```bash
arduino-cli version
```

### Initialization
```bash
arduino-cli config init
```
```bash
arduino-cli core update-index
```
install board compiler/tools for arduino uno
```bash
arduino-cli core install arduino:avr
```

### libs
#### Search
```bash
arduino-cli lib search --names U8x8
```
#### Install
1. grove oled (U8x8lib.h)
```bash
arduino-cli lib install U8g2
```
2. grove dht sensor (DHT.h)
```bash
arduino-cli lib install "Grove Temperature And Humidity Sensor"
```

## Usage
### Create new project
```bash
arduino-cli sketch new MyFirstSketch
```

### Search board
```bash
arduino-cli board list
```
result:
```
Port         Protocol Type              Board Name FQBN Core
/dev/ttyAMA0 serial   Serial Port       Unknown
/dev/ttyS0   serial   Serial Port       Unknown
/dev/ttyUSB0 serial   Serial Port (USB) Unknown <<< 正解
```
Usually the device Port will be named `ttyUSB0`, `ttyUSB1`, etc.

### Compile
```bash
arduino-cli compile -b arduino:avr:uno
```

### Upload/Write
```bash
arduino-cli upload -b arduino:avr:uno -p /dev/ttyUSB0
```


## One-command compile & upload bash script
```bash
curl https://raw.githubusercontent.com/nafell/ardrun/main/ardrun -o ~/bin/ardrun
```
execution permission
```bash
chmod 755 ~/bin/ardrun
```
Run on sketch working directory
```bash
ardrun
```
