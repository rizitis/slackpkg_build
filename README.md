# slackpkg_build
=========


**How it works:**

When you command `slackpkg_build <package name>` script do:
1. First read `/etc/slackpkg/mirrors` for your slackware repo url
2. Then use wget to download from $url/source/FILE_LIST
3. Read FILE_LIST and found the remote path for $package or DIR and download it using lftp
4. When download finish ask if thats all  or if you want to build package also. 
5. In any case script DONT install builded package just build and stop. 

==========

**Options:**

You can download and build a package

You can download DIR BUT not build it:
```
[DIR]	a/ 	 	 
[DIR]	ap/ 	 	 
[DIR]	d/ 	 	 
[DIR]	e/ 	 	 
[DIR]	f/ 	 	 
[DIR]	installer/ 	 	 
[DIR]	k/ 	 	 
[DIR]	kde/ 	 	 
[DIR]	l/ 	 	 
[DIR]	n/ 	 	 
[DIR]	t/ 	 	 
[DIR]	tcl/ 	 	 
[DIR]	x/	 	 	 
[DIR]	xap/ 	 	 
[DIR]	xfce/		 	 
[DIR]	y/
```
=============

**EXAMPLES**

`slackpkg_build kde` will download all kde DIR

`slackpkg_build xfce` will download all xfce DIR. etc...

`slackpkg_build emacs` will download emacs source folder and ask if you want to build.

==============

**what is not doing:**
1. as said, installation of SlackBuild output `/tmp/package.txz`
2. not downloading files out of a DIR `CHECKSUMS*, MANIFEST.*, *.TXT`
3. if you download a DIR you cant answer  `yes`  to continue for build all subprojects of the DIR/*
4. It not building KDE or X11 files as they dont have personal SlackBuild but belong to an all in one SlackBuild in parent folder

================
### INSTALLATION
Download slackpkg_build script add it in root $PATH and make it executable

Assume you install it in `/usr/local/bin/` 

 `chmod +x /usr/local/bin/slackpkg_build`
 

==============

**Usage:**

`# slackpkg_build <package>`
> will download an offially slackware source DIR or package for hacking  or to build it as is... 

[![asciicast](https://asciinema.org/a/PyahkBW8Q3EtDtj4dn9rxLvi2.svg)](https://asciinema.org/a/PyahkBW8Q3EtDtj4dn9rxLvi2)
