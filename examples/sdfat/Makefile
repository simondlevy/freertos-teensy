SKETCH = sdfat

FQBN = teensy:avr:teensy40

PORT = /dev/ttyACM0

LIBS = $(HOME)/Documents/Arduino/libraries

build:
	cp ../../src/FreeRTOSConfig_default.h ../../src/FreeRTOSConfig.h 
	arduino-cli compile  --libraries $(HOME)/Documents/Arduino/libraries \
		--fqbn $(FQBN) $(SKETCH).ino
	rm ../../src/FreeRTOSConfig.h 

flash:
	arduino-cli upload -p $(PORT) --fqbn $(FQBN) .

edit:
	vim $(SKETCH).ino

listen:
	miniterm.py $(PORT) 115200 --exit-char 3 # exit on CTRL-C

