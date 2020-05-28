- [Install](#install)
  * [Requirements](#requirements)
  * [Recommended Browsers](#recommended-browsers)
  * [Release Version](#release-version)
    + [Windows](#windows)
    + [macOS](#macos)
      - [Obtaining server logs on Mac](#obtaining-server-logs-on-mac)
    + [Linux](#linux)
- [Upgrade](#upgrade)
  * [Prepare for upgrading](#prepare-for-upgrading)
  * [Perform the upgrade](#perform-the-upgrade)
- [Alternatives](#alternatives)
  * [Nightly Releases](#nightly-releases)
  * [Development Version](#development-version)
  * [Running As a Server](#running-as-a-server)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>


# Install
OpenRefine is a desktop application in that you download it, install it, and run it on your own computer. However, unlike most other desktop applications, it runs as a small web server on your own computer and you point your web browser at that web server in order to use Refine. So, think of Refine as a personal and private web application.

## Requirements
1. [[Java JRE/JDK installed|Setup-JAVA]]  (If you are running a 64 bit operating system, then it's recommended that you install 64 bit Java)

2. **A Supported OS**:  Windows, Linux, macOS

NOTE: On Windows we do NOT support Cygwin, MSYS2, or Git Bash for running OpenRefine, instead just use Windows Terminal

## Recommended Browsers

OpenRefine works best on browsers based on Webkit, such as:
* Google Chrome
* Chromium
* Opera
* MS Edge

We are aware of some minor rendering and performance issues on other browsers such as Firefox.

## Release Version

* OpenRefine requires you to have a working Java JRE, otherwise you will not be able to start OpenRefine. (the commmand window will just open and close quickly after you double click on OpenRefine.exe)
* [Download OpenRefine here](https://github.com/OpenRefine/OpenRefine/releases).
* Install it as detailed below for your operating system
  * [Windows](Installation-Instructions#windows)
  * [macOS](Installation-Instructions#macos) 
  * [Linux](Installation-Instructions#linux)
* As long as OpenRefine is running, you can point your browser at http://127.0.0.1:3333/ to use it, and you can even use it in several browser tabs and windows.
* If you're running a proxy or get a BindException, you can change the IP configuration with -i and -p, see **Running & Configuration** below, or use refine -help for options.

### Windows

**Install:** Once you have downloaded the .zip file, uncompress it into a folder wherever you want (such as in ```C:\Open-Refine```).

**Run:** Run the ```.exe``` file in that folder. You should see the Command window in which OpenRefine runs. By default, the Command window has a black background and text in monospace font in it.

**Shut down:** When you need to shut down OpenRefine, switch to that Command window, and press ```Ctrl-C```. Wait until there's a message that says the shutdown is complete. That window might close automatically, or you can close it yourself. If you get asked, "Terminate all batch processes? Y/N", just press Y.

**Upgrading:** If you upgrade to a new version of OpenRefine, make sure you [back up your OpenRefine workspace](https://github.com/OpenRefine/OpenRefine/wiki/FAQ-Where-Is-Data-Stored). This will ensure that if problems occur, no data will be lost and you will be able to revert to a previous.

### macOS

**Install via Disk Image:** Once you have downloaded the .dmg file, open it, and drag the OpenRefine icon into the Applications folder icon (just like you would normally install Mac applications). If you get a message saying "Open Refine can't be opened because it is from an unidentified developer" you will need to open System Preferences and go to "Security and Privacy" and the General tab. Here you will see a message indicating that "OpenRefine was blocked from opening because it is not from an identified developer". Click the "Open Anyway" button to complete the OpenRefine installation. (for details WHY you have to do this, see [Issue #2191](https://github.com/OpenRefine/OpenRefine/issues/2191). Note that in macOS Catalina the message shown has the additional text "macOS cannot verify that this app is free from malware", but the reason for the message and the solution is the same)

<img width="677" alt="screenshot 2019-01-07 at 12 21 37" src="https://user-images.githubusercontent.com/576174/50768061-0f620100-1277-11e9-9b50-311ef33f991d.png">


**Install via Homebrew:** Follow our detailed [Homebrew installation guide](Homebrew), or follow quick steps below:
 
1. Install [Homebrew from here](http://brew.sh)

2. In Terminal enter 
```
  brew cask install openrefine
```

3. Then find OpenRefine in your Applications folder.

**Run:** To launch OpenRefine, go to the Applications folder and double click the OpenRefine app. You'll see the OpenRefine app appear in your dock.

**Shut down:** You can switch to the OpenRefine app (clicking on its icon in the dock) and invoke its Quit command.

**See also**: [Cannot install on Mac OS X 10.8 (Mountain Lion) - "Google Refine" is damaged and can't be opened. You should move it to the Trash](https://github.com/OpenRefine/OpenRefine/issues/590)

If you use Yosemite you will need to install [Java for OS X 2014-001](http://support.apple.com/kb/DL1572) first. 

#### Obtaining server logs on Mac

Sometimes it is useful to access the OpenRefine server logs to understand the cause of an issue. Here are the steps to run OpenRefine in a terminal on MacOS:
* Find the OpenRefine app/icon in Finder
* Ctrl+Click on the icon and select "Show Package Contents" from the context menu that displays
* This should open a new Finder menu showing a folder called "Contents" - navigate into this folder then into the "MacOS" folder
* Ctrl+Click on "JavaAppLauncher"
* Choose 'Open With' from menu, and select "Terminal" 

### Linux
**Install / Run:** Once you have downloaded the ```tar.gz``` file, open a shell and type

```
  tar xzf openrefine-linux-2.7.tar.gz
  cd openrefine-2.7
  ./refine
```

This will start OpenRefine and open your browser to its starting page.

**Shut down:** Press ```Ctrl-C``` in the shell.

# Upgrade

## Prepare for upgrading ###
1. [Backup your OpenRefine data in your workspace](https://github.com/OpenRefine/OpenRefine/wiki/FAQ-Where-Is-Data-Stored)
2. (Optional) Export existing OpenRefine Project(s) that you want to continue to work with after upgrade (create *.tar.gz files)

## Perform the upgrade ###
3. Install OpenRefine [latest release](https://github.com/OpenRefine/OpenRefine/releases/latest)
4. Install updated extensions (RDF, etc.)
5. Copy your previously backed up OpenRefine workspace directory back into place, following reverse of step 1.
6. (Optional) Begin to import your OpenRefine .tar.gz Projects that you intend to work with, 1 by 1 while verifying things are OK. 

# Alternatives
## Nightly Releases

We provide easy to install packaged snapshot releases of the latest development version of OpenRefine, which contain the latest features implemented but might also be less stable.  You should [backup your workspace](https://github.com/OpenRefine/OpenRefine/wiki/FAQ-Where-Is-Data-Stored) before trying one.
* https://github.com/OpenRefine/OpenRefine-nightly-releases

## Development Version

If you want to try the very latest developments in OpenRefine, you can try installing the current development version. The development version hasn't had the same level of testing that the release
version has, but we generally try to keep it in good shape.  It will have bug
fixes which are not yet available in the release version, but may also have
new bugs as well.

The installation process for the Development version is more complex as the software has not been prepared for general distribution.

* [Step-by-step to get & build the development version](Building-OpenRefine-From-Source).

## Running As a Server

By default (and for security reasons), Refine only listens to TCP requests coming from localhost (127.0.0.1), on port 3333 (by default). If you want to share your Refine instance with colleagues and respond to TCP requests to any IP address of the machine, run Refine like this from the command line:

```
./refine -i 0.0.0.0
```

or set this option in `refine.ini`:

```
REFINE_HOST=0.0.0.0
```

or set this JVM option:

```
-Drefine.host=0.0.0.0
```

On macOS, you can add a specific entry to the Info.plist file located within the app bundle (`/Applications/OpenRefine.app/Contents/Info.plist`):

```
<key>JVMOptions</key>
<array>
  <string>-Drefine.host=0.0.0.0</string>
  …
</array>
```

Please note that if your machine has an external IP (is exposed to the Internet), you should not do this, or should protect it behind a proxy or firewall, e.g. `nginx`.

