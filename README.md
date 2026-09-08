# PSX Rip
Bash script to backup Playstation (PSX) games in Linux

# psxrip.sh
Script for ripping PSX game discs into `.bin` files with corresponding `.cue` files.

# Requirements 

This tool requires the following to be installed and available in PATH.

 * cdrdao (http://cdrdao.sourceforge.net/) 

# Usage

```bash
psxrip.sh [{--outputdir} <value>] [{--drive} <value>] [{--disable-subchan] [{--help|-h}] [--enable-fast-rip] [--use-raw-driver] FILENAME
```

> The parameter `FILENAME` is __mandatory__. Without it, the script will abort.
>
> Plain spaces &nbsp in the filename are __prohibited__!

## Available switches:
>  --drive       		Define the device to be used. If this parameter is not
>                		provided, /dev/cdrom will be used.
>
>  --help / -h   		Displays this help text.
>
>  --disable-subchan  	Don't extract subchannel data. Subchannel data might be
>                		required for some PSX copy protection though it *could* create
>                		problems. Retry with this parameter set if any problems occur
>                		when trying to use the resulting image.
>
>  --outputdir   		Define the folder in which the resulting image should be saved.
>                		If the folder does not exist, it will be created. If no
>                		--outputdir parameter is given, the folder ~/psxrip will be
>                		used.
>
>  --enable-fast-rip    Runs CD-ROM reader at full speed to get a faster rip but lower 
>						quality 
>						(Not Recommended)
>
>  --disable-umount		Disables automatic unmount of mounted DRIVE if mount is detected. 
>
>  --use-raw-driver 	Uses generic-mmc-raw instead of generic-mmc:0x20000 driver (not-recommended) Here for legacy reasons.
>
>  --disable-eject      Disables CD-ROM eject on a successful rip

# Installation
 1. Download [psxrip.sh](psxrip.sh) to machine with CD/DVD drive
 2. Permit the script to execute:
```bash
   chmod +x `psxrip.sh`
```
 3. Use in terminal:
    
```bash
./psxrip.sh PARAMETERS
```
  - Optionally, move `psxrip.sh` to your `$PATH`

## Configuration
 1. Copy [the configuration example](psxrip.example.conf) to `$HOME/.config/psxrip.conf`
 2. Permit read and write capability:
```bash
chmod o+rw $HOME/.config/psxrip.conf
```
 3. Edit file for your specific needs, referring to [the available options](#Available-switches).

# Images tested with
  * [ePSXe 2.0.5 (64-bit)](https://www.epsxe.com/files/ePSXe205linux.zip)
