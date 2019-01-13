# No-Battery-CPS2
Run CPS2 'B' boards with original roms without a battery

Forked from: https://github.com/ArcadeHacker/ArcadeHacker_CPS2

The purpose of this is to install a Arduino in each CPS B board so that it will write the decryption key every time you boot the game. This will allow you to keep the original unaltered roms, but be able to remove the battery and not have to worry about it leaking and causing damage to the PCB.

This is intended to be used on a Arduino Nano due to the small form factor, but should work on other Arduino versions as well. You will need to be connected (soldered) to the CPS2 B board as specified in the original ArcadeHacker_CPS2 programming guide, but without the need of a LCD Shield:

# Boards with CN-9 except 93646B-5

+5V     - Arudino 5V

DATA    - Arduino # 2

SETUP1  - Arduino # 3

CLOCK   - Arduino # 11

SETUP2  - Arduino # 12

GND     - Arduino GND

NOTE: You will need to edit the .ino file to change the value of "const unsigned char Key[] PROGMEM = ..." to the decryption key of the game you will be installing this in.

# 93646B-3 & 93646B-4 boards:

A 75 - 100 ohm  resistor is needed on pin 11 (CLOCK)

CPS2 Board without CN9, CN2 interface pins

(Arduino 2)  DATA    ->  CN2 A32

(Arduino 11) CLOCK   ->  CN2 A31 (Resistor needed, 75-100 ohm)

(Arduino 3)  SETUP1  ->  CN2 A30

(Arduino 12) SETUP2  ->  CN2 A29


# 93646B-5 boards:

CN9 has no power on PIN 1, you can take it from CN8.
