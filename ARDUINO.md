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
