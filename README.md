# uinput-joystick-demo

A program that simulates a Linux joystick using the uinput API.

This demo program shows how to use the [uinput API](https://www.kernel.org/doc/html/v4.12/input/uinput.html) to create a joystick device instance (with buttons) and feed input data to that device.  The device will appear as /dev/input/js<N> and can be used by any application that accepts input from a joystick.  For testing purposes, the command line [jstest](https://linux.die.net/man/1/jstest) application is always a good option.

Thanks are owed to [Marek Klaus's blog article](https://blog.marekkraus.sk/c/linuxs-uinput-usage-tutorial-virtual-gamepad/) that got me pointed in the right directon.
