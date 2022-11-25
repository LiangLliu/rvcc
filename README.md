# rvcc

本项目学习[B站课程](https://www.bilibili.com/video/BV1gY4y1E7Ue)，@sunshaoce和@ksco将其由原来的X86架构改写为RISC-V
64架构，同时加入了大量的中文注释，并且配有316节对应于每一个commit的课程，帮助读者可以层层推进、逐步深入的学习编译器的构造。

## rvcc课程资料

* rvcc课程材料： https://github.com/sunshaoce/rvcc-course
* rvcc参考 https://github.com/sunshaoce/rvcc

## RISC-V介绍

RISC-V是一个开源的精简指令集，相较于常见的X86、ARM架构，其简单易学，并且发展迅猛。现在已经出现了支持RISC-V的各类设备，未来还将出现RISC-V架构的笔记本电脑，可谓是前景一片光明。

## Build & Run

* 编译汇编代码

```bash
riscv64-unknown-linux-gnu-gcc -static tmp.s -o tmp
```

* qemu模拟

```bash
qemu-riscv64 -L $RISCV/sysroot tmp

# 取控制台值
echo $?
```

* Makefile

```bash
make rvcc
make test
make clean
```

* CMake

```bash
# CMakeLists.txt
cmake -Bbuild .
cd build
make

# 删除无用的build文件
rm -rf build/
```