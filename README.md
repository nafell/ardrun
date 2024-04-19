https://tech.144lab.com/entry/arduino-cli
https://arduino.github.io/arduino-cli/0.21/commands/arduino-cli/

## install
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

## initialization
```bash
arduino-cli config init
```
```bash
arduino-cli core update-index
```
install board compiler/tools
```bash
arduino-cli core install arduino:avr
```

## libs
### search
```bash
arduino-cli lib search --names U8x8
```

1. grove oled (U8x8lib.h)
```bash
arduino-cli lib install U8g2
```
2. grove dht sensor (DHT.h)
```bash
arduino-cli lib install "Grove Temperature And Humidity Sensor"
```

## search board
```bash
arduino-cli board list
```
Port         Protocol Type              Board Name FQBN Core
/dev/ttyAMA0 serial   Serial Port       Unknown
/dev/ttyS0   serial   Serial Port       Unknown
/dev/ttyUSB0 serial   Serial Port (USB) Unknown <<< 正解


## compile
```bash
arduino-cli compile -b arduino:avr:uno
```

## write
```bash
arduino-cli upload -b arduino:avr:uno -p /dev/ttyUSB0
```


# 1 command compile & run bash script
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