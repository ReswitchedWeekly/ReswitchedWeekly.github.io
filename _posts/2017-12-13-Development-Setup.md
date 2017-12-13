---
layout: post
category
title: Setup Development
---
This is an example of what it takes to setup up a reswitched development environment.

## Requirements

These are universal requirements needed for everything.
- Recommended Linux or WSL
- LLVM and Clang Version 5 or higher.
Most likely or package manager is not up to date.
    - Arch is on version 5
    - Debian and Ubuntu are not.
        - You need to add the [official llvm apt](https://apt.llvm.org/)
        - I recommend setting llvm-5 and clang-5 as default but it isn't necessary.
- Python2 and Pip2

## Mephisto

### Setup
```
#May require sudo
pip2 install -r requirements.txt
#end sudo
git clone https://github.com/reswitched/unicorn.git
cd unicorn
UNICORN_ARCHS="aarch64" ./make.sh
sudo ./make.sh install
```
### Install
```
git clone https://github.com/reswitched/Mephisto.git
cd Mephisto
make
```
You might want to add ctu to your PATH.

## Libtransistor

### Setup
```
#May require sudo
pip2 install -r requirements.txt
#end sudo
```
### Install

```
git clone https://github.com/reswitched/libtransistor.git
cd libtransistor
make
```
If your default LLVM and Clang are below 5.0
run make like this. (i.e Ubuntu and Debian with the apt repo)
`make LLVM_POSTFIX=-5.0`
You also might want to set $LIBTRANSISTOR_HOME to the folder.

## Where to go from here:
This section will be filled with docs and tutorials as they are released.

### Last Updated: 12/12/2017 MM/DD/YYY