---
layout: post
category
title: Setup Development
---
This is an example of what it takes to setup up a reswitched development environment.

## Requirements

- Linux or WSL is recommended.
- LLVM and Clang Version 5 or higher.
    - Arch Linux has recent enough versions of LLVM and Clang
    - Debian and Ubuntu do not.
        - You will need to add the [official llvm apt](https://apt.llvm.org/)
        - I recommend setting llvm-5 and clang-5 as default, but it isn't necessary.
    - Fedora is also not up to date.
        - You can download prebuilt binaries from the llvm website or build it yourself.
- Python2 and Pip2

## Mephisto
Mephisto recently got a dockerfile.
For information on that check the readme.
### Build Unicorn
```
git clone https://github.com/reswitched/unicorn.git
cd unicorn
sudo pip2 install -r requirements.txt
UNICORN_QEMU_FLAGS="--python=python2" UNICORN_ARCHS="aarch64" ./make.sh
sudo ./make.sh install
```
### Build Mephisto

```
git clone https://github.com/reswitched/Mephisto.git
cd Mephisto
make
```
If your default LLVM and Clang are below 5.0
run make like this. (i.e Ubuntu and Debian with the apt repo)
```
make LLVM_POSTFIX=-5.0
```
You might want to add ctu to your PATH.

## Libtransistor

### Build Libtransistor
```
git clone https://github.com/reswitched/libtransistor.git
cd libtransistor
sudo pip2 install -r requirements.txt
make
```
If your default LLVM and Clang are below 5.0
run make like this. (i.e Ubuntu and Debian with the apt repo)
```
make LLVM_POSTFIX=-5.0
```
You also might want to set `$LIBTRANSISTOR_HOME` to the folder where you cloned libtransistor.

### Run Libtransistor Tests Under Mephisto
```
make MEPHISTO=path/to/Mephisto/ctu run_tests
```

## Where to go from here:
This section will be filled with docs and tutorials as they are released.

### Last Updated: 2017/12/13 YYYY/MM/DD
