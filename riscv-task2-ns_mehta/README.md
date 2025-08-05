Spike Version:
```
Spike RISC-V ISA Simulator 1.1.1-dev
```
GCC Version:
```
Using built-in specs.
COLLECT_GCC=riscv64-unknown-elf-gcc
COLLECT_LTO_WRAPPER=/home/nishant/riscv_toolchain/riscv_gnu/libexec/gcc/riscv64-unknown-elf/15.1.0/lto-wrapper
Target: riscv64-unknown-elf
Configured with: /home/nishant/riscv_toolchain/riscv-gnu-toolchain/build/../gcc/configure --target=riscv64-unknown-elf --prefix=/home/nishant/riscv_toolchain/riscv_gnu --disable-shared --disable-threads --enable-languages=c,c++ --with-pkgversion= --with-system-zlib --enable-tls --with-newlib --with-sysroot=/home/nishant/riscv_toolchain/riscv_gnu/riscv64-unknown-elf --with-native-system-header-dir=/include --disable-libmudflap --disable-libssp --disable-libquadmath --disable-libgomp --disable-nls --disable-tm-clone-registry --src=../../gcc --enable-multilib --with-abi=lp64d --with-arch=rv64gc --with-isa-spec=20191213 'CFLAGS_FOR_TARGET=-Os    -mcmodel=medlow' 'CXXFLAGS_FOR_TARGET=-Os    -mcmodel=medlow'
Thread model: single
Supported LTO compression algorithms: zlib
gcc version 15.1.0 () 
```

Compile Commands
```
riscv64-unknown-elf-gcc -O0 -g -march=rv64imac -mabi=lp64 -DUSERNAME="\"$U\"" -DHOSTNAME="\"$H\"" -DMACHINE_ID="\"$M\"" -DBUILD_UTC="\"$T\"" -DBUILD_EPOCH=$E factorial.c -o factorial
spike pk ./factorial
riscv64-unknown-elf-gcc -O0 -S factorial.c -o factorial.s
cat factorial.s
riscv64-unknown-elf-objdump -d ./factorial | sed -n '/<main>:/,/^$/p' | tee
factorial_main_objdump.txt
riscv64-unknown-elf-objdump -d ./factorial | sed -n '/<main>:/,/^$/p' | tee factorial_main_objdump.txt
cat factorial_main_objdump.txt 
spike -version
riscv64-unknown-elf-gcc -O0 -g -march=rv64imac -mabi=lp64 -DUSERNAME="\"$U\"" -DHOSTNAME="\"$H\"" -DMACHINE_ID="\"$M\"" -DBUILD_UTC="\"$T\"" -DBUILD_EPOCH=$E max_array.c -o max_array
riscv64-unknown-elf-gcc -O0 -g -march=rv64imac -mabi=lp64 -DUSERNAME="\"$U\"" -DHOSTNAME="\"$H\"" -DMACHINE_ID="\"$M\"" -DBUILD_UTC="\"$T\"" -DBUILD_EPOCH=$E bitops.c -o bitops
riscv64-unknown-elf-gcc -O0 -g -march=rv64imac -mabi=lp64 -DUSERNAME="\"$U\"" -DHOSTNAME="\"$H\"" -DMACHINE_ID="\"$M\"" -DBUILD_UTC="\"$T\"" -DBUILD_EPOCH=$E bubble_sort.c
riscv64-unknown-elf-gcc -O0 -g -march=rv64imac -mabi=lp64 -DUSERNAME="\"$U\"" -DHOSTNAME="\"$H\"" -DMACHINE_ID="\"$M\"" -DBUILD_UTC="\"$T\"" -DBUILD_EPOCH=$E bubble_sort.c -o bubble_sort
spike pk ./max_array
spike pk ./bitops
spike pk ./bubble_sort
riscv64-unknown-elf-gcc -O0 -S max_array.c -o max_array.s
riscv64-unknown-elf-gcc -O0 -S bitops.c -o bitops.s
riscv64-unknown-elf-gcc -O0 -S bubble_sort.c -o bubble_sort.s
riscv64-unknown-elf-objdump -d ./factorial | sed -n '/<main>:/,/^$/p' | tee max_array_main_objdump.txt
riscv64-unknown-elf-objdump -d ./factorial | sed -n '/<main>:/,/^$/p' | tee bitops_main_objdump.txt
riscv64-unknown-elf-objdump -d ./factorial | sed -n '/<main>:/,/^$/p' | tee bubble_sort_main_objdump.txt
cat max_array_main_objdump.txt 
cat factorial_main_objdump.txt 
riscv64-unknown-elf-objdump -d ./max_array | sed -n '/<main>:/,/^$/p' | tee max_array_main_objdump.txt
riscv64-unknown-elf-objdump -d ./bitops | sed -n '/<main>:/,/^$/p' | tee bitops_main_objdump.txt
riscv64-unknown-elf-objdump -d ./bubble_sort | sed -n '/<main>:/,/^$/p' | tee bubble_sort_main_objdump.txt
spike pk ./factorial
spike pk ./max_array
spike pk ./bitops
spike pk ./bubble_sort
```
ProofID/RunID is visible in each output screenshot
