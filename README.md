# Helloworld project of Pixar USD in C++
## Introduction
I hope to develop a conversion tool with pixar usd for our own DCC software [zeno](https://github.com/zenustech/zeno). After learning the [tutorial officially provided by usd](https://graphics.pixar.com/usd/release/tut_usd_tutorials.html#), I hope to start a c++ usd project. However, there is a lack of c++ usd resources on the network, and even running a helloworld is very difficult. I provide the helloworld project I obtained after practice here, so that the required usd learners can use it.

## Pre-requriements
Install pixar usd properly, follow [the official build instructions](https://github.com/PixarAnimationStudios/USD#3-run-the-script).

Add environment variable. Example in Linux with zsh:
```shell
echo "export USD_INSTALL_ROOT=/usr/local/USD" >> ~/.zshrc
```
`/usr/local/USD` is my USD install directory, make sure it matches yours.

## Edit cmake file
We need to link a lib names `libboost_python.so`, but the name of this lib rely on the python version runs the USD install script. In my system, it names `libboost_python38.so`, You can use this command to find out the name of this lib.
```shell
ls /usr/local/USD/lib | grep 'libboost_python'
```
Modify `CMakeLists.txt` line 28 to make sure the lib's name matches yours.

## Have fun
Now you can start your c++ usd project.
You can directly compile and run exist program in this repo.
```shell
cmake -B build
cmake --build build
cd build && ./run_it
usdview helloworld.usda
```

## references
[Pixar USD official website](https://graphics.pixar.com/usd/)

[USD Cookbook](https://github.com/ColinKennedy/USD-Cookbook)
