# Embedded-segger-debug
Writing this so that it helps other.
I didn't able to figure out the cause of the issue. I found a work around, that working for me all the time. I also was hoping to automate the downloading of bootloader, soft device, setting and app all together by embedded segger studio, now I can do that.
Here are the steps;
click on project -> option -> User build step -> Post-Build Command and add the following line.
nrfutil settings generate --family NRF52 --application Output/Debug/Exe/ble_app_buttonless_dfu_pca10040_s132.hex --application-version 0 --bootloader-version 0 --bl-settings-version 1 Output/Debug/Exe/setting.hex 
click on Loader -> Additional Load File[0] choose your soft device
click on Additional Load File[1] choose your bootloader.hex
click on Additional Load File[2] choose your setting.hex
That's all, enjoy your debug session.
