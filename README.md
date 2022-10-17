# How to setup Ardupilot-Sitl, Mavproxy & Missionplanner on Ubuntu(20.04)
## 1- Setting up Ardupilot-Sitl and Mavproxy
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
## Install required packages (Mavproxy and other required packages)
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
## 2- Installing Mission planner
## install mono
```
sudo apt install gnupg ca-certificates
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
echo "deb https://download.mono-project.com/repo/ubuntu stable-focal main" | sudo tee /etc/apt/sources.list.d/mono-official-stable.list
sudo apt update
sudo apt install mono-devel
```
### download Mission planner zip file 
https://firmware.ardupilot.org/Tools/MissionPlanner/archive/MissionPlanner-1.3.74.zip /
unzip the file and run this in mp directory
```
mono MissionPlanner.exe
```

