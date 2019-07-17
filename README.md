# Wyse Linux Installation

## Why

I managed to get my hands on a wyse thin client pc for realively cheap, but it
came with an unusable Window 7 Embedded OS.  
This wil be a tutorial to get Debian up and running on the 4GB System.

## Step 1 - Debian Installation

Download [net install](https://www.debian.org/CD/netinst/) for Debian, and 
create a bootable drive with it.  
To boot from the drive, enter the bios by hitting the Del key and entering in
`Fireport`.  
Move your USB drive to the top of the boot list.  
Install Debain normally from there.

## Step 2 - Disabling Swap

Since the system comes with only 4GB Storage and 2GB of that is used by swap, we
going to have diable swap.  

- Login your account and go root, `su` and enter the root password.  
- Run `/sbin/swapoff -a` to disable all swap devices.
- Remove the swap entry in fsab, `vi /ect/fstab`
- Check that swap was disabled, `free -h`

## Step 3 - Add Swap To System

- Start fdisk, `/sbin/fdisk /dev/sda`
- List all partition with p
- Delete all the partitions on sda with d and input number
- Create a new partition with n and use default settings
- Run `/sbin/resize2fs /dev/sda1` to register the new partition. 


## Step 4 (optional) - Add Sudo

`apt install sudo` to install sudo  
`/sbin/usermod -aG sudo <username>` to add user to sudo users

## Step 5 (optional) - Install xcfe4

`apt install xcfe4` for XCFE Desktop  
`apt install xcfe4-goodies` for additional XCFE Plugins
