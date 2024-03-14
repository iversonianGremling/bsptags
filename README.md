# BSPTAGS
![bsptags_logo](https://github.com/Vdevelasco/bsptags/assets/24989959/6e82f6fe-b17d-4c6a-accf-9e6750390408)





### Video

https://github.com/Vdevelasco/bsptags/assets/24989959/68cdf6f6-7769-4b5b-b78b-24f62f428757

### BSPTAGS tries to imitate one of dwm's key features, combining tags (or workspaces in this case). 

Its intended usage is mapping bsptoggletag 1,2,3 ...etc to a keyboard shortcut i.e. super+alt+1, super+alt+2...etc. When pressed all the windows in workspace 1 or 2 respectively will go to the workspace you are currently working in. If the same keyboard shortcut is hit again they'll return to its original workspace.


## Limitations
This script relies purely on bspc native "moving across workspaces" command so if you fuse a workspace with a lot of windows the layout might get messed up

## Usage
### Bsptags
 - bsptags <workspace_number>: will move windows from the specified workspace to the currently focused workspace
 - bsptabs -b <workspace_number>: if the windows have been moved from the specified <workspace_number> it'll return them to their original workspace
 - (experimental) bsptabs -m <workspace_1> <workspace_2>: Will move windows from workspace 1 to workspace 2, should work well in conjunction with bsptabs -b <workspace_number>
 - bsptabs -r: removes the tmp file created for the script to work (useful in case some error happens)
 - bsptabs -h: displays a help menu

### Bsptoggletag
  - bsptoggletag <workspace_number>: if two workspaces are not "merged" it'll try to merge them using bsptabs, if they are already merged it'll "unmerge" them

If you are using it as a command in sxhkd you have to redirect its output to /dev/null like this:
``super + alt + 3

  $HOME/.scripts/bsptags/bsptoggletag 3 >> /dev/null
``


## Installation
Just run 

``git clone https://github.com/Vdevelasco/bsptags/ ~/.scripts/``

By default bsptoggletag looks for ~/.scripts/bsptags/bsptags, if you want to use another location change the variable "bsptags_location" inside bsptoggletag and that should be it.

If you want to use the commands directy you should add this to your .bashrc or .zshrc:

``export PATH="$HOME/.scripts/bsptags/:$PATH"``
