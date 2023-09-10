# WINDOWS 10 ON GITHUB CODESPACES FOR FREE

* BE SURE TO USE THE 4-CORES MACHINE TYPE
> https://github.com/codespaces/

## Install packages : qemu, dwm, aqemu, tigervnc
```bash
sudo apt update
sudo apt install qemu-kvm virtinst libvirt-clients bridge-utils libvirt-daemon-system tigervnc-standalone-server dwm aqemu -y
```

## Downloaad novnc
```bash
cd /
sudo git clone https://github.com/novnc/noVNC
```

## Download Disk image for windows 10
```bash
sudo wget -O /tmp/Tiny10_x64_HDA.img https://files.mollomm1.dev/api/public/dl/eHWIyWhJ
```

## Download VM config for windows 10
```bash
sudo mkdir -r /root/.aqemu
sudo wget -O /root/.aqemu/Tiny_10_x64.aqemu https://files.mollomm1.dev/api/public/dl/fCJ-7xlS
```

## launch aqemu, vncserver and novnc
```bash
sudo vncserver -SecurityType None -xstartup "dwm" -rfbport 5900 && sudo /noVNC/utils/novnc_proxy --vnc 127.0.0.1:5900 --listen localhost:6080
```

* after opening the novnc client do ALT+P then type **aqemu**
* Aqemu will warn you you are root user, just click **No** and ignore.
* In Find Qemu setup step be sure to click the search button, else it will break.

after setting up aqemu just start the Tiny 10 x64 vm

Admin password : Admin