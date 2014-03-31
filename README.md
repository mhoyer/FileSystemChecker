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
