# qt5-crosscompile-rpi-ansible

This is an ansible playbook for cross-compiling Qt5 for the Raspberry Pi. It is mostly based on the [Qt RPi beginner guide](https://wiki.qt.io/RaspberryPi_Beginners_Guide).

## Running

This requires linux, and root access. Install ansible (1.6 or higher), and then type `./run`, as root. Paths are currently hardcoded, all files will be downloaded in `/opt/buildroot`.

After running the `./run` script, Qt5 will be downloaded and configured and ready for compilation.
Compiling takes a long time, so this could be done best in a `screen` session:

    cd /opt/buildroot/qt5
    make -j 4
    make install
    
## Compiling an example

After installation, all Qt tools will be installed in `/usr/local/qt5pi/bin`. You can now compile any Qt `.pro` project for the RPi by calling `/usr/local/qt5pi/bin/qmake`.

Note that this will compile Qt as static libraries, with the idea that the output binary is statically linked to the Qt library, for easy portability.

    
