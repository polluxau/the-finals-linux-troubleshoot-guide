![image](https://github.com/user-attachments/assets/fd82225b-33fb-4dda-83a5-9f062cd51ae2)
![tux small](https://github.com/user-attachments/assets/5cec50e6-407c-4e91-b828-ba6c30355dcd)



--------------------------------------
![nvlogo_white-1538839930](https://github.com/user-attachments/assets/5e0ce5f1-d399-4262-a72f-994a55811854)


If your on Nvidia please use the Nvidia driver that is provided by your Distro

If your on a Wayland Desktop like KDE Plasma, Gnome, Cosmic, Lxqt, Budgie please use the latest nvidia driver like 555 or 560 or newer

--------------------------------------
![amd-logo-white-png-5773-1024x245-601490339](https://github.com/user-attachments/assets/57cea371-7a50-4b67-9d80-5b9457826bc9)


On AMD you have the AMDGPU driver in the Linux kernel and RADV in MESA which is the userspace driver, please use atleast kernel 6.8 or higher and mesa 23.1 or higher

if you are using a newer Distro like Fedora, Arch, Opensuse tumbleweed, Bazzite, Fedora kinote, Fedora silverblue, Nixos, Fedora workstation or even Gentoo make sure you are using 6.10.9 or above

The reason for kernel 6.10.9 is because of a recent regression that caused lots of games to have a decent amount of frame spikes under a amd gpu including THE FINALS
https://www.phoronix.com/news/Linux-6.11-rc7-AMDGPU-Fix

-----------------------------------
![image](https://github.com/user-attachments/assets/7401c332-fd00-416b-9428-b11cf9b0738c)


Intel, use the latest kernel and MESA aswell, Intel uses the i915 driver right now in the kernel and ANV in mesa, Intel is currently reworking their driver in the kernel called the Intel-XE driver and are improving ANV in mesa for gaming, i dont own a intel gpu so its hard for me to test if the finals works properly or not

-----------------------------------


![1922724614id24077gol](https://github.com/user-attachments/assets/ce86fddd-3424-4333-91c4-d0cfe301803a)



**PROTON**

Please use Proton experimental, experimental has all of the latest patches from valve for THE FINALS, do NOT use bleeding edge

--------------------------------------


**YOU CAN ALSO USE PROTON-GE BUT IT ISN'T REQUIRED**

Proton-ge uses experimental(bleeding edge) and gets updated every couple of weeks with its own patches included like video codecs and specific fixes that valve can not do because of licenses or other issues 

https://github.com/GloriousEggroll/proton-ge-custom

-----------------------------------

**YOU CAN USE A APPLICATION LIKE PROTONPLUS OR PROTON-UP-QT TO GET PROTON-GE INSTALLED ON STEAM**

https://flathub.org/apps/com.vysp3r.ProtonPlus

https://flathub.org/apps/net.davidotek.pupgui2

--------------------------------------

**IF YOUR GAME CRASHES AFTER A HOUR OR SO**

This usually indicates that your vm.max map_count is too low on the linux distro you are running, what is vm max map count?

vm.max_map_count is a kernel parameter in Linux that limits the maximum number of memory mappings (also known as virtual memory areas or VMA) a process can have. This parameter is used to prevent excessive memory fragmentation and potential denial-of-service attacks.
What is a memory mapping?
A memory mapping is a region of virtual memory that is mapped to a physical memory page or a file

Distros like linux mint 21, ubuntu 22.04, debian 12 will have too low of a value, so the game will crash as it tries to create more virtual memory in the game

------------------------------------

**HOW TO INCREASE IT**

To increase your vm.max_map_count do this 

Open your terminal

sudo nano /etc/sysctl.d/vm.max_map_count.conf

Add this value to this config 

vm.max_map_count=2147483642

Ctrl-x, y, enter to save the file

Reboot your system

--------------------------------------

**IF YOUR GAME STOPS WORKING**

If the game for some reason stops working please clear your wine prefix, your wine prefix is the fake windows directory that proton uses, so when you clear it, the components it uses will be removed requiring the game to redo the setup instructions/recreate that wine prefix so it's clean to use

**THIS MAY RESET YOUR IN-GAME SETTINGS SO PLEASE REMEMBER WHAT YOU HAD BEFOREHAND!**

**HOW TO CLEAR YOUR WINE PREFIX**

Each game has its own prefix that steam will create under /steamlibrary/compatdata

If your game is on the main drive then enable hidden files in your file manager and you'll find .steam 

Go to your steamlibrary and right click on the finals, properties, updates, and find the APPID for THE FINALS, yours will be different to mine

![image](https://github.com/user-attachments/assets/8456b6a2-4005-451a-811e-426db77b9694)

Then go to the steamlibrary where you have the finals installed and go to compatdata, find the folder that has the same appid as THE FINALS

![image](https://github.com/user-attachments/assets/776e90f7-53b8-4ba9-be16-b6a2fa9c5a2a)

Delete that prefix and verify the game in steam

Use experimental and should be good to go

---------------------------------------

**EAC PROBLEMS**

If you get any EAC problems please try clearing the prefix first then if you get the same issue use this launch command for the finals

`PROTON_USE_EAC_LINUX=1 %command%`

![image](https://github.com/user-attachments/assets/fe7447fb-1840-4889-a2f2-34ededeaebc0)


**EAC LANGUAGE ISSUE**

For some reason EAC wont launch if your running a language like ar_sa(Arabic), ja_ja(Japanese), ko_kr(Korean), th_th(Thai), tr_tr(Turkish), zh_cn(Simplified Chinese), zh_tw(Traditional Chinese) so you have to manually add these fonts into the wine prefix of THE FINALS so EAC can launch properly

`<SteamLibrary-folder>/steamapps/compatdata/2073850/pfx/drive_c/windows/Fonts`

If you look in The Finals/EasyAntiCheat/Localization and open a .cfg like ko_kr.cfg you will see the fonts its looking for like Malgunsl.ttf or Malgun.ttf, so just search these up online and download them, then place it in the fonts folder in the prefix so the language can work with EAC 

![image](https://github.com/user-attachments/assets/0a9d23ef-eb8a-4960-b3d5-97e8ebbaa78e)



---------------------------------------

**IF YOU HAVE A MEMORY LEAK**

If you are getting a memory leak in the finals after a while like 3 hours or so, please try flatpak steam, this has seemed to have solved the issue for me but this leak may still be present if your on a arch based system it seems

Also another fix might be that you dont have zram or "swap" we like to call it, enabled on your linux distro, please look up how to do this for your linux distro that you are using 

**IF YOU HAVE FURTHER PROBLEMS **

Please go to the proton github THE FINALS issue page and report your problem

You can also do `PROTON_LOG=1 %command%` as your launch command for the finals to get a log of the game, this log will be in your home directory, which you can then upload to your github comment explaining the problem you are having

https://github.com/ValveSoftware/Proton/issues/7317

---------------------------------------


**IF THE GAME BREAKS FROM A UPDATE PLEASE TRY CLEARING THE PREFIX, IF THAT DOESNT WORK TRY BLEEDING EDGE BUILD OF PROTON**

**WARNING THIS CAN OVERTIME DESTROY YOUR WINE PREFIX SO PLEASE USE WITH CAUTION**

Find experimental in your steam library

![image](https://github.com/user-attachments/assets/69d9cbdf-9655-4849-bf17-02d88c17214a)

Proprieties on experimental and go to beta, select bleeding edge, latest untested dxvk and vkd3d, update and force compatibility on the finals to use experimental(bleeding edge)

![image](https://github.com/user-attachments/assets/e4ce2cf9-e286-4f3a-aa06-6438fd0a966e)

![image](https://github.com/user-attachments/assets/80c1f38b-c055-49ec-9761-86761972a1b7)

If it works have fun in the arena! 

Nama Tama Love's you 

![image](https://github.com/user-attachments/assets/3cc6a3e7-5276-4643-a0ae-366009daf791)



