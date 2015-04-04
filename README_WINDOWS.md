Windows compatability
---------------------

#### Summary / Goals
I've made some very crude efforts at Windows compatibility in my fork.  
My current focus is on identifying compatability problems and making easy fixes. 
I'm focused on getting a minimal GUI version working such that messages are sent securely. Features like secure storage, TPM, and spell check are lower priority.  
I hope this work will form a starting point for other developers, as I'm not that familiar with Windows, GTK, Go, or even Git.

#### Features currently not compatible with Windows
+ Spell checking
+ TPM
+ Checks for encrypted storage

#### Current development environment
I have made some progress in Windows 7 with the GTK+ bundle 3.6.4 for Win32 with MinGW (also Win32). I'm using Go 1.3rc2 for Win32. I would recommend sticking to 32 bit packages at present as GTK support for Win64 is experimental (according to http://www.gtk.org/download/win64.php).  


#### Steps I took to set up a build environment
I did the following in Windows 7 within a VirtualBox  
Here's what I did to get going--some of this may be redundant / unnecessary.  
Install the following:  
GTK bundle 3.6.4, Win32 - http://www.gtk.org/download/win32.php  
Go 1.3rc2, Win32 - https://storage.googleapis.com/golang/go1.3rc2.windows-386.msi  
MinGW, Win32 - http://www.mingw.org/  
Git  
Pkg-config 0.26-1: http://pkgconfig.freedesktop.org/releases/ (installed to C:\MinGW\bin  
glib 2.28 - http://ftp.gnome.org/pub/gnome/binaries/win32/glib/2.28/glib_2.28.8-1_win32.zip  

I also installed / set up pkg-config:  
```  
  go to http://ftp.gnome.org/pub/gnome/binaries/win32/dependencies/  
  download the file pkg-config_0.26-1_win32.zip  
  extract the file bin/pkg-config.exe to C:\MinGW\bin  

  download the file gettext-runtime_0.18.1.1-2_win32.zip  
  extract the file bin/intl.dll to C:\MinGW\bin  

  go to http://ftp.gnome.org/pub/gnome/binaries/win32/glib/2.28  
  download the file glib_2.28.8-1_win32.zip  
  extract the file bin/libglib-2.0-0.dll to C:\MinGW\bin  
```

Set the following environment variables:  
PKG_CONFIG_PATH=C:\GTK\lib\pkgconfig  
GOPATH=C:\gopath  
GOROOT=C:\Go  
