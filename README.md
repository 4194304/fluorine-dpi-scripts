# Fluorine DPI Scripts
Here are a few scripts I have made for the Fluorine desktop environment (and other environments too), that help you set up a hiDPI friendly experience on X11.

SetDPI helps you scale X11 and GTK, while OpenScale lets you scale any openbox theme, both with complete automation and ease of use.

## SetDPI

### Preparation
First, install the `xorg-xrdb` package.

From there, you can download it in whatever way best suits you.

After that, find the script, and allow execution permission by running `chmod +x setdpi.sh`.

### Execution
Once the script is ready, open a terminal.

Here are the applicable arguments used for this script:

__Argument 1: Xresources__
This will be the DPI percentage used in the Xresources file to scale X11, Openbox, and other window managers.

__Argument 2: GTK__
Using xrdb-override, you can set a scale factor for GTK. As was the last, this is controlled by a percentage value as well.

Finally, execute the script by running `./setdpi.sh`. If Fluorine is already installed, you should see an mkdir warning, which is fine to ignore. If performing this without the Fluorine desktop environment, no output should be seen.

After execution, if you restart any apps open before execution of the script, the scale will apply.

### Post-execution
After executing the script, it leaves a script named `dpi.sh` to set the GTK scale in the `.fluorine` directory which can be found in your home folder. This script can be run with your window manager's native autostart functionality, XDG autostart, or with the xinitrc file.

## OpenScale
OpenScale is a utility to scale Openbox themes.

OpenScale requires the `imagemagick` package to even work, so make sure that it's installed before use.

Make sure that the file has execution permission, and if not, run `chmod +x openscale.sh` to grant permission.

### Usage
After ImageMagick is installed successfully and OpenScale is downloaded, you can get to scaling themes.

The first argument is responsible for the percentage scale you want. IMPORTANT NOTE: __OMIT__ the percentage symbol otherwise the script will return to you that your input was invalid.

The second argument is the directory you want. Simply find the path of the Openbox theme you want to scale (NOT IN ARCHIVED FORM OR INSIDE OF THE openbox-3 FOLDER), and run the script with `./openscale.sh`.

During the resizing process, you may see quite a few "file not found" errors. It's perfectly normal, as the script is made to convert all button images for all themes.

### Post-execution
After the conversion, use `obconf` to find the theme folder, and create a theme archive. Then simply install the Openbox theme archive as would be any other theme and enjoy.

If the result looks odd and distorted (which might), use [this tool](https://xbm.jazzychad.net) to edit the image to your liking.
