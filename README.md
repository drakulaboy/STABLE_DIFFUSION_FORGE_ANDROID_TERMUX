THIS WORKS ON 8GB RAM!!! DON'T DISABLE PHANTOM PROCESSOR KILLER DOING THIS WILL MAKE ALL STABLE DIFFUSION TERMUX CRASH!!!

1. Prerequisites
First you have to install Termux and install PRoot. Then install and login to Ubuntu in PRoot


pkg updated && pkg upgrade -y && termux-setup-storage &&
pkg install wget -y && pkg install git -y && pkg install proot -y &&
cd ~ && git clone https://github.com/MFDGaming/ubuntu-in-termux.git && cd ubuntu-in-termux && chmod +x ubuntu.sh && ./ubuntu.sh -y && ./startubuntu.sh 

2. Installing stable-diffusion-webui-forge
Run below commands sequentially as root user in Ubuntu

Install basic tools

apt update && apt upgrade -y && apt-get install curl git gcc make build-essential python3 python3-dev python3-distutils python3-pip python3-venv python-is-python3 -y 

Install required extensions

apt-get install libgl1 libglib2.0-0 libsm6 libxrender1 libxext6 -y

Clone the repository

git clone https://github.com/lllyasviel/stable-diffusion-webui-forge

or

git clone https://github.com/lllyasviel/stable-diffusion-webui-forge.git

Change the current directory

cd stable-diffusion-webui-forge


You Dont Need This Command on newer android 13-14 it can cause crashes but every phone is different 
'Fix' the issue with Python running in PRoot

export ANDROID_DATA=anything 

Install required Python packages

pip install -r requirements.txt 

if you have errors like 
error: externally-managed-environment
then use this command
pip install -r requirements.txt --break-system-packages

Launch the webui. It will take some time to complete first-time installation then everything should be fine

python launch.py --always-cpu --skip-torch-cuda-test --always-offload-from-vram --attention-split --all-in-fp16 --vae-in-cpu

Navigate to the webui in your browser
http://127.0.0.1:7860 

To start after rebooting termux after first installation 

cd ubuntu-in-termux && ./startubuntu.sh

THEN PASTE BOTTOM COMMAND 
cd ubuntu-in-termux && ./startubuntu.sh
cd stable-diffusion-webui-forge && python launch.py --always-cpu --skip-torch-cuda-test --always-offload-from-vram --attention-split --all-in-fp16 --vae-in-cpu


YOU NEED THIS TERMUX MOD VERSION THIS IS THE ONE I USED!

https://github.com/KitsunedFox/termux-monet


