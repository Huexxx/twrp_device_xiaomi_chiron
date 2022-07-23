# device_xiaomi_chiron-twrp

Tree for building OrangeFox for Xiaomi Mi MIX 2

The Xiaomi Mi MIX 2 (codenamed "Chiron") is a high-end smartphone from Xiaomi.

It was announced in October 2017. Release date was December 2017.

Forked From:https://github.com/0ranko0P/twrp_device_xiaomi_sagit

## Note

Decryption works on Android 12.x ROMs

## Device specifications

| Basic                   | Spec Sheet                                                          |
| -----------------------:|:------------------------------------------------------------------- |
| CPU                     | Quad-core 2.45 GHz Kryo 280 & Quad-core 1.9 GHz Kryo 280            |
| Chipset                 | Qualcomm MSM8998 Snapdragon 835                                     |
| GPU                     | Adreno 540                                                          |
| Memory                  | 6/8 GB RAM                                                          |
| Shipped Android Version | 7.1.1                                                               |
| Storage                 | 64/128/256 GB (UFS Flash)                                           |
| Battery                 | Non-removable Li-Po 3350 mAh (QC 3.0)                               |
| Display                 | 1080 x 2160 pixels, 5.99 inches (~403 ppi pixel density)            |
| Camera                  | 12 MP, f/2.0, phase detection autofocus, dual-LED (dual tone) flash |

## Device picture

![Xiaomi Mi MIX 2](https://i8.mifile.cn/a1/pms_1505401464.03824312!560x560.jpg "Xiaomi Mi MIX 2 in black")

## Kernel Source

https://github.com/Nanhumly/android_kernel_xiaomi_msm8998/tree/lineage-19.1

## Compile

First repo init the TWRP 12.1 tree:

```shell
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-12.1
```

Sync source:

```shell
repo sync
```

In order to successfully build in this branch, the following patch(es) will need to be cherry-picked:

- [fscrypt: wip](https://gerrit.twrp.me/c/android_bootable_recovery/+/5405)
- [fscrypt: move functionality to libvold](https://gerrit.twrp.me/c/android_system_vold/+/5540)
- [mtp: Allow transfer of files larger than 4G](https://gerrit.twrp.me/c/android_bootable_recovery/+/5689)

Finally execute these:

```
.build/envsetup.sh
lunch twrp_chiron-eng
mka recoveryimage
```

## Credits

Special thanks to the following people or repo:

- [0ranko0P](https://github.com/0ranko0P)
- [GTCxprice](https://github.com/GTCxprice)
- [Nanhumly](https://github.com/Nanhumly)
- [Rom-Builder](https://github.com/Rom-Builder)
- [foxlesbiao](https://github.com/foxlesbiao)
