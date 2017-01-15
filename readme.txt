The Arch Linux package of the Linux kernel and modules with several patches for
Microsoft Surface (Pro).

	- Make Type Cover mutitouch enabled.
	- Fix Wi-Fi freezing (from <https://bugzilla.kernel.org/show_bug.cgi?id=188351>).

There are two ways to enable both touch panel and pen:

	- Install xf86-input-libinput and xf86-input-wacom.  Add the following
	  configuration to xorg.conf (All "Option" settings are optional):

			Section "InputClass"
				Identifier "ntrig"
				MatchProduct "1B96:1B05 Pen"
				MatchDevicePath "/dev/input/event*"
				Driver "wacom"
				Option "Suppress" "0"
				Option "RawSample" "1"
				Option "Threshold" "1"
				Option "Button2" "3"
			EndSection

	- Install xf86-input-libinput and xf86-input-evdev.

Currently I use xf86-input-wacom.
