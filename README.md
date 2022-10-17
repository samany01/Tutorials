# How to setup Ardupilot-Sitl, Mavproxy & Missionplanner on Ubuntu(20.04)
## Setting up Ardupilot-Sitl
## Install git
```
sudo apt-get update

sudo apt-get install git

sudo apt-get install gitk git-gui
```
## Clone ArduPilot repository
```
git clone https://github.com/ArduPilot/ardupilot.git
cd ardupilot
git submodule update --init --recursive
```
## Install required packages
```
cd ardupilot
Tools/environment_install/install-prereqs-ubuntu.sh -y
. ~/.profile
```
log out and log in or restart 
## Adding the path
```
gedit ~/.bachrc   (open bachrc file and add these two lines at the end)
export PATH=$PATH:$HOME/ardupilot/Tools/autotest
export PATH=/usr/lib/ccache:$PATH
. ~/.bashrc      
```
