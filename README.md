Use this for stereo (and non-stereo?) cameras.

INSTALLATION
============
Get source from accam.rosinstall:
```
  cd ~/ws_dir/src
  wstool merge accam/accam.rosinstall
  wstool update
```
Setup udev rules for firewire

SIMPLE TEST
===========
- Mono usb camera:  roslaunch accam camera.launch camdir:=cam_usb0 stereo:=false
- Stereo usb camera: does not work
- Stereo firewire camera: not complete here.  See other git repo.


LAUNCH FILE OPTIONS
===================
- camdir:=
  - cam_usb0    - /dev/video0  (fatdragon built-in camera)
  - cam_usb12   - /dev/video1 and /dev/video2 as left/right usb camera pair
  - 1394stereo  - firewire camera via camera1394stereo
- stereo:=      - false to only do left (for mono cameras)
- view_left:=   - true/false to see raw video
- view_right:=  - true/false to see raw video
  
each camera (set via camdir argument) is in a directory of the same name under
config/
  

LAUNCH FILES
============
- camera.launch - launch camera and (optionally) left/right view
