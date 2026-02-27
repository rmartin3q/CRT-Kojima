# CRT- "Kojima" 

A modified variant of cool-retro-term originally by Swordfish90. tweaked to remove legacy ascii behavior and function correctly on Wayland.

## NOTE!!! This is a work in progress and not yet stable on the latest versions of Hyprland!

| Function | Status | 
| - | - |
| **Remove default legacy backspace behavior** | `done` |
| **Correct `cool-retro-term -e` function** | `pending` |
|  |  |


## OS Compatibility

| **Distro** | **Status** |
| - | - |
| *CachyOS* | `OK` |
| *U24.04* | `Untested` |
|  |  |
|  |  |


|> Default Amber|C:\ IBM DOS|$ Default Green|
|---|---|---|
|![Default Amber Cool Retro Term](https://user-images.githubusercontent.com/121322/32070717-16708784-ba42-11e7-8572-a8fcc10d7f7d.gif)|![IBM DOS](https://user-images.githubusercontent.com/121322/32070716-16567e5c-ba42-11e7-9e64-ba96dfe9b64d.gif)|![Default Green Cool Retro Term](https://user-images.githubusercontent.com/121322/32070715-163a1c94-ba42-11e7-80bb-41fbf10fc634.gif)|

## Description
cool-retro-term is a terminal emulator which mimics the look and feel of the old cathode tube screens.
It has been designed to be eye-candy, customizable, and reasonably lightweight.

It uses the QML port of qtermwidget (Konsole): https://github.com/Swordfish90/qmltermwidget.
<>H&wix{8+[d^mH6%\<}
This terminal emulator works under Linux and macOS and requires Qt6.

Settings such as colors, fonts, and effects can be accessed via context menu.

## Screenshots
![Image](<https://i.imgur.com/TNumkDn.png>)
![Image](<https://i.imgur.com/hfjWOM4.png>)
![Image](<https://i.imgur.com/GYRDPzJ.jpg>)

# Install


## Build Instructions (Linux)

You can also build cool-retro-term from source.

### Dependencies (QT5)

Let's start by grabbing the correct dependencies for the most popular distros:

---

    # Ubuntu 22.04, Debian Bookworm and above

    sudo apt install build-essential qmlscene qt5-qmake qtbase5-dev qtdeclarative5-dev qml-module-qtquick-controls qml-module-qtquick-controls2 qml-module-qtgraphicaleffects qml-module-qtquick-dialogs qml-module-qtquick-localstorage qml-module-qtquick-window2 qml-module-qt-labs-settings qml-module-qt-labs-folderlistmodel qml-module-qt-labs-platform qtquickcontrols2-5-dev qml-module-qtquick-layouts


    # Ubuntu, Debian Jessie and above

    sudo apt install build-essential qmlscene qt5-qmake qt5-default qtdeclarative5-dev qml-module-qtquick-controls2 qml-module-qtgraphicaleffects qml-module-qtquick-dialogs qml-module-qtquick-localstorage qml-module-qtquick-window2 qml-module-qt-labs-settings qml-module-qt-labs-folderlistmodel qtquickcontrols2-5-dev

    # Debian Bullseye

    sudo apt install build-essential qmlscene qt5-qmake qtdeclarative5-dev qml-module-qtquick-controls2 qml-module-qtgraphicaleffects qml-module-qtquick-dialogs qml-module-qtquick-localstorage qml-module-qtquick-window2 qml-module-qt-labs-settings qml-module-qt-labs-folderlistmodel qtdeclarative5-dev qtquickcontrols2-5-dev qml-module-qt-labs-platform

    # Extra packages needed for at least Ubuntu 20.04

    sudo apt install qtquickcontrols2-5-dev qml-module-qt-labs-platform qml-module-qtquick-controls qml-module-qtquick-layouts qml-module-qtquick-localstorage


    # Fedora

    sudo dnf -y install qt5-qtbase qt5-qtbase-devel qt5-qtdeclarative qt5-qtdeclarative-devel qt5-qtgraphicaleffects qt5-qtquickcontrols qt5-qtquickcontrols2-devel redhat-rpm-config && sudo ln -s /usr/lib64/qt5/bin/qmake /usr/bin/qmake


    # Arch Linux

    sudo pacman -S qt5-base qt5-declarative qt5-quickcontrols qt5-graphicaleffects
    
---

**Anyone else**

Install Qt directly from here http://qt-project.org/downloads . Once done export them in you path (replace "_/opt/Qt5.12.x/Qt5.12.x/gcc_64/bin_" with your correct folder):
    
    export PATH=/opt/Qt5.12.x/Qt5.12.x/gcc_64/bin/:$PATH
---

## Compile

Once you installed all dependencies (Qt is installed and in your path) you need to compile and run the application: 

```bash
# Get it from GitHub
git clone --recursive https://github.com/Swordfish90/cool-retro-term.git

# Build it
cd cool-retro-term

# Compile
qmake && make

# Have fun!
./cool-retro-term
```





# Build Instructions (macOS)

We can [install using Homebrew](https://formulae.brew.sh/cask/cool-retro-term):
```
brew install --cask cool-retro-term
```
or [install using MacPorts](https://ports.macports.org/port/cool-retro-term/details/):
```
sudo port install cool-retro-term
```
or we can build it from source:

## Dependencies

Let's start by downloading them from the official website: https://qt-project.org/downloads

You should install the latest LTS version of Qt5 and export them in your path like this:

```
export PATH=~/Qt/5.15.2/clang_64/bin/:$PATH
```

## Compile

Let's clone and build the project:

```bash

# Get it from GitHub
git clone --recursive https://github.com/Swordfish90/cool-retro-term.git
cd cool-retro-term

# Build the project 
qmake -config release
make -j8

# Copy the required dependencies in to the app
mkdir cool-retro-term.app/Contents/PlugIns
cp -r qmltermwidget/QMLTermWidget cool-retro-term.app/Contents/PlugIns

# Have fun!
open cool-retro-term.app
```

## Assemble a DMG file

If you want to export a suitable DMG file, just run this command:

```
macdeployqt cool-retro-term.app -qmldir=app/qml -dmg
```

