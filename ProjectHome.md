I reverse engineered the Winblows driver of the Logitech C110 USB keyboard so that we can change the color of the led lights in any shade between red and blue from Linux.

In the "Downloads" section is a proof of concept that I keep running all the time. It slowly, gradually makes the backlight color change from blue to red and back. If you give it one argument (0-255), the color will be set to that value (0 = red, 255 = blue).

This open source Linux driver is better than the original proprietary driver because it allows you to continuously change the backlight color in addition to setting just one, fixed color.

Enjoy !

# Using the program #
  * Download a pre-compiled version from the "Downloads" section (or compile your own, see below)
  * Make sure your keyboard is plugged in (duh!)
  * Start the color changing program:
```
chmod +x Logitech_G110_change_color # make the program executable
./Logitech_G110_change_color # run it
```
  * You can also set a single color like this:
```
./Logitech_G110_change_color 0 # red
./Logitech_G110_change_color 128 # purple
./Logitech_G110_change_color 255 # blue
```

# Compiling the code #
(these instructions are for Ubuntu)

  * You need a compiler:
```
sudo apt-get install build-essential
```
  * and subversion:
```
sudo apt-get install subversion
```
  * Install libusb-dev (this is a dependency):
```
sudo apt-get install libusb-dev
```
  * Check out the source code:
```
 svn checkout http://logitech-keyboard-change-color.googlecode.com/svn/trunk/ logitech-keyboard-change-color-read-only
```
  * Compile the project:
```
cd logitech-keyboard-change-color-read-only
make
```