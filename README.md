# my_p4_simulation

This repository is for training how to install and use the P4 in a simulation environment like Mininet.
Non-root user is considered for this setup. So, follow step by step ... 


## Install Prerequirements

    $ sudo apt-get update && sudo apt-get install -y git curl build-essential python3 python3-pip
## 1- Download & Install the Mininet 
    $ sudo git clone https://github.com/mininet/mininet.git
    $ cd mininet
    $ git checkout 2.3.0
    $ git config --global --add safe.directory /home/alireza/My_P4_Simulation/mininet
    $ sudo apt install python3-pycodestyle or sudo pip3 install pycodestyle
    $ sudo PYTHON=python3 mininet/util/install.sh -n   # install Python 3 Mininet
    
**Note:** If you face problem with 'pep8' you can use the follwoing option!

    $ sudo apt install mininet

Check the Python version of the Mininet 

    $ echo py sys.version | sudo mn -v output
    
## 2- Install P4 & BMv2 switch

    $ sudo apt-get install -y autoconf automake libtool libssl-dev g++ libpcap-dev \
    libboost-dev libboost-system-dev libboost-filesystem-dev libboost-thread-dev \
    libboost-test-dev libevent-dev libjudy-dev libbz2-dev cmake \
    libffi-dev libgmp-dev libpcre3-dev libavl-dev libev-dev libjson-c-dev
    
    $ git clone https://github.com/p4lang/behavioral-model.git 
    $ cd behavioral-model

### 2-1 Install 'thrift' compiler

    $ cd thrift
    $ ./build_thrift.sh
    $ cd .. 
    
**Note:** If './build_thrift.sh' doesn't exist follow as below!!

    $ sudo apt-get install thrift-compiler

### 2-2 Install BMv2
Be sure you are in the 'behavioral-model' folder then

    $ sudo ./autogen.sh
    $ sudo ./configure
    $ sudo make
    $ sudo make install

## 3- Install PI and P4C (P4 Compiler)
### 3-1 Install PI 

    $ Install PI
    $ sudo git clone https://github.com/p4lang/PI.git
    $ cd PI
    $ sudo ./autogen.sh
    $ sudo ./configure --with-proto
    $ git config --global --add safe.directory /home/alireza/My_P4_Simulation/PI
    $ sudo make
    $ sudo make install
    $ cd ..

### 3-2 Install P4C

    $ sudo git clone https://github.com/p4lang/p4c.git
    $ cd p4c
    $ sudo mkdir build
    $ cd build
    $ sudo apt-get install libboost-iostreams-dev libboost-graph-dev         # Prerequirements installment if it was required!!
    $ sudo cmake ..
    $ sudo make
    $ sudo make install
    $ cd ../..

# 4- Install Runtime Controller 

    $ sudo apt-get update
    $ sudo apt-get install -y build-essential autoconf libtool pkg-config \
                        libgflags-dev libgtest-dev clang libc++-dev
    $ 
