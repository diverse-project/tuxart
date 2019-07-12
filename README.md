# Welcome to TuxArt 

The **goal** of TuxArt is to create as many different [Tux](https://en.wikipedia.org/wiki/Tux_(mascot)) as possible configuration files of the Linux kernel. 
We are developping a Python-based generator that can produces the Tux of your machine, a family of Tux (as a gif or grid), or a custom Tux. You can even use a Docker image to play with TuxArt!
![tux grid](tuxart/examples/TuxFamily.png)

## Context
The first question you might ask if you are not familiar with Linux is what is Tux?
Well basically [Tux](https://en.wikipedia.org/wiki/Tux_(mascot)) (link to the wiki) is a penguin and the official mascot of the Linux kernel. The Linux kernel contains over 15000 configuration options, most of them take 3 different value (yes, no or module).
So theorically there are 3^15000 possible configuration files of the Linux kernel.

This program will fetch for your running Kernel's configuration file and then generate an unique Tux based on the current active configurations on your kernel.

The script will fetch in the default folders /boot and /proc for a configuration file.

An arbitrary kernel configuration file can be passed as argument, output file will be stored in ~/Pictures/CustomTux


## Download and Install Insructions

- From terminal type
	- `wget "https://github.com/HommeOursPorc/tuxart/releases/download/3.2.1/tuxart-3.2.1.tar.gz"`
	- `pip3 install tuxart-3.2.1.tar.gz --user --install-option="--install-scripts=~/.local/bin"`
(note: you can use `pip3 install . --user --install-option="--install-scripts=~/.local/bin"` if you want to update tuxart from the sources/git assuming that '.' refers to the directory of the sources)

- Then add `~/.local/bin` to your command line with
	- `export PATH=$PATH:~/.local/bin`



### Running TuxArt

- From terminal type
	- `tuxart`

If you want to pass your custom configuration file:
- From terminal type
	- `tuxart -f [configuration file]`

Type `tuxart -h` or `tuxart --help` for help from terminal

### Docker and TuxArt

You can build the image with the Docker file or simply reuse a custom and ready-to-use image: 
`docker run --rm macher/tuxart tuxart --grid linux-4.13.3`

## Options

Various options are available if you already have a linux kernel.*

You can either :
- **generate a grid of Tux** (like the one in the header)
- **generate a .gif of Tux**

![Super Tux](tuxart/examples/SuperTux.gif)

 - **summon elemenTux** ( all configurations set to yes, module or no )


 ![Red tux](tuxart/examples/redtux.svg)
 ![Green tux](tuxart/examples/greentux.svg)
 ![Blue tux](tuxart/examples/bluetux.svg)


### Running options 

   - From terminal type :
	   - `tuxart --grid [path to kernel folder] [number of tux, default = 4]`
	   - `tuxart --gif [path to kernel folder] [number of tux, default = 4]`
	   - `tuxart --rgb [path to kernel folder]`


*If you don't have a kernel, download one from https://www.linux-mips.org/pub/linux/mips/kernel/v4.x/
Unpack the archive and run one of the command lines from above with the path to the archive's folder passed as argument.*



##### If you are interested in how tuxart work I suggest you to read the [DESIGN.md](./DESIGN.md) file

### The future of tuxart

While working with randomly generated kernels, a visual feedback can increase the comprehension of the latters.

Visual feedback can be improved by increasing choice between custom accessories. This kind of benefits can be achieved by adding more accessories and by fully respecting dependencies between related configurations.

#### Known Issues
- Loading bar get overwritten in --grid and --gif options
- Misconfiguration of the installation folder when .tar is download from pypi

Want to see 100 variants of the Tux family? https://gist.github.com/FAMILIAR-project/2d6588ad2711be43decdc2a9128d6c45
