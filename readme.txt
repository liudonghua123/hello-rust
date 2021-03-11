# https://www.rust-lang.org/learn/get-started
D:\code\rust>cargo new hello-rust
     Created binary (application) `hello-rust` package

D:\code\rust>
D:\code\rust\hello-rust>rustup toolchain list
stable-x86_64-pc-windows-msvc (default)

D:\code\rust\hello-rust># install 32-bit toolchain 
D:\code\rust\hello-rust>rustup install stable-i686-pc-windows-msvc
D:\code\rust\hello-rust># set default toolchain if necessary
D:\code\rust\hello-rust>rustup default stable-i686-pc-windows-msvc
D:\code\rust\hello-rust># build 64 binary
D:\code\rust\hello-rust>cargo build --target=x86_64-pc-windows-msvc --release
   Compiling hello-rust v0.1.0 (D:\code\rust\hello-rust)
    Finished release [optimized] target(s) in 7.30s

D:\code\rust\hello-rust># build 32 binary
D:\code\rust\hello-rust>cargo build --target=i686-pc-windows-msvc --release
   Compiling hello-rust v0.1.0 (D:\code\rust\hello-rust)
error[E0463]: can't find crate for `std`
  |
  = note: the `i686-pc-windows-msvc` target may not be installed

error: aborting due to previous error

For more information about this error, try `rustc --explain E0463`.
error: could not compile `hello-rust`

To learn more, run the command again with --verbose.

D:\code\rust\hello-rust>
# https://users.rust-lang.org/t/how-to-build-both-32-and-64-bit-app-on-windows/26365/3
# https://rust-lang.github.io/rustup-components-history/i686-pc-windows-msvc.html
# https://crates.io/
D:\code\rust\hello-rust># IMPORTANT!!! 
D:\code\rust\hello-rust>rustup target add i686-pc-windows-msvc
info: downloading component 'rust-std' for 'i686-pc-windows-msvc'
info: installing component 'rust-std' for 'i686-pc-windows-msvc'
info: using up to 500.0 MiB of RAM to unpack components
 20.8 MiB /  20.8 MiB (100 %)  12.1 MiB/s in  1s ETA:  0s

D:\code\rust\hello-rust>
D:\code\rust\hello-rust>cargo build --target=i686-pc-windows-msvc --release
   Compiling hello-rust v0.1.0 (D:\code\rust\hello-rust)
    Finished release [optimized] target(s) in 0.39s

D:\code\rust\hello-rust># show you all the deps.
D:\code\rust\hello-rust>cargo tree
hello-rust v0.1.0 (D:\code\rust\hello-rust)

D:\code\rust\hello-rust>
D:\code\rust\hello-rust>rustup show
Default host: x86_64-pc-windows-msvc
rustup home:  C:\Users\Liu.D.H\.rustup

installed toolchains
--------------------

stable-i686-pc-windows-msvc
stable-x86_64-pc-windows-msvc (default)

installed targets for active toolchain
--------------------------------------

i686-pc-windows-msvc
x86_64-pc-windows-msvc

active toolchain
----------------

stable-x86_64-pc-windows-msvc (default)
rustc 1.50.0 (cb75ad5db 2021-02-10)


D:\code\rust\hello-rust>
D:\code\rust\hello-rust>rustc --print target-list
aarch64-apple-darwin
aarch64-apple-ios
aarch64-apple-ios-macabi
aarch64-apple-tvos
aarch64-fuchsia
aarch64-linux-android
aarch64-pc-windows-msvc
aarch64-unknown-freebsd
aarch64-unknown-hermit
aarch64-unknown-linux-gnu
aarch64-unknown-linux-musl
aarch64-unknown-netbsd
aarch64-unknown-none
aarch64-unknown-none-softfloat
aarch64-unknown-openbsd
aarch64-unknown-redox
aarch64-uwp-windows-msvc
aarch64-wrs-vxworks
arm-linux-androideabi
arm-unknown-linux-gnueabi
arm-unknown-linux-gnueabihf
arm-unknown-linux-musleabi
arm-unknown-linux-musleabihf
armebv7r-none-eabi
armebv7r-none-eabihf
armv4t-unknown-linux-gnueabi
armv5te-unknown-linux-gnueabi
armv5te-unknown-linux-musleabi
armv5te-unknown-linux-uclibceabi
armv6-unknown-freebsd
armv6-unknown-netbsd-eabihf
armv7-apple-ios
armv7-linux-androideabi
armv7-unknown-freebsd
armv7-unknown-linux-gnueabi
armv7-unknown-linux-gnueabihf
armv7-unknown-linux-musleabi
armv7-unknown-linux-musleabihf
armv7-unknown-netbsd-eabihf
armv7-wrs-vxworks-eabihf
armv7a-none-eabi
armv7a-none-eabihf
armv7r-none-eabi
armv7r-none-eabihf
armv7s-apple-ios
asmjs-unknown-emscripten
avr-unknown-gnu-atmega328
hexagon-unknown-linux-musl
i386-apple-ios
i586-pc-windows-msvc
i586-unknown-linux-gnu
i586-unknown-linux-musl
i686-apple-darwin
i686-linux-android
i686-pc-windows-gnu
i686-pc-windows-msvc
i686-unknown-freebsd
i686-unknown-haiku
i686-unknown-linux-gnu
i686-unknown-linux-musl
i686-unknown-netbsd
i686-unknown-openbsd
i686-unknown-uefi
i686-uwp-windows-gnu
i686-uwp-windows-msvc
i686-wrs-vxworks
mips-unknown-linux-gnu
mips-unknown-linux-musl
mips-unknown-linux-uclibc
mips64-unknown-linux-gnuabi64
mips64-unknown-linux-muslabi64
mips64el-unknown-linux-gnuabi64
mips64el-unknown-linux-muslabi64
mipsel-sony-psp
mipsel-unknown-linux-gnu
mipsel-unknown-linux-musl
mipsel-unknown-linux-uclibc
mipsel-unknown-none
mipsisa32r6-unknown-linux-gnu
mipsisa32r6el-unknown-linux-gnu
mipsisa64r6-unknown-linux-gnuabi64
mipsisa64r6el-unknown-linux-gnuabi64
msp430-none-elf
nvptx64-nvidia-cuda
powerpc-unknown-linux-gnu
powerpc-unknown-linux-gnuspe
powerpc-unknown-linux-musl
powerpc-unknown-netbsd
powerpc-wrs-vxworks
powerpc-wrs-vxworks-spe
powerpc64-unknown-freebsd
powerpc64-unknown-linux-gnu
powerpc64-unknown-linux-musl
powerpc64-wrs-vxworks
powerpc64le-unknown-linux-gnu
powerpc64le-unknown-linux-musl
riscv32gc-unknown-linux-gnu
riscv32i-unknown-none-elf
riscv32imac-unknown-none-elf
riscv32imc-unknown-none-elf
riscv64gc-unknown-linux-gnu
riscv64gc-unknown-none-elf
riscv64imac-unknown-none-elf
s390x-unknown-linux-gnu
sparc-unknown-linux-gnu
sparc64-unknown-linux-gnu
sparc64-unknown-netbsd
sparc64-unknown-openbsd
sparcv9-sun-solaris
thumbv4t-none-eabi
thumbv6m-none-eabi
thumbv7a-pc-windows-msvc
thumbv7a-uwp-windows-msvc
thumbv7em-none-eabi
thumbv7em-none-eabihf
thumbv7m-none-eabi
thumbv7neon-linux-androideabi
thumbv7neon-unknown-linux-gnueabihf
thumbv7neon-unknown-linux-musleabihf
thumbv8m.base-none-eabi
thumbv8m.main-none-eabi
thumbv8m.main-none-eabihf
wasm32-unknown-emscripten
wasm32-unknown-unknown
wasm32-wasi
x86_64-apple-darwin
x86_64-apple-ios
x86_64-apple-ios-macabi
x86_64-apple-tvos
x86_64-fortanix-unknown-sgx
x86_64-fuchsia
x86_64-linux-android
x86_64-linux-kernel
x86_64-pc-solaris
x86_64-pc-windows-gnu
x86_64-pc-windows-msvc
x86_64-rumprun-netbsd
x86_64-sun-solaris
x86_64-unknown-dragonfly
x86_64-unknown-freebsd
x86_64-unknown-haiku
x86_64-unknown-hermit
x86_64-unknown-hermit-kernel
x86_64-unknown-illumos
x86_64-unknown-l4re-uclibc
x86_64-unknown-linux-gnu
x86_64-unknown-linux-gnux32
x86_64-unknown-linux-musl
x86_64-unknown-netbsd
x86_64-unknown-openbsd
x86_64-unknown-redox
x86_64-unknown-uefi
x86_64-uwp-windows-gnu
x86_64-uwp-windows-msvc
x86_64-wrs-vxworks

D:\code\rust\hello-rust>
D:\code\rust\hello-rust>rustup toolchain --help
rustup-toolchain
Modify or query the installed toolchains

USAGE:
    rustup toolchain <SUBCOMMAND>

FLAGS:
    -h, --help    Prints help information

SUBCOMMANDS:
    list         List installed toolchains
    install      Install or update a given toolchain
    uninstall    Uninstall a toolchain
    link         Create a custom toolchain by symlinking to a directory
    help         Prints this message or the help of the given subcommand(s)

DISCUSSION:
    Many `rustup` commands deal with *toolchains*, a single
    installation of the Rust compiler. `rustup` supports multiple
    types of toolchains. The most basic track the official release
    channels: 'stable', 'beta' and 'nightly'; but `rustup` can also
    install toolchains from the official archives, for alternate host
    platforms, and from local builds.

    Standard release channel toolchain names have the following form:

        <channel>[-<date>][-<host>]

        <channel>       = stable|beta|nightly|<version>
        <date>          = YYYY-MM-DD
        <host>          = <target-triple>

    'channel' is either a named release channel or an explicit version
    number, such as '1.42.0'. Channel names can be optionally appended
    with an archive date, as in 'nightly-2017-05-09', in which case
    the toolchain is downloaded from the archive for that date.

    The host may be specified as a target triple. This is most useful
    for installing a 32-bit compiler on a 64-bit platform, or for
    installing the [MSVC-based toolchain] on Windows. For example:

        $ rustup toolchain install stable-x86_64-pc-windows-msvc

    For convenience, omitted elements of the target triple will be
    inferred, so the above could be written:

        $ rustup toolchain install stable-msvc

    The `rustup default` command may be used to both install and set
    the desired toolchain as default in a single command:

        $ rustup default stable-msvc

    rustup can also manage symlinked local toolchain builds, which are
    often used for developing Rust itself. For more information see
    `rustup toolchain help link`.

D:\code\rust\hello-rust>
D:\code\rust\hello-rust>rustup update
info: syncing channel updates for 'stable-i686-pc-windows-msvc'
info: latest update on 2021-02-11, rust version 1.50.0 (cb75ad5db 2021-02-10)
info: downloading component 'rust-std' for 'x86_64-pc-windows-msvc'
 20.9 MiB /  20.9 MiB (100 %)   7.9 MiB/s in  7s ETA:  0s
info: downloading component 'cargo'
  3.4 MiB /   3.4 MiB (100 %)   1.2 MiB/s in  2s ETA:  0s
info: downloading component 'clippy'
info: downloading component 'rust-docs'
 14.6 MiB /  14.6 MiB (100 %)   4.9 MiB/s in  3s ETA:  0s
info: downloading component 'rust-std'
 20.8 MiB /  20.8 MiB (100 %)   6.6 MiB/s in  4s ETA:  0s
info: downloading component 'rustc'
 51.7 MiB /  51.7 MiB (100 %)   9.4 MiB/s in  7s ETA:  0s
info: downloading component 'rustfmt'
  1.9 MiB /   1.9 MiB (100 %)   1.1 MiB/s in  2s ETA:  0s
info: removing previous version of component 'rust-std' for 'x86_64-pc-windows-msvc'
info: removing previous version of component 'cargo'
info: removing previous version of component 'clippy'
info: removing previous version of component 'rust-docs'
info: removing previous version of component 'rust-std'
info: removing previous version of component 'rustc'
info: removing previous version of component 'rustfmt'
info: installing component 'rust-std' for 'x86_64-pc-windows-msvc'
info: Defaulting to 500.0 MiB unpack ram
 20.9 MiB /  20.9 MiB (100 %)  11.3 MiB/s in 57s ETA:  0s
info: installing component 'cargo'
info: installing component 'clippy'
info: installing component 'rust-docs'
 14.6 MiB /  14.6 MiB (100 %)   1.1 MiB/s in 27s ETA:  0s
info: installing component 'rust-std'
 20.8 MiB /  20.8 MiB (100 %)  12.4 MiB/s in  1m 55s ETA:  0s
info: installing component 'rustc'
 51.7 MiB /  51.7 MiB (100 %)  12.5 MiB/s in  4s ETA:  0s
info: installing component 'rustfmt'
info: syncing channel updates for 'stable-x86_64-pc-windows-msvc'
info: latest update on 2021-02-11, rust version 1.50.0 (cb75ad5db 2021-02-10)
info: downloading component 'rust-src'
info: downloading component 'cargo'
info: downloading component 'clippy'
info: downloading component 'rust-docs'
 14.6 MiB /  14.6 MiB (100 %)   9.2 MiB/s in  2s ETA:  0s
info: downloading component 'rust-std'
 20.9 MiB /  20.9 MiB (100 %)   9.9 MiB/s in  2s ETA:  0s
info: downloading component 'rustc'
 52.1 MiB /  52.1 MiB (100 %)   9.7 MiB/s in  6s ETA:  0s
info: downloading component 'rustfmt'
info: removing previous version of component 'rust-src'
info: removing previous version of component 'cargo'
info: removing previous version of component 'clippy'
info: removing previous version of component 'rust-docs'
info: removing previous version of component 'rust-std'
info: removing previous version of component 'rustc'
info: removing previous version of component 'rustfmt'
info: installing component 'rust-src'
info: installing component 'cargo'
info: installing component 'clippy'
info: installing component 'rust-docs'
 14.6 MiB /  14.6 MiB (100 %)   1.9 MiB/s in 22s ETA:  0s
info: installing component 'rust-std'
 20.9 MiB /  20.9 MiB (100 %)  11.5 MiB/s in  1m  2s ETA:  0s
info: installing component 'rustc'
 52.1 MiB /  52.1 MiB (100 %)  13.1 MiB/s in  4s ETA:  0s
info: installing component 'rustfmt'
info: checking for self-updates
info: downloading self-update

    stable-i686-pc-windows-msvc updated - rustc 1.50.0 (cb75ad5db 2021-02-10) (from rustc 1.50.0 (cb75ad5db 2021-02-10))
  stable-x86_64-pc-windows-msvc updated - rustc 1.50.0 (cb75ad5db 2021-02-10) (from rustc 1.48.0 (7eac88abb 2020-11-16))

info: cleaning up downloads & tmp directories

D:\code\rust\hello-rust>

