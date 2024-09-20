![image](https://github.com/user-attachments/assets/3487ffc1-5f38-4880-9254-3b79c67f2dd9) ![image](https://github.com/user-attachments/assets/8a177197-61d1-4797-9cb9-30592315ebb8) ![linux logo](https://github.com/user-attachments/assets/a58c8dc5-117b-4d04-998e-9f21407062d9)


**NVIDIA**

If your on nvidia please use the nvidia driver that is provided by your distro

If your on a wayland desktop like kde plasma or gnome, please use the latest nvidia driver like 555 or 560 or newer

**AMD**

On amd you have the amdgpu driver in the linux kernel and RADV in MESA which is the userspace driver, please use atleast kernel 6.10.9 or higher and mesa 24.1 or higher

The reason for kernel 6.10.9 is because of a recent regression that caused the finals to have a decent amount of frame spikes under a amd gpu
https://www.phoronix.com/news/Linux-6.11-rc7-AMDGPU-Fix

**IF YOU ARE ON A LTS DISTRO LIKE LINUX-MINT, UBUNTU LTS, ZORIN, PLEASE INSTALL A NEWER MESA**

https://launchpad.net/~kisak/+archive/ubuntu/kisak-mesa

**STEPS FOR INSTALLING KISAK MESA**

`sudo add-apt-repository ppa:kisak/kisak-mesa`

`sudo apt update`

**INTEL**

Intel, use the latest kernel and mesa aswell, intel uses the i915 driver right now in the kernel and ANV in mesa, intel is currently reworking their driver in the kernel called the Intel-XE driver and are improving ANV in mesa for gaming, i dont own a intel gpu so its hard for me to test if the finals works properly or not

**PROTON**

Please use proton experimental, experimental has all of the latest patches from valve for THE FINALS, you do not need bleeding edge unless the game breaks after a update

**HOW TO USE EXPERIMENTAL(BLEEDING EDGE) IF THE GAME BREAKS AFTER A UPDATE**

**WARNING THIS CAN OVERTIME DESTROY YOUR WINE PREFIX SO PLEASE USE WITH CAUTION**

Find experimental in your steam library

![image](https://github.com/user-attachments/assets/69d9cbdf-9655-4849-bf17-02d88c17214a)

Proprieties on experimental and go to beta, select bleeding edge, latest untested dxvk and vkd3d, update and force compatibility on the finals to use experimental(bleeding edge)

![image](https://github.com/user-attachments/assets/e4ce2cf9-e286-4f3a-aa06-6438fd0a966e)

![image](https://github.com/user-attachments/assets/80c1f38b-c055-49ec-9761-86761972a1b7)

**YOU CAN ALSO USE PROTON-GE BUT IT ISN'T REQUIRED**

proton-ge uses experimental(bleeding edge) and gets updated every couple of weeks with its own patches included like video codecs and specific fixes that valve can not do because of licenses or other issues 

https://github.com/GloriousEggroll/proton-ge-custom

**YOU CAN USE A APPLICATION LIKE PROTONPLUS OR PROTON-UP-QT TO GET PROTON-GE INSTALLED ON STEAM**

https://flathub.org/apps/com.vysp3r.ProtonPlus

https://flathub.org/apps/net.davidotek.pupgui2

If the game for some reason stops working please clear your wine prefix, your wine prefix is the fake windows directory that proton uses, so when you clear it, the components it uses will be removed requiring the game to redo the setup instructions/recreate that wine prefix so its a clean prefix to use

**THIS MAY RESET YOUR IN-GAME SETTINGS SO PLEASE REMEMBER WHAT YOU HAD BEFOREHAND!**

**HOW TO CLEAR YOUR WINE PREFIX**

Each game has its own prefix that steam will create under /steamlibrary/compatdata

Go to your steamlibrary and right click on the finals, properties, updates, and find the APPID for THE FINALS, yours will be different to mine

![image](https://github.com/user-attachments/assets/8456b6a2-4005-451a-811e-426db77b9694)

Then go to the steamlibrary where you have the finals installed and go to compatdata, find the folder that has the same appid as THE FINALS

![image](https://github.com/user-attachments/assets/776e90f7-53b8-4ba9-be16-b6a2fa9c5a2a)

Delete that prefix and verify the game in steam

Use experimental and should be good to go

**EAC PROBLEMS**

If you get any EAC problems please try clearing the prefix first then if you get the same issue use this launch command for the finals

`PROTON_USE_EAC_LINUX=1 %command%`

You can also add other environment variables behind %command% like mangohud or gamemoderun, make sure these tools are installed on your distro if you want to use them, it would look like this

`PROTON_USE_EAC_LINUX=1 mangohud gamemoderun %command%`

![image](https://github.com/user-attachments/assets/fe7447fb-1840-4889-a2f2-34ededeaebc0)

**IF YOU HAVE A MEMORY LEAK**

If you are getting a memory leak in the finals after a while like 3 hours or so, please try flatpak steam, this has seemed to have solved the issue for me but this leak may still be present if your on a arch based system it seems

**IF YOU HAVE FURTHER PROBLEMS **

Please go to the proton github THE FINALS issue page and report your problem

You can also do `PROTON_LOG=1 %command%` as your launch command for the finals to get a log of the game which you can then upload to your github comment explaining the problem you are having

https://github.com/ValveSoftware/Proton/issues/7317




