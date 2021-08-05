# 製作Live USB隨身碟的軟體Unetbootin

必須將USB隨身碟格式化為FAT32的格式，製作完成的隨身碟才能開機。

//查看掛載點
$ fdisk -l 

假設裝置為
Device Boot Start End Sectors Size Id Type
/dev/sdb4 * 256 248348100 248347845 118.4G 7 HPFS/NTFS/exFAT

$ umount /dev/sdb4

//格式化為FAT32
$ mkfs -t vfat /dev/sdb4

go to https://unetbootin.github.io/ 點選下載Linux

//到下載檔案處執行即可製作開機隨身碟
sudo ./XXXXXX.bin

