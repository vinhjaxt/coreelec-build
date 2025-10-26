# coreelec-build
[coreelec] build img

# Steps
```sh
git clone --single-branch --depth=1 --recurse-submodules -b coreelec-22 https://github.com/CoreELEC/CoreELEC
docker run --name coreelec -d -v ./CoreELEC:/CoreELEC:rw -w /CoreELEC --network host ubuntu:25.04 sleep infinity
docker exec -it coreelec bash
useradd user
mkdir /home/user
chown user:user /home/user /CoreELEC -R

apt install -y sudo visudo nano vim cpio rsync
apt install -y make gcc git python3 xfonts-utils rdfind libparse-yapp-perl gperf xsltproc libxml-parser-perl patchutils lzop

# Optional: modify kernel config at /CoreELEC/projects/Amlogic-ce/devices/Amlogic-no/linux/linux.aarch64.conf
DEVICE=Amlogic-no ARCH=aarch64 make image

ls target/
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Alta.img.gz
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Alta.img.gz.sha256
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Generic.img.gz
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Generic.img.gz.sha256
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Khadas_VIM1S.img.gz
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Khadas_VIM1S.img.gz.sha256
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Khadas_VIM4.img.gz
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Khadas_VIM4.img.gz.sha256
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Odroid_C4.img.gz
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Odroid_C4.img.gz.sha256
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Odroid_C5.img.gz
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Odroid_C5.img.gz.sha256
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Odroid_N2.img.gz
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Odroid_N2.img.gz.sha256
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Radxa_Zero.img.gz
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Radxa_Zero.img.gz.sha256
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Radxa_Zero2.img.gz
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Radxa_Zero2.img.gz.sha256
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Solitude.img.gz
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606-Solitude.img.gz.sha256
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606.kernel
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606.system
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606.tar
CoreELEC-Amlogic-no.aarch64-22.0-Piers_devel_20251025204606.tar.sha256
```
