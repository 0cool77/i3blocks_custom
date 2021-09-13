# i3blocks_custom
This i3bocks configuration is my custom config.
As source for the configuration I took the following Github repositories:
- https://github.com/vivien/i3blocks
- https://github.com/vivien/i3blocks-contrib/tree/master/time


For the icons I use Font awesome:
https://fontawesome.com/v5/cheatsheet/free/solid

My configuration for i3Blocks looks like this:
```
# i3blocks configuration file
#
# The i3blocks man page describes the usage of the binary,
# and its website describes the configuration:
#
#     https://vivien.github.io/i3blocks


# Global properties
separator=true
separator_block_width=15
SCRIPT_DIR=/home/<USERNAME>/.config/i3blocks/scripts

# [documentation]
# full_text=Documentation
# website=https://vivien.github.io/i3blocks
# command=xdg-open "$website"
# color=#f12711
# 
# [greetings]
# color=#f5af19
# command=echo "Hello, $USER!l
# interval=once

[arch-update]
command=$SCRIPT_DIR/arch-update 
interval=3600
markup=pango
LABEL= 

[weather]
command=curl -Ss 'https://wttr.in?0&T&Q' | cut -c 16- | head -2 | xargs echo
interval=3600
color=#A4C2F4

# [batterybar]
# command=$SCRIPT_DIR/batterybar
# label=bat:
# interval=5
# markup=pango
# min_width=bat: ■■■■■
# Discharging colors low to high
# #C1=#FF0027
# #C2=#FF3B05
# #C3=#FFB923
# #C4=#FFD000
# #C5=#E4FF00
# #C6=#ADFF00
# #C7=#6DFF00
# #C8=#10BA00
# CHARGING_COLOR=#00AFE3
# FULL_COLOR=#FFFFFF
# AC_COLOR=#535353

[battery2]
command=$SCRIPT_DIR/battery2
markup=pango
interval=1

[wifi]
command=$SCRIPT_DIR/wifi
label=
INTERFACE=wlan0
interval=5

# Query my default IP address only on startup
[ip]
command=hostname -i | awk '{ print "IP: " $1 }'
interval=once
color=#91E78B

[public-ip]
command=wget -qO - icanhazip.com | awk  '{print "P-IP: " $1}'
interval=once

[disk]
command=$SCRIPT_DIR/disk
LABEL=HOME 
#DIR=/mnt/data
interval=30

[time]
command=date '+%Y-%m-%d %H:%M:%S'
interval=1
```
