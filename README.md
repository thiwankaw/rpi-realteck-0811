# rpi-realteck-0811


goto https://github.com/morrownr/8821au-20210708?tab=readme-ov-file


install below packages

sudo apt install -y raspberrypi-kernel-headers build-essential bc dkms git


clone the repo

git clone https://github.com/morrownr/8821au-20210708.git

run install

cd 8821au-20210708
sudo ./install-driver.sh


edit /etc/wpa_supplicant/wpa_supplicant.conf as below


ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=LK

network={
ssid="SLT-4G_C5C67"
key_mgmt=WPA-PSK
psk="yourpassword"
}

below commands may be useful

wpa_cli  -i wlan0 reconfigure
ifconfig wlan0
iwconfig
ifconfig  wlan0 up
service networking restart
systemctl  restart wpa_supplicant
wpa_supplicant -B -i wlan0 -c /etc/wpa_supplicant/wpa_supplicant.conf




