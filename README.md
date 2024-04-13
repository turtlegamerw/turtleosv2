# turtleosv2
so you need to run a few commands to make it work


cargo rustc -- -C link-arg=-nostartfiles
rustup override set nightly
rustup component add llvm-tools-preview
rustup target add thumbv7em-none-eabihf
cargo build --target thumbv7em-none-eabihf
cargo install bootimage
cargo bootimage

and run it using qemu
qemu-system-x86_64 -drive format=raw,file=bootimage-turtle_osv2.bin
(its in target/x86_64-turtle_osv2/debug/bootimage-turtle_osv2.bin)
