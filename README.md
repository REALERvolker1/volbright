This repository is archived. The current version of volbright is here in my [dotfiles](https://github.com/REALERvolker1/homescripts/blob/main/bin/volbright.sh)

# volbright
An event-driven shell script to show you your info ~

- backlight brightness

![image](https://user-images.githubusercontent.com/73304952/230544567-228d9095-db54-494e-a6d0-4782adf565e1.png)

- volume

![image](https://user-images.githubusercontent.com/73304952/230544468-7094f85f-161e-4c6d-8b29-fd6cd3902279.png)

- keyboard brightness

![image](https://user-images.githubusercontent.com/73304952/230544597-da85f71a-cd9a-4876-9073-c45ed2fec4b5.png)


# Usage
Dependencies:
- pipewire-pulseaudio (or pulseaudio)
- inotify-tools
- dunst
- a [nerd font](https://www.nerdfonts.com)

For the best experience, edit your dunstrc to add an override:
```ini
[brightness-watcher]
# appname: whatever $APPNAME is in the script
appname = "vlk-brightness-audio-watcher"
format = "%s"
icon_position = off
alignment = center
```
After this, edit `volbright.sh` to match your system configuration.
```bash
# poke around in /sys/class/backlight until you find something
BACKLIGHT_PATH="/sys/class/backlight/path/to/device"
# Your system may or may not have a nice and easy way to get the keyboard backlight state
KEYBOARD_PATH="/sys/class/leds/path/to/keyboard"

BRIGHTNESS_COLOR='#ffffff'
KEYBOARD_COLOR='#99c1f1'
VOLUME_COLOR='#8ff0a4'

#GOOD_COLOR='#57e389'
WARN_COLOR='#f8e45c'
URGENT_COLOR='#ff7800'
CRITICAL_COLOR='#ed333b'
```
To run the script, all you need to do is run `volbright.sh --help`

# Credits
This script was inspired by a [similar](https://gitlab.com/Nmoleo/i3-volume-brightness-indicator) script by u/NmoleoSoftware from [Reddit](https://www.reddit.com/r/i3wm/comments/125xvg2/i_made_a_volume_and_brightness_indicator_for_i3wm/)
