# waveshare-7.5inch-driver
[Waveshare 7.5inch](https://www.waveshare.com/7.5inch-e-paper.htm) E-Ink Python driver.

## Dependencies

* python3
* python3-pillow
* python3-rpi.gpio
* python3-spidev (v3.3, newer then raspbian)

## Usage


```
from PIL import Image, ImageDraw, ImageFilter

import epd7in5

# Create buffer
Himage = Image.new('1', (epd7in5.EPD_WIDTH, epd7in5.EPD_HEIGHT), 255)
draw = ImageDraw.Draw(Himage)
draw.text((20, 20), "hello world", fill=0)

# Get buffer
buf = epd.getbuffer(Himage)

# Create driver
epd = epd7in5.EPD()

# Init driver
epd.init()

# clear the screen
epd.clear()

# Display buffer
epd.display(buf)

# Set display in deep sleep
epd.sleep()
```

## License

This code is MIT licensed, code is inspired by/borrowed from [waveshare's driver](https://github.com/waveshare/e-Paper/tree/master/7.5inch_e-paper_code/RaspberryPi/python3).
