# riscv.linuxboot
export RISCV and PATH to toolchain


cd riscv.core.buildroot
make rocket_defconfig
make
cd ..
cd riscv-pk
mkdir build
cd build
../configure --prefix=$RISCV --host=riscv64-unknown-elf --with-dts=./../../riscv.core.buildroot/board/riscv/rocket/rocket.dts --with-payload=./../../riscv.core.buildroot/output/images/vmlinux --enable-logo --with-arch=rv64imac
make
 
