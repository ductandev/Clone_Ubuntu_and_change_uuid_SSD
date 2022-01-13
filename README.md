# Clone_Ubuntu_and_change_uuid_SSD

1. Dowload ventoy \
https://github.com/ventoy/Ventoy/releases chọn như hình rồi tải xuống cho linux
![image](https://user-images.githubusercontent.com/42485856/147914248-af43119d-e47f-459f-861a-17eddf48df97.png)

2. giải nén thư mục ventoy vừa tải về và vào thư mục 
Xem kỹ ổ đó dạng gì, sda, sdb, sdc
```
cd /Downloads/ventoy-1.0.63-linux/ventoy-1.0.63 
sudo ./Ventoy2Disk.sh -i /dev/sdb
y
y
```
3. tải clonezilla https://clonezilla.org/downloads/download.php?branch=stable chọn loại file iso và tải
```
cd 
sudo nautilus
copy file clonezela.iso trong thư mục dowload vào ổ đĩa ventoy vào ổ đĩa
```


# Đổi UUID cho ổ cứng
```
umount /dev/sdc5  
sudo -s
sudo e2fsck -f /dev/sdb5
sudo tune2fs -U random /dev/sdb5
```

- lệnh trên để đổi UUID ổ cứng ---> sau đó rút ổ cứng ra và cắm vào lại, rồi vào ổ 31GB chọn vào /etc/fstab đổi UUID ---> sau đó tiếp tục vào rồi vào /boot/grub/grub.cfg đổi UUID là xong
