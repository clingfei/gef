# Qemu-user supported architectures
I also list the tools I used in my Ubuntu 24.04 environment.

* x86
    * toolchain: `gcc` via apt with `-m32` option.
    * qemu: `qemu-i386` via apt.
    * gdb: `gdb-multiarch` via apt.
* x64
    * toolchain: `gcc` via apt.
    * qemu: `qemu-x86_64` via apt.
    * gdb: `gdb-multiarch` via apt.
* arm (Cortex-A)
    * toolchain: `gcc-arm-linux-gnueabihf` via apt.
    * qemu: `qemu-arm` via apt.
    * gdb: `gdb-multiarch` via apt.
* aarch64 (Cortex-A)
    * toolchain: `gcc-aarch64-linux-gnu` via apt.
    * qemu: `qemu-aarch64` via apt.
    * gdb: `gdb-multiarch` via apt.
* ppc32
    * toolchain: `gcc-powerpc-linux-gnu` via apt.
    * qemu: `qemu-ppc` via apt.
    * gdb: `gdb-multiarch` via apt.
* ppc64
    * toolchain: `gcc-powerpc64{,le}-linux-gnu` via apt.
    * qemu: `qemu-ppc64{,le}` via apt.
    * gdb: `gdb-multiarch` via apt.
* mips32
    * toolchain: `gcc-mips{,el}-linux-gnu` via apt.
    * qemu: `qemu-mips{,el}` via apt.
    * gdb: `gdb-multiarch` via apt.
* mips64
    * toolchain: `gcc-mips64{,el}-linux-gnuabi64` via apt.
    * qemu: `qemu-mips64{,el}` via apt.
    * gdb: `gdb-multiarch` via apt.
* mipsn32
    * toolchain: `gcc-multilib-mips{,el}-linux-gnu` or `gcc-multilib-mips64{,el}-linux-gnuabi64` via apt with `-mabi=n32` option.
    * qemu: `qemu-mipsn32{,el}` via apt.
    * gdb: `gdb-multiarch` via apt.
* sparc32
    * toolchain: `sparcv8--uclibc--stable-2024.05-1` from https://toolchains.bootlin.com/
    * qemu: `qemu-sparc` via apt.
    * gdb: `gdb-multiarch` via apt.
* sparc32plus
    * toolchain: `gcc-multilib-sparc64-linux-gnu` via apt with `-m32` option.
    * toolchain (Ubuntu 23.04 or before): not found.
    * qemu: `qemu-sparc32plus` via apt.
    * gdb: `gdb-multiarch` via apt.
* sparc64
    * toolchain: `gcc-sparc64-linux-gnu` via apt.
    * toolchain (Ubuntu 23.04 or before): `sparc64--glibc--bleeding-edge-2024.05-1` from https://toolchains.bootlin.com/
        * Because the toolchain obtained with apt seems to be broken since the built ELF always SIGSEGV.
    * qemu: `qemu-sparc64` via apt.
    * gdb: `gdb-multiarch` via apt.
* riscv32
    * toolchain: `riscv32-ilp32d--glibc--bleeding-edge-2024.05-1` from https://toolchains.bootlin.com/
    * qemu: `qemu-riscv32` via apt.
    * gdb: `gdb-multiarch` via apt.
* riscv64
    * toolchain: `gcc-riscv64-linux-gnu` via apt.
    * qemu: `qemu-riscv64` via apt.
    * gdb: `gdb-multiarch` via apt.
* s390x
    * toolchain: `gcc-s390x-linux-gnu` via apt.
    * qemu: `qemu-s390x` via apt.
    * gdb: `gdb-multiarch` via apt.
* sh4
    * toolchain: `gcc-sh4-linux-gnu` via apt.
    * toolchain (Ubuntu 23.04 or before): `sh-sh4--uclibc--bleeding-edge-2024.05-1` from https://toolchains.bootlin.com/
        * Because the toolchain obtained with apt seems to be broken since static build is failed.
        * glibc version is broken too. Use uclibc version.
    * qemu: `qemu-sh4` via apt.
    * gdb: `gdb-multiarch` via apt.
* m68k
    * toolchain: `gcc-m68k-linux-gnu` via apt.
    * qemu: `qemu-m68k` via apt.
    * gdb: `gdb-multiarch` via apt.
* alpha
    * toolchain: `gcc-alpha-linux-gnu` via apt.
    * qemu: `qemu-alpha` via apt.
    * gdb: `gdb-multiarch` via apt.
* hppa32 (PA-RISC)
    * toolchain: `gcc-hppa-linux-gnu` via apt.
    * qemu: `qemu-hppa` via apt.
    * gdb: `gdb-multiarch` via apt.
* or1k (OpenRISC 1000)
    * toolchain: `openrisc--glibc--bleeding-edge-2024.05-1` from https://toolchains.bootlin.com/
    * qemu: `qemu-or1k` via apt.
    * gdb: build from latest. See [docs/FAQ](https://github.com/bata24/gef/blob/dev/docs/FAQ.md#gdb-will-not-load-gef).
* nios2
    * toolchain: `nios2--glibc--bleeding-edge-2024.05-1` from https://toolchains.bootlin.com/
    * qemu: `qemu-nios2` via apt.
    * gdb: build from latest. See [docs/FAQ](https://github.com/bata24/gef/blob/dev/docs/FAQ.md#gdb-will-not-load-gef).
* microblaze
    * toolchain: `microblazebe--glibc--bleeding-edge-2024.05-1` from https://toolchains.bootlin.com/
    * qemu: `qemu-microblaze` via apt.
    * gdb: build from latest. See [docs/FAQ](https://github.com/bata24/gef/blob/dev/docs/FAQ.md#gdb-will-not-load-gef).
* xtensa (lx60)
    * toolchain: `xtensa-lx60--uclibc--bleeding-edge-2024.05-1` from https://toolchains.bootlin.com/
        * Because the toolchain obtained with apt seems to be broken since the C header is unavailable.
    * qemu: `qemu-xtensa` via apt.
    * gdb: `xtensa-lx60--uclibc--bleeding-edge-2023.08-1` from https://toolchains.bootlin.com/
        * Because `gdb` built from latest source will not work with `set architecture xtensa`.
        * But old toolchain includes `xtensa-linux-gdb`, so I used it.
        * The readline seems to be broken in Ubuntu 22.04, but workaround: `LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libncurses.so.6 xtensa-linux-gdb`.
* cris
    * lib: [cris-dist_1.64-1_i386.deb](https://www.axis.com/ftp/pub/axis/tools/cris/compiler-kit/cris-dist_1.64-1_i386.deb)
    * toolchain: [x86_64-gcc-7.3.0-nolibc_cris-linux.tar.xz](https://ftp.iij.ad.jp/pub/linux/kernel/tools/crosstool/files/bin/x86_64/7.3.0/x86_64-gcc-7.3.0-nolibc_cris-linux.tar.xz) from http://ftp.iij.ad.jp/pub/linux/kernel/tools/crosstool/
        * `mkdir cris-gcc-7.3.0-glibc && tar xf x86_64-gcc-7.3.0-nolibc_cris-linux.tar.xz -C cris-gcc-7.3.0-glibc --strip-components 1`
        * `cd cris-gcc-7.3.0-glibc && mkdir rootfs && dpkg-deb -x ../cris-dist_1.64-1_i386.deb rootfs`
        * `export CRIS=$(pwd)/rootfs/usr/local/cris/cris-axis-linux-gnu`
        * `cd /lib/x86_64-linux-gnu && ln -s libisl.so.{23,15} && ln -s libmpfr.so.{6,4}`
        * `cris-linux-gcc -B $CRIS/lib -I $CRIS/sys-include -static ./test.c`
    * qemu: `qemu-cris` via apt.
        * It needs `-cpu` option like `qemu-cris -cpu crisv17 -g 1234 ./a.out`.
        * Could not use `-cpu crisv32` because gdb does not support it.
    * gdb: build from latest. See [docs/FAQ](https://github.com/bata24/gef/blob/dev/docs/FAQ.md#gdb-will-not-load-gef).
* loongarch64
    * toolchain: [CLFS-loongarch64-8.1-x86_64-cross-tools-gcc-glibc.tar.xz](https://github.com/loongson/build-tools/releases/download/2023.08.08/CLFS-loongarch64-8.1-x86_64-cross-tools-gcc-glibc.tar.xz)
    * qemu: `qemu-loongarch64` via apt.
    * qemu (Ubuntu 23.04 or before): build from [latest](https://download.qemu.org/).
        * `./configure --target-list=loongarch64-linux-user && make && cp build/qemu-loongarch64 /usr/local/bin`
    * gdb: build from latest. See [docs/FAQ](https://github.com/bata24/gef/blob/dev/docs/FAQ.md#gdb-will-not-load-gef).
* arc32 (HS38; ARCv2)
    * toolchain: `gcc-arc-linux-gnu` via apt.
    * toolchain (Ubuntu 23.04 or before): `arcle-hs38--glibc--bleeding-edge-2024.05-1` from https://toolchains.bootlin.com/
    * qemu: https://github.com/foss-for-synopsys-dwc-arc-processors/qemu
        * `./configure --target-list=arc-linux-user --disable-werror && make && cp build/qemu-arc /usr/local/bin`
    * gdb: build from latest. See [docs/FAQ](https://github.com/bata24/gef/blob/dev/docs/FAQ.md#gdb-will-not-load-gef).
* arc32 (HS58; ARCv3)
    * toolchain: [arc_gnu_2023.09_prebuilt_arc32_uclibc_linux_install.tar.bz2](https://github.com/foss-for-synopsys-dwc-arc-processors/toolchain/releases/download/arc-2023.09-release/arc_gnu_2023.09_prebuilt_arc32_uclibc_linux_install.tar.bz2)
    * qemu: https://github.com/foss-for-synopsys-dwc-arc-processors/qemu
        * `./configure --target-list=arc-linux-user --disable-werror && make && cp build/qemu-arc /usr/local/bin`
        * It needs `-cpu` option like `qemu-arc -cpu hs5x -g 1234 ./a.out`.
    * gdb: https://github.com/foss-for-synopsys-dwc-arc-processors/binutils-gdb
        * `git switch arc64`
        * `./configure --disable-{binutils,ld,gold,gas,sim,gprof,gprofng} --target=arc64-snps-linux-gnu --with-python=/usr/bin/python3 && make && cp gdb/gdb /usr/local/bin/gdb-arc`
* arc64 (HS68; ARCv3)
    * toolchain: [arc_gnu_2023.09_prebuilt_arc64_glibc_linux_install.tar.bz2](https://github.com/foss-for-synopsys-dwc-arc-processors/toolchain/releases/download/arc-2023.09-release/arc_gnu_2023.09_prebuilt_arc64_glibc_linux_install.tar.bz2)
    * qemu: https://github.com/foss-for-synopsys-dwc-arc-processors/qemu
        * `./configure --target-list=arc64-linux-user --disable-werror && make && cp build/qemu-arc64 /usr/local/bin`
        * It needs `-cpu` option like `qemu-arc64 -cpu hs6x -g 1234 ./a.out`.
    * gdb: https://github.com/foss-for-synopsys-dwc-arc-processors/binutils-gdb
        * `git switch arc64`
        * `./configure --disable-{binutils,ld,gold,gas,sim,gprof,gprofng} --target=arc64-snps-linux-gnu --with-python=/usr/bin/python3 && make && cp gdb/gdb /usr/local/bin/gdb-arc`
* csky
    * toolchain: https://github.com/c-sky/toolchain-build
        * `apt -y install autoconf automake autotools-dev curl python3 libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev`
        * `git submodule update --init && ./build-csky-gcc.py csky-gcc --src ./ --triple csky-unknown-linux-gnu --disable-gdb`
    * qemu: https://github.com/XUANTIE-RV/qemu
        * `sed -i -e '/assert(min <= max);/d' accel/tcg/user-exec.c`
            * You will get an assertion error, so remove it.
            * Or, you can revert to a slightly older version: `git switch xuantie-qemu-6.1.0`
        * `./configure --target-list=cskyv1-linux-user,cskyv1eb-linux-user,cskyv2-linux-user,cskyv2eb-linux-user --disable-{bpf,werror} && make && cp build/qemu-cskyv{1,2}{,eb} /usr/local/bin`
        * It needs `-cpu` option like `qemu-cskyv2 -cpu ck810 -g 1234 ./a.out`.
    * gdb: build from latest. See [docs/FAQ](https://github.com/bata24/gef/blob/dev/docs/FAQ.md#gdb-will-not-load-gef).


# Qemu-user UNSUPPORTED architectures
These will be added if I find a combination that works.
If you find it, please let me know in the issue page.

* bfin:
    * [x] toolchain: `bfin--uclibc--bleeding-edge-2018.02-1` from https://toolchains.bootlin.com/
    * [ ] qemu: https://github.com/vapier/qemu
        * gdb stub is broken.
    * [x] gdb: build from latest. See [docs/FAQ](https://github.com/bata24/gef/blob/dev/docs/FAQ.md#gdb-will-not-load-gef).
* hexagon:
    * [x] toolchain: https://github.com/quic/toolchain_for_hexagon
    * [x] qemu: `qemu-hexagon` via apt.
    * [ ] gdb: not found.
* tilegx:
    * [x] toolchain: https://ftp.riken.jp/Linux/kernel.org/tools/crosstool/files/bin/x86_64/7.3.0/
    * [x] lib: http://www.voidrouter.net/archives/211
    * [ ] qemu: https://github.com/qemu/qemu/releases/tag/v5.2.0
        * the breakpoint is broken.
    * [x] gdb: build from latest. See [docs/FAQ](https://github.com/bata24/gef/blob/dev/docs/FAQ.md#gdb-will-not-load-gef).
* s390
    * [x] toolchain: `gcc-multilib-s390x-linux-gnu` via apt with `-m31` option.
    * [ ] toolchain (Ubuntu 23.04 or before): not found.
    * [ ] qemu: not found.
    * [x] gdb: build from latest. See [docs/FAQ](https://github.com/bata24/gef/blob/dev/docs/FAQ.md#gdb-will-not-load-gef).
* hppa64
    * [x] toolchain: `gcc-hppa64-linux` via apt.
    * [ ] lib: not found.
    * [ ] qemu: not found.
    * [ ] gdb: not found.
* loongarch32
    * [x] toolchain: [loongson-gnu-toolchain-8.3-x86_64-loongarch32r-linux-gnusf-v2.0.tar.xz](https://gitee.com/loongson-edu/la32r-toolchains/releases/download/v0.0.3/loongson-gnu-toolchain-8.3-x86_64-loongarch32r-linux-gnusf-v2.0.tar.xz)
    * [ ] qemu: https://gitee.com/loongson-edu/la32r-QEMU
        * `./configure --target-list=loongarch32-linux-user --disable-werror && make && cp build/qemu-loongarch32 /usr/local/bin`
        * It says `Architecture rejected` when connecting from gdb.
    * [x] gdb: build from latest. See [docs/FAQ](https://github.com/bata24/gef/blob/dev/docs/FAQ.md#gdb-will-not-load-gef).
* e2k
    * [ ] toolchain: not found.
    * [x] qemu: https://github.com/OpenE2K/qemu-e2k
        * `./configure --target-list=e2k-linux-user --disable-werror && make && cp build/qemu-e2k /usr/local/bin`
    * [ ] gdb: https://github.com/OpenE2K/binutils-gdb
        * `git switch gdb-9.1-mcst`
        * `mkdir build && cd build && ../configure --disable-{binutils,ld,gold,gas,sim,gprof,gprofng,nls,bpf} --target=e2k-linux-gnu --with-python=/usr/bin/python3 && make`
        * Crash when it executes. It seems that binding python3 failed.
* nds32
    * [x] toolchain: https://github.com/VincentZWC/prebuilt-nds32-v3f-toolchain
    * [ ] qemu: not found.
    * [ ] gdb: not found.
