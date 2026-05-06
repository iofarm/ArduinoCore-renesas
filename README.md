## Arduino Renesas fsp Boards with modified LwIpWrapper

A fork of the Arduino Renesas core with a modified LwIpWrapper library. The `lwipClient::write()` method is patched to correctly report the number of bytes written, and an `lwipClient::availableForWrite()` method is implemented to report the space available in the buffer instead of 0.

Correct linker flags are only configured for the Portenta C33.

### Installation

1. Find the path of your Arduino sketchbook folder in the Arduino IDE under
   `Settings` > `Sketchbook location`. Within this folder, create a new
   folder named `hardware` if it does not already exist.

2. Install the Arduino Core API: Under the `hardware` folder from step 1,
   create a new folder named `arduino`, if it does not already exist.
   Navigate to this folder in a terminal and clone the Arduino Core API
   there:

```
git clone https://github.com/arduino/ArduinoCore-API.git
```

 3. Install the modified Arduino Renesas core: Under the `hardware` folder
   from step 1, create a new folder named `thesoftlaboratory`. Navigate to
   this folder in a terminal and clone this repository there:

```
git clone --recurse-submodules -j8 https://github.com/iofarm/ArduinoCore-renesas.git renesas_portenta
```

   Note that the `--recurse-submodules` option is required so that the
   dependencies are also cloned.

 4. When building your sketch, make sure to use the modified Renesas core
    instead of the default; in the Arduino IDE, this will be the core with
    "(in Sketchbook)" at the end of the name.
