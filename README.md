# pyspacemouse-to-trackpoint

Ad-hoc Python code made just for fun to use 3D mouse (3dconnexion devices) as TrackPoint. Current state is just proof-of-concept.

## Credit

Huge Thanks to [Kuba Andrýsek](https://github.com/JakubAndrysek) for the code regarding reading 3D mouse data, which was taken from his project [pySpaceMouse](https://github.com/JakubAndrysek/pySpaceMouse).

## What does work:

* automated detection of 3D mouse device (by Kuba Andrýsek)
* move cursor around: Up, Down, Left, Right
* left and right clicks
* scroll up/down by using yaw (angle on the XY plane)
* zoom-in/zoom-out by using z-axis (emulating CTRL + '+'|'-')
	+ sensitivity can be changed by 'zoom\_sens' variable; greater the number = greater force required
* horizontal scroll (left/right) by pushing (negative z-axis) and then move on x-axis will corespond to movement
	+ sensitivity can be changed by 'hs\_sens' variable; greater the number = more movement per 1 scroll point is required

## What does NOT work:

* script is ad-hoc, no permanent system integration thus far
* sensitivity can only be changed by values from inside the script

## Run inside virtual environment

you should swich to 'root' and then:

```shell

# make sure you have these
apt install python3-dev
apt install python3-uinput
apt install python3-evdev
apt install python3-venv

# create and load virtual environment
python3 -m venv venv
source venv/bin/activate

# install dependencies inside virtual environment
pip install python-uinput
pip install easyhid
pip install evdev

# make sure kernel module is loaded
modprobe uinput

# now python script should work if you have the device connected
python3 pyspacemouse.py

```

## Nones

* 3D mouse may work without the need its light to be up.
* official drivers for 3D mouse may not be required.
