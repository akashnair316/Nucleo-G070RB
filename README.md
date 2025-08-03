# Nucleo-G070RB
## Installation Packages
```
sudo apt install --no-install-recommends git cmake ninja-build gperf ccache dfu-util device-tree-compiler wget python3-dev python3-venv python3-tk xz-utils file make gcc gcc-multilib g++-multilib libsdl2-dev libmagic1
```


## First Time setup
```
python3 -m venv /home/akash/Projects/github/Nucleo-G070RB/zephyrproject/.venv
source /home/akash/Projects/github/Nucleo-G070RB/zephyrproject/.venv/bin/activate
pip install west

west init /home/akash/Projects/github/Nucleo-G070RB/zephyrproject
cd /home/akash/Projects/github/Nucleo-G070RB/zephyrproject
west update
west zephyr-export
west packages pip --install

cd /home/akash/Projects/github/Nucleo-G070RB/zephyrproject/zephyr
west sdk install

west build -b nucleo_g070rb samples/basic/blinky
```
## After setup, only build
```
source /home/akash/Projects/github/Nucleo-G070RB/zephyrproject/.venv/bin/activate
cd /home/akash/Projects/github/Nucleo-G070RB/zephyrproject/zephyr
west build -b nucleo_g070rb samples/basic/blinky
```
## Flashing
# Use anyone of this, mostly openocd works
```
west flash --runner openocd
west flash --runner jlink
west flash --runner pyocd
```

## To check if a board supports zephyr or not
https://docs.zephyrproject.org/latest/boards/index.html#boards=&arch=arm64&vendor=st&soc=stm32g070xx

## Board porting guide
https://docs.zephyrproject.org/latest/hardware/porting/board_porting.html#board-porting-guide

## Official documentation for Nucleo G070RB board
https://docs.zephyrproject.org/latest/boards/st/nucleo_g070rb/doc/index.html
