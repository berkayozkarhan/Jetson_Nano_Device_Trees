### What?
This repo contains device trees that can be used for the jetson nano 2gb development kit. Normally, the sudo /opt/nvidia/jetson/jetson-io.py command is used to configure the pins on the nano carrier board to use their special functions, but some modules of jetson nano can get users into really dirty work in this regard. You can avoid this dirty work by placing the .dtb files from this repo in the correct directories on your development board (Jetson Nano 2 GB Developer Kit).
When I first did this job, I didn't know much, so I went through a difficult process for this process, but in the end, I did the right thing and went to the device tree update process. There is also an .img file that contains this device tree file and can be configured with 40 pin headers, but you can create your own file by following the links below.

- https://docs.nvidia.com/jetson/l4t/index.html#page/Tegra%20Linux%20Driver%20Package%20Development%20Guide/adaptation_and_bringup_nano.html#wwpID0E0AQ0HA

- https://docs.nvidia.com/jetson/l4t/index.html#page/Tegra%20Linux%20Driver%20Package%20Development%20Guide/flashing.html#wwpID0E0CM0HA


### Pin Functions Enabled

Using the img files in img_files, you can flash the Balena Etcher program or other ways to your sd card and use the functions in the 40 pin header. In the forums, they have made different explanations for the jetson-io.py file that cannot be opened, but the solution that takes care of the situations such as the file not opening, giving an error or flashing it will be to update the device tree in the operating system. In some explanation "sudo find /opt/nvidia/jetson-io/ -mindepth 1 -maxdepth 1 -type d -exec touch {}/__init__.py \;" After the command, I write operations such as the jetson-io.py file becomes openable and you move your dtb file to the /boot/dtb file. 

### Usage

After flashing created img files to your sd card, the jetson-io.py configuration file can also be used without any problems.

After flashing the sd card, do not forget to run the command below to see the spi device as /dev/spi* in your /dev directory.


> sudo modprobe spidev
