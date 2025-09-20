# Tools Installation Guide

This guide provides instructions for installing the required tools and setting up the environment.

---

### System Requirements
- 6 GB RAM  
- 50 GB HDD  
- Ubuntu 20.04 or higher  
- 4 vCPU  

---

### Resizing the Ubuntu Window to Fit the Screen
```bash
$ sudo apt update
$ sudo apt install build-essential dkms linux-headers-$(uname -r)
$ cd /media/koppisetti09/VBox_GAs_7.1.10
$ ./autorun.sh
```
# Tool Check: Yosys
## Installation Steps

### Update system packages
```
$ sudo apt-get update
```

### Clone Yosys repository
```
$ git clone https://github.com/YosysHQ/yosys.git
$ cd yosys
```

### Install make 
```
$ sudo apt install make
```               

### Install dependencies
```
$ sudo apt-get install build-essential clang bison flex \
    libreadline-dev gawk tcl-dev libffi-dev git \
    graphviz xdot pkg-config python3 libboost-system-dev \
    libboost-python-dev libboost-filesystem-dev zlib1g-dev
```

### Configure build
```
$ make config-gcc
```

### Initialize Git submodule (abc)
```
$ git submodule update --init --recursive
```

### Build Yosys
```
$ make
```

### Install Yosys
```
$ sudo make install
```

### To invoke the Tool
```
$ yosys
```

### Check Yosys installation
```
$ yosys -V
```
<img width="1588" height="1029" alt="Screenshot 2025-09-20 171940" src="https://github.com/user-attachments/assets/456bf9b2-240a-4deb-b048-feb0d202924c" />


# Tool Check: Icarus Verilog (iverilog)
## Installation Steps

### Update system packages
```
$ sudo apt-get update
```

### Install Icarus Verilog
```
$ sudo apt-get install iverilog
```

### To invoke the Tool
```
$ iverilog
```

### Check Icarus Verilog installation
```
$ iverilog -V
```
<img width="1569" height="817" alt="image" src="https://github.com/user-attachments/assets/9802a79a-e39c-4368-bbc6-9e65c8841d54" />

# Tool Check: GTKWave
## Installation Steps
### Update system packages
```
$ sudo apt-get update
```
### Install GTKWave
```
$ sudo apt install gtkwave
```

### To invoke the Tool
```
$ gtkwave
```

### Check GTKWave installation
```
$ gtkwave -V
```

<img width="2083" height="1526" alt="Screenshot 2025-09-20 173432" src="https://github.com/user-attachments/assets/abe8e2b4-0f30-478e-b198-84d306817e01" />







