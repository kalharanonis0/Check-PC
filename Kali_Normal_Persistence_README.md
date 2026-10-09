# Kali Linux Live USB --- Normal Persistence Setup (Without LUKS)

මෙම README එක Kali Linux Live USB එකකට **encrypted නොවන (Normal)
Persistence** සකස් කිරීම සඳහාය. Persistence මඟින් files සහ settings restart
කළාට පසුවත් තබාගැනීමට උදව් වේ.

> **වැදගත් ආරක්ෂක අවවාද**
>
> -   මේ පියවරවලදී partition එකක් format කිරීමෙන් එහි තිබෙන දත්ත මැකෙයි.
> -   `/dev/sda` හෝ `/dev/sda3` හැම පරිගණකයකම USB එක නොවේ. Device names
>     වෙනස් විය හැකියි.
> -   Commands ධාවනය කිරීමට පෙර USB එකේ නම සහ අලුත් partition එක නිවැරදි බව
>     නැවත පරීක්ෂා කරන්න.
> -   දැනට තිබෙන Live USB partitions (`sda1`, `sda2` වැනි) delete හෝ
>     format කරන්න එපා.
> -   LUKS encryption භාවිතා නොකරන නිසා persistence partition එකේ දත්ත
>     encrypted නොවේ.

## 1. Terminal එක විවෘත කරන්න

Kali Linux Live USB එකෙන් boot කර Terminal එක විවෘත කරන්න.

## 2. Disk එක සහ partitions හඳුනාගන්න

``` bash
lsblk -o NAME,SIZE,TYPE,FSTYPE,MOUNTPOINTS,MODEL
```

වැඩි විස්තර සඳහා:

``` bash
sudo fdisk -l
```

USB එකේ device name එක, capacity එක සහ partitions පරීක්ෂා කරන්න. මෙම
උදාහරණයේ `/dev/sda` යනු USB එක සහ `/dev/sda3` යනු අලුතින් සාදන persistence
partition එක ලෙස සලකනවා. **ඔබේ පරිගණකයේ නම වෙනස් නම් commands වල device
name එක ඒ අනුව වෙනස් කරන්න.**

## 3. USB එකේ free space පරීක්ෂා කරන්න

``` bash
sudo parted /dev/sdX unit MiB print free
```

`/dev/sdX` වෙනුවට USB device එකේ නිවැරදි නම යොදන්න. උදාහරණයක් ලෙස USB එක
`/dev/sda` නම් `/dev/sda` යොදන්න.

Free space එක ඇති බවත්, එය USB එකේ බවත් තහවුරු කරන්න. Disklabel type එක `dos`
හෝ `gpt` විය හැකියි.

## 4. Free space එකේ අලුත් partition එකක් සාදන්න

Partition එකක් සෑදීමෙන් USB partition table එක වෙනස් වෙනවා. දැනට තිබෙන
partitions මකා නොදමන්න.

``` bash
sudo fdisk /dev/sdX
```

`/dev/sdX` වෙනුවට නිවැරදි USB device එක යොදන්න. `fdisk` තුළ:

1.  `p` --- දැනට තිබෙන partition table එක පරීක්ෂා කරන්න.
2.  `n` --- අලුත් partition එකක් සාදන්න.
3.  Partition number එකක් අසන විට, භාවිතා නොවන ඊළඟ number එක තෝරන්න.
4.  First sector සහ last sector සඳහා free space භාවිතා කිරීමට අවශ්‍ය අගයන්
    තෝරන්න. Default අගයන් භාවිතා කිරීමට පෙර ඒවා free space තුළ බව තහවුරු කරන්න.
5.  `p` භාවිතයෙන් නව partition එක සහ දැනට තිබෙන partitions සියල්ල පරීක්ෂා කරන්න.
6.  සියල්ල නිවැරදි නම් පමණක් `w` ටයිප් කර වෙනස්කම් ලියන්න. සැකයක් තිබේ නම් `w` නොදී ඉවත්
    වන්න.

> Partition number එක අනිවාර්යයෙන් `3` විය යුතු නැහැ. USB layout එක අනුව වෙනස්
> විය හැකියි.

Kernel එකට partition table එක නැවත කියවීමට:

``` bash
sudo partprobe /dev/sdX
lsblk /dev/sdX
```

අලුත් partition එක හඳුනාගෙන තිබෙන බව තහවුරු කරන්න.

## 5. අලුත් partition එක ext4 ලෙස format කරන්න

පහත command එකේ `/dev/sdX3` වෙනුවට ඔබ අලුතින් සාදාගත් partition එකේ නම යොදන්න.

``` bash
sudo mkfs.ext4 -L persistence /dev/sdX3
```

**මෙය තෝරාගත් partition එකේ දත්ත මකන ක්‍රියාවකි.** USB එකේ අලුතින් සාදපු
persistence partition එක බව 100% තහවුරු නොකර run කරන්න එපා.

## 6. Persistence configuration file එක සාදන්න

පහත commands වල `/dev/sdX3` වෙනුවට ඔබේ persistence partition එකේ නිවැරදි නම
යොදන්න.

``` bash
sudo mkdir -p /mnt/my_usb
sudo mount /dev/sdX3 /mnt/my_usb
echo "/ union" | sudo tee /mnt/my_usb/persistence.conf
cat /mnt/my_usb/persistence.conf
```

අවසාන command එකේ output එක මෙසේ විය යුතුයි:

``` text
/ union
```

ඉන්පසු unmount කරන්න:

``` bash
sudo umount /mnt/my_usb
```

## 7. Persistence mode එකෙන් boot කරන්න

1.  Kali Live USB එක restart කරන්න.
2.  Boot menu එකේ `Live USB Persistence` හෝ ඒ හා සමාන persistence විකල්පයක්
    තිබේ නම් එය තෝරන්න. නම Kali image/version එක අනුව වෙනස් විය හැකියි.
3.  Kali ආරම්භ වූ පසු Terminal එක විවෘත කරන්න.

## 8. Persistence වැඩ කරනවාද පරීක්ෂා කරන්න

Test file එකක් සාදන්න:

``` bash
echo "persistence-test" > ~/persistence-test.txt
cat ~/persistence-test.txt
```

`persistence-test` පෙන්වන බව බලන්න. පසුව persistence mode එකෙන් restart කර
නැවත boot කරන්න. ඊට පස්සේ:

``` bash
cat ~/persistence-test.txt
```

ගොනුව සහ එහි අන්තර්ගතය තිබේ නම් persistence ක්‍රියා කරන බවට ලකුණකි.

## 9. ගැටලුවක් තිබේ නම්

-   Persistence boot option එක නොපෙනේ නම්, භාවිතා කරන Kali Live image එකේ
    boot menu සහ persistence support එක පරීක්ෂා කරන්න.
-   ගොනුව restart පසු නැති නම්, persistence mode එකෙන්ම boot වූවාද සහ
    `persistence.conf` එකේ අන්තර්ගතය හරියට `/ union` ද යන්න පරීක්ෂා කරන්න.
-   Partition name එක ගැන සැකයක් තිබේ නම්, format command එක ධාවනය නොකර
    `lsblk` output එක පරීක්ෂා කරන්න.
-   මෙය Kali Live USB එක සඳහා වන ක්‍රමයකි; වෙනත් Linux distributions වල boot
    option සහ persistence සැකසුම් වෙනස් විය හැකියි.

## Reference

Kali Linux documentation --- Adding Encrypted Persistence to a Kali
Linux Live USB Drive:\
https://www.kali.org/docs/usb/usb-persistence-encryption/

මෙම README එක encrypted persistence නොව **Normal Persistence** සඳහා සකස්
කර ඇත. Kali නිල ලිපියේ encryption සම්බන්ධ පියවර මෙහි භාවිතා කර නැත.
