# Arduino

# Arduino-cli installation
[arduino-cli](https://ericslenk.com/posts/getting-started-with-the-nodemcu-esp8266-and-arduino-cli)

Install arduino-cli tar package
```bash
wget -qO arduino-cli.tar.gz https://downloads.arduino.cc/arduino-cli/arduino-cli_latest_Linux_64bit.tar.gz
```

Extract tar package to executable command
```bash
sudo tar xf arduino-cli.tar.gz -C /usr/local/bin arduino-cli
```

Initialize arduino-cli
```bash
arduino-cli config init
```

Add the package for your specific arduino board
```yaml
# /home/lucidmachine/.arduino15/arduino-cli.yaml
board_manager:
  additional_urls:
    - http://arduino.esp8266.com/stable/package_esp8266com_index.json
```

Update arduino-cli packages
```bash
arduino-cli core update-index
```

Install the board for your arduino
```bash
arduino-cli core install esp8266:esp8266
```

```bash
arduino-cli board listall | grep -i 'nodemcu'
```

## Install the necessary libraries
```bash
arduino-cli lib install EspMQTTClient
```

```bash
arduino-cli lib install Servo
```

```bash
arduino-cli lib install VL53L0X
```

```bash
arduino-cli lib install ArduinoJson
```

```bash
arduino-cli lib install NTPClient
```

## Compile and Upload
Compile sketch to be uploaded to your specific board
```bash
arduino-cli compile --fqbn esp8266:esp8266:nodemcuv2 <sketch>
```

Upload the sketch to your specific board
```bash
arduino-cli upload --port /dev/ttyUSB0 --fqbn esp8266:esp8266:nodemcuv2 <sketch>
```

## Windows specific commands

```bat
REM arduino-start.bat
arduino-cli compile --fqbn esp8266:esp8266:nodemcuv2 arduino
arduino-cli upload --port COM3 --fqbn esp8266:esp8266:nodemcuv2 arduino
python C:\Users\22hamfri\arduino-monitor.py
```

```bash
pip install pyserial
```

```python
# arduino-monitor.py
import serial

port = serial.Serial("COM3", 9600)

while True:
    if port.in_waiting > 0:
        line = port.read(port.in_waiting).decode("utf-8", errors="ignore")
        print(line, end="")
```

### Old School
```bash
mode COM3: baud=9600 parity=n data=8 stop=1
```

```bat
REM arduino-monitor.bat
@echo off
:loop
type COM3
goto loop
```
