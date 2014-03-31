# FileSystemChecker for CWM

As you can check your Android partitions only in recovery mode this update.zip should help you.

The script is based on http://forum.xda-developers.com/showthread.php?t=2165870

## Usage

Build the .zip file by zipping the `META-INF` folder up into `FileSystemChecker.zip`:

```
FileSystemChecker.zip
└─ META-INF
  └─ com
     └─ google
        └─ android
           └─ update-binary
```

1. copy the .zip to your phones storage: `adb push`
2. reboot into CWM recovery: `adb reboot recovery`
3. run the script install command to execute: `FileSystemChecker.zip`

Output should look like so:

```
Install from sdcard complete.

-- Installing: /storage/sdcard0/FileSytemChecker.zip
Finding update package...
I:Update location: /storage/sdcard0/FileSytemChecker.zip
Opening update package...
Installing update...


 + checking file system for /data:
   device: /dev/block/mmcblk0p10
   running e2fsck: /dev/block/mmcblk0p10: 21486/131072 files (9.0% non-contiguous), 405060/524288 blocks


 + checking file system for /system:
   device: /dev/block/mmcblk0p9
   running e2fsck: /dev/block/mmcblk0p9: 1736/32768 files (0.7% non-contiguous), 121493/131072 blocks

 + checking file system for /storage/sdcard0:
   device: /dev/block/vold/259:3
   running fsck_msdos:
    ** /dev/block/vold/259:3
    ** Phase 1 - Read FAT (compare skipped)
    Attempting to allocate 11761 KB for FAT
    ** Phase 2 - Check Cluster Chains
    ** Phase 3 - Checking Directories
    ** Phase 4 - Checking for Lost Files
    Lost cluster chain at cluster 48
    1 Cluster(s) lost
    Reconnect? yes
    Next free cluster in FSInfo block (48) not free
    Fix? yes
    14337 files, 1770520 free (442630 clusters)

    ***** FILE SYSTEM WAS MODIFIED *****


 + checking file system for /storage/sdcard1:
   device: /dev/block/vold/179:9
   running fsck_msdos:
    ** /dev/block/vold/179:9
    ** Phase 1 - Read FAT (compare skipped)
    Attempting to allocate 7480 KB for FAT
    ** Phase 2 - Check Cluster Chains
    ** Phase 3 - Checking Directories
    ** Phase 4 - Checking for Lost Files
    5121 files, 3180448 free (198778 clusters)

Finished

Install from sdcard complete.
```
