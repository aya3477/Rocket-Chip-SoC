
## Submodules in Rocket Chip 

+ **Chisel** - The HDL we use at Berkeley to develop our RTL. 
+ **Rocket** - Source code for the Rocket core and caches. 
+ **Uncore** - Logic outside the core: coherence agent, Dle interface, host interface.
+ **Hardfloat** - Parameterized FMAs and converters.
+ **Dramsim2** - Simulates DRAM Dming for simulaDons.
+ **Fpga-zync** - Code that helps get rocket-chip on FPGAs.
+ **Riscv-tools** - SoPware toolchain used with this version of Rocket Chip.
+ **CSrc** - Glue code to be used with the C++ emulator.
+ **Emulator** - Build directory for the C++ emulator, contains generated code and executables.
+ **Fsim** - Build directory for FPGA verilog generaDon.
+ **Project** - Scala/sbt configuraDon files.
+ **Src** - Chisel source code for rocket chip.
+ **Vsrc** - Verilog test harness for rocket-chip.
+ **Vsim** - Build directory for ASIC verilog generaDon 

[Source](https://riscv.org/wp-content/uploads/2015/01/riscv-rocket-chip-tutorial-bootcamp-jan2015.pdf)

## Instructions for Rocket Chip on OS

### Install Rocket Chip

    $ git clone https://github.com/ucb-bar/rocket-chip.git
    $ cd rocket-chip
    $ git submodule update --init

### Required Installation 
#### Installing Homebrew 
    
    $ cd ..
    $ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

#### Install Java 17  
  
    $ brew install default-jdk
    
  OR [x64 DMG Installer](https://www.oracle.com/java/technologies/downloads/#jdk17-mac)
  
#### Install sbt and Verilator for Chisel

    $ brew install git perl python3 make
    $ brew install g++
    $ brew install sbt verilator
    
#### Install RISC-V ToolChain

    $ git clone https://github.com/freechipsproject/rocket-tools
    $ cd rocket-tools
    $ git submodule update --init --recursive
    $ export RISCV=/path/to/install/riscv/toolchain
    $ export MAKEFLAGS="$MAKEFLAGS -j8" # Quad-Core
    $ ./build-rv32ima.sh # RV32
    
 

