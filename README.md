# How to Run

## Setup

### Install make:
`sudo apt install make`

#### I was unable to confirm if the next command + file modification is necessary:

`sudo vim /etc/apt/apt.conf.d/20auto-upgrades`

Replace the '1' with '0' in the line with "Unattended-Upgrade" and save the file


### Install gcc
`sudo apt install gcc`

### Install linux-headers
sudo apt install linux-headers-$(uname -r)

### Install Build Essentials
sudo apt install build-essential

## Run

### Run `make`

To load the kernel module, run:

`sudo insmode hello.ko`

To remove the kernel module, run:

`sudo rmmod hello`


To confirm if "Hello World" or "Goodbye!" have been printed, the logs can be checked:

`cat /var/log/syslog | grep -a "Hello World"`

`cat /var/log/syslog | grep -a "Goodbye!"`


## Debugging

While figuring out the Hello World and Goodbye was trivial, compiling took a while. I had a bit of issue with some lock acquision for apt. As mentioned above, I installed Debian/Ubuntu Linux headers, but I can't fully confirm if they were there to begin with, so that might be redundant. Additionally, some auto upgrading was disabled, but I wasn't able to reliably test if that was actually causing an error. However, if all of the steps are followed, the code should compile and will be loaded into the kernel.