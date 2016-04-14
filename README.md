# Atheros-Driver-Problem
Qualcomm Atheros Device 0042 (rev 30) 


###############################################################################################################

sudo apt-get install build-essential linux-headers-$(uname -r) git

echo "options ath10k_core skip_otp=y" | sudo tee /etc/modprobe.d/ath10k_core.conf

wget https://www.kernel.org/pub/linux/kernel/projects/backports/stable/v4.4.2/backports-4.4.2-1.tar.gz

tar -zxvf backports-4.4.2-1.tar.gz

cd backport-4.4.2-1

make defconfig-wifi

make

sudo make install

git clone https://github.com/kvalo/ath10k-firmware.git

sudo cp -r ath10k-firmware/QCA9377 /lib/firmware/ath10k/

sudo cp /lib/firmware/ath10k/QCA9377/hw1.0/firmware-5.bin_WLAN.TF.1.0-00267-1 /lib/firmware/ath10k/QCA9377/hw1.0/firmware-5.bin


###########################################################################################################
