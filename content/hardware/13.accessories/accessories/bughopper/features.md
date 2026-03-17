<FeatureDescription>
The Arduino Bughopper is a compact USB-to-UART debug accessory built around the FT230XQ USB-to-UART bridge IC. It connects to the Arduino UNO Q board through its onboard JCTL connector, providing a dedicated serial debug channel without occupying the board's main USB port. Onboard ESD protection, automatic voltage level translation and status LEDs make it a reliable tool for remote debugging, firmware logging and continuous UART monitoring.
</FeatureDescription>

<FeatureList>

<Feature title="FT230XQ-R USB-to-UART Bridge" image="communication">
The FT230XQ IC converts USB traffic from your development machine into a standard UART serial link (TXD/RXD), enabling real-time debug logging and serial communication with the UNO Q at baud rates from 300 bps up to 3 Mbps.
<FeatureWrapper>
  <FeatureLink title="Documentation" url="/tutorials/bug-hopper/user-manual/#usb-to-uart-bridge"/>
</FeatureWrapper>
</Feature>

<Feature title="Automatic Voltage Level Translation" image="mcu">
An onboard bidirectional level translator automatically bridges the +3.3 VDC Bughopper logic domain and the UNO Q's MPU +1.8 VDC voltage domain, ensuring reliable signal integrity regardless of the target operating voltage.
<FeatureWrapper>
  <FeatureLink title="Documentation" url="/tutorials/bug-hopper/user-manual/#voltage-level-translation"/>
</FeatureWrapper>
</Feature>

<Feature title="ESD-Protected USB Lines" image="usb">
Dedicated ESD protection diodes protect the USB data lines against electrostatic discharge, safeguarding both the Bughopper and the connected UNO Q from damage during insertion and normal use.
</Feature>

<Feature title="Dual Output Connectors" image="communication">
The board provides two physical connection options for the JCTL interface: a female 2.54 mm 2×5 header for direct cable attachment and a male 1.27 mm 2×5 header for compact ribbon cable setups, offering flexible integration into any workspace or enclosure.
<FeatureWrapper>
  <FeatureLink title="Documentation" url="/tutorials/bug-hopper/user-manual/#connectors"/>
</FeatureWrapper>
</Feature>

<Feature title="USB-C® Connectivity" image="usb">
A USB-C connector provides a modern, reversible connection to the host development machine, supplying the +5 VDC required to power the Bughopper and its internal +3.3 VDC logic.
</Feature>

<Feature title="Four Status LEDs" image="power">
Four onboard LEDs provide at-a-glance visibility of the system state: a green LED indicates +3.3 VDC power, a red LED confirms +1.8 VDC from the UNO Q MPU is present, and two yellow LEDs indicate serial activity on the TXD and RXD lines respectively.
<FeatureWrapper>
  <FeatureLink title="Documentation" url="/tutorials/bug-hopper/user-manual/#status-leds"/>
</FeatureWrapper>
</Feature>

<Feature title="Auxiliary GPIO Lines" image="mcu">
Four auxiliary GPIO lines are available on the output connectors, allowing the FT230XQ IC to send control signals to the UNO Q alongside the main serial link.
<FeatureWrapper>
  <FeatureLink title="Documentation" url="/tutorials/bug-hopper/user-manual/#cbus-gpio"/>
</FeatureWrapper>
</Feature>

</FeatureList>