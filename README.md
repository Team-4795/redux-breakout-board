# rio-RGB_LED-buffer-board
a pcb that mounts to a RoboRIO and buffers the data stream for WS2812b and similar LED strips

The RoboRIO can generate a data stream for addressable "smart" LED
strips built from WS2812b and similar LEDs.  This data comes out on
one of the PWM ports, but is much faster than the typical "servo" PWM
data.  As such, it is more sensitive to signal integrity issues,
especially when splitting it to drive multiple LED strips with
identical data.

The tutorial and circuit board here is inspired by a discussion on the
Chief Delphi forums https://www.chiefdelphi.com/t/wrong-colors-from-ws2812-led-strips-driven-by-roborio/434199


The basic idea is that we use one WS2812b addressable LED as a
"buffer", to recieve the data stream from the RoboRIO, and retransmit
it downstream to one or more LED strips on the robot.

This has two benefits:
- The output from a WS2812b is more nearly optimized to drive further LEDs than the output of the Rio itself.
- We've always got a single LED on the RoboRIO for testing the RGB-output code, even when the other LED strips are disconnected.


References

https://docs.wpilib.org/en/stable/docs/software/hardware-apis/misc/addressable-leds.html

https://www.chiefdelphi.com/t/wrong-colors-from-ws2812-led-strips-driven-by-roborio/434199



