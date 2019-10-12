# uinput-joystick-demo

A program that simulates a Linux joystick using the uinput API.

This demo program shows how to use the [uinput API](https://www.kernel.org/doc/html/v4.12/input/uinput.html) to create a joystick device instance (with buttons) and feed input data to that device.  The device will appear as /dev/input/js*N* and can be used by any application that accepts input from a joystick.  For testing purposes, the command line [jstest](https://linux.die.net/man/1/jstest) application is always a good option.

Thanks are owed to [Marek Klaus's blog article](https://blog.marekkraus.sk/c/linuxs-uinput-usage-tutorial-virtual-gamepad/) that got me pointed in the right direction.

The uinput-demo.c source file is for a command-line application that creates a joystick with three absolute analog channels (X, Y, Z) and four buttons (A B X Y).  There are source lines that are #if'ed out showing some additional buttons and absolute analog channels that are available.  For a complete list see [input-event-codes.h](https://github.com/torvalds/linux/blob/master/include/uapi/linux/input-event-codes.h).

After the joystick device is created, it is fed data indefinitely (until the uinput-demo app is killed). The X and Y analog channels are fed by "fast" triangle waves that are 90° out of phase.  The Z analog channel is a slow ramp.  The four buttons toggle on/off at four different frequencies (they appear as a 4-bit binary counter).

To run the uinput-demo app, you'll need write permission for /dev/uinput (which on Gentoo is usually only accessible to root).  Assuming you have no other joystick devices, the simulated joystick device will appear as /dev/input/js0.
