# BossBox Build Script

These is the build script for both versions of BossBox

Once you have built a new box, follow the following instructions to package it up

# SSH into the box
vagrant ssh


# "Zero it out" (make it small as possible)
sudo dd if=/dev/zero of=/EMPTY bs=1M

sudo rm -f /EMPTY



# Clear APT cache (make it smaller)
sudo apt-get autoremove

sudo apt-get clean


# Delete bash histroy and exit
cat /dev/null > ~/.bash_history && history -c && exit


# Stop the box
vagrant halt


# Package the box with Vagrant
vagrant package --output my-custom-environment.box


# Add the box to your local vagrant!
vagrant box add my-custom-environment my-custom-environment.box

# Upload the box to Vagrant Cloud
Coming Soon!
