# Install-MikroTik-CHR-on-vps

Simple steps to install Mikrotik Cloud Hosted Router on any Cloud VM whether on Almalinux or Ubuntu etc.

# Prerequisites:
----------------

1: VPS should have a VNC access
2: You will need the following network information:
    - IP Address
    - Net Mask
    - IP Gateway
3: Sometimes, you may need to disable the Virtio driver!

# Information Gathering
-----------------------

Find Disk - lsblk | grep disk | cut -d ' ' -f 1 | head -n 1

Find ethernet - ip route show default | sed -n 's/.* dev \([^\ ]*\) .*/\1/p'

Find VPS IP - ip addr show $ETH | grep global | cut -d' ' -f 6 | head -n 1

Find VPS Gateway - ip route list | grep default | cut -d' ' -f 3

# Installation
--------------
Run the below command to install CHR on the VPS

MikroTik 7.10.2

bash -c "$(curl -L https://raw.githubusercontent.com/azadrahorg/Install-MikroTik-CHR-on-VPS/main/mik78.sh)"

Now reboot the VPS?

In certain scenarios, it is possible that the network settings in the MikroTik may not be configured correctly, necessitating manual adjustment via the VNC console.
