Installing the toolchain
========================

### Ubuntu and other Debian based systems

To install the toolchain, run the following commands:
```bash
# Get the Redox OS APT key
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys AA12E97F0881517F

# Install the APT repository
sudo add-apt-repository 'deb https://static.redox-os.org/toolchain/apt /'

# Update your package lists
sudo apt update

# Install the cross compiler
sudo apt install x86-64-unknown-redox-gcc
```

### Arch Linux
To install the toolchain, run the following commands:
 ```bash 
 # Clone libc
 git clone --recursive git@github.com:redox-os/libc
 
 # Go to the packages 
 cd libc/packages/arch
 
 # Start with binutils
 cd binutils
 makepkg -si
 
 # Then autoconf
 cd ../autoconf
 makepkg -si
 
 # Then gcc-freestanding
 cd ../gcc-freestanding
 makepkg -si
 
 # Then newlib
 cd ../newlib
 makepkg -si
 
 # Finally gcc
 cd ../gcc
 makepkg -si
 ```

### Other distros/Mac OS X
To install the toolchain, run the following commands:
 ```bash 
 # Clone libc
 git clone --recursive git@github.com:redox-os/libc
 
 # Run the setup script
 cd libc
 ./setup.sh all
 
 # Add the tools to your path
 export PATH=$PATH:/path/to/libc/build/prefix/bin
 ```
Next steps
----------

Now that we have the build tools and the toolchain, we can finally [compile Redox](getting_started/compiling_redox.html)
