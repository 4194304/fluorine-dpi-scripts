# Fluorine DPI Scripts
The main script, setdpi.sh, can be used in any environment.

When run, it will output a file named "dpi.sh" in the ~/.fluorine/ directory.

If used in a Fluorine environment, it should start and apply when it starts. However, if you're in an environment that is NOT based off of Fluorine, follow the instructions below.

## Setup

### Section 1. Packages and installation
This tool requires that you have the following packages:
`bash` (declare, echo, rm, chmod)
`xorg-xrdb` (xrdb-override)

Once the required packages are installed, the script can be downloaded from the repository using a variety of methods, including `git`.

### Section 2. Finding the folder
If using git, simply change directories into the folder that should be named `fluorine-dpi-scripts`.

Now the script is downloaded and ready to use.

Open a terminal and `cd` into the directory that contains the script.

### Section 3. Running it
Once you have successfully found the script using the terminal, before executing, be aware of the two vital arguments.

DPI scale factor is passed as a percentage.

__Argument 1: Xresources scale__
This is the scale factor used in Xresources, which will give programs the instruction to scale.

__Argument 2. GTK scale__
This is the scale factor used for all GTK applications.

__What about Qt?__
Qt by default copies the DPI scale from other sources, so Qt can be left out.

__Executing it__
To execute it, first run `chmod +x setdpi.sh`. This will allow execute permission which will in turn make the script work.

Finally, to execute it, run `./setdpi.sh` with the two arguments mentioned above. It should return no output (if the `.fluorine` folder is in your home directory beforehand it will return an mkdir warning), and in your home directory you should find a folder named `.fluorine`.

### Section 4. Post-setup
After executing the script, in the `.fluorine` folder, there should be a script named `dpi.sh`. The script can be moved anywhere or named anything, however, regenerating it will return another .

In environments such as Openbox, there should be an autostart file. Otherwise, you can add it to XDG autostart or your .xinitrc file which can be found in your home directory (if using startx). Use the following template below if that is done:
`exec ~/.fluorine/dpi.sh`

## Finishing up
Once the installation, setup, and execution is done, restart the X server to verify that everything is working correctly. If not, reread the direction and try again.
