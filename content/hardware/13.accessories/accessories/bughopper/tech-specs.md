Here you will find the technical specifications for the Arduino® Bug Hopper.

**Please read: power supply and voltage domains.**

The Arduino Bughopper is powered **exclusively** through its USB-C® connector, which supplies +5 VDC from the host development machine. The onboard FT230XQ-R USB-to-UART bridge IC uses this +5 VDC input to generate a regulated +3.3 VDC rail internally, which powers the board's logic and is indicated by the onboard green LED.

The Bughopper operates across two distinct voltage domains:

- The host side operates at +3.3 VDC. All internal serial signals (TXD and RXD) between the FT230XQ IC and the onboard level translator run at this voltage.

- The target side operates at +1.8 VDC, the operating voltage supplied by the connected Arduino UNO Q board through the JCTL connector. The onboard level translator of the Bughopper automatically bridges these two domains, ensuring signal integrity. The onboard red LED lights up when +1.8 VDC is present, confirming that the UNO Q board is powered and connected.

**Important note: The Bughopper does not supply power to the UNO Q board and does not draw power from it**. Always ensure the UNO Q board is independently powered before connecting the Bughopper to avoid undefined behavior on the +1.8 VDC rail.