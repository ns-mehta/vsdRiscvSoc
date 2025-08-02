
# Task 1
The following commands have been executed:
```
cd
pwd=$PWD
mkdir riscv_toolchain && cd riscv_toolchain
mkdir riscv_gnu
git clone https://github.com/riscv-collab/riscv-gnu-toolchain.git
cd riscv-gnu-toolchain
mkdir build && cd build
echo 'export PATH="$HOME/riscv_toolchain/riscv_gnu/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
../configure --prefix=$pwd/riscv_toolchain/riscv_gnu --enable-multilib
make -j$(nproc)
cd ../..
git clone https://github.com/riscv-software-src/riscv-isa-sim.git
cd riscv-isa-sim
mkdir build && cd build
../configure --prefix=$pwd/riscv_toolchain/riscv_gnu
make -j$(nproc)
sudo make install
cd ../..
git clone https://github.com/riscv-software-src/riscv-pk.git
cd riscv-pk
mkdir build && cd build
../configure --prefix=$pwd/riscv_toolchain/riscv_gnu --host=riscv64-unknown-elf
make -j$(nproc)
make install
```

The Prebuilt toolchain was not used as it's assembler version was not getting compatiable with the version of the Proxy Kernal.

The program output from spike pk./unique_test
```
RISC-V Uniqueness Check
User: nishant
Host: nishant-HP
UniqueID: 0x862edac5bdd8533c
GCC_VLEN: 6

```
