# DISKO 2
![Medium](https://img.shields.io/badge/Medium-orange) ![Forensics](https://img.shields.io/badge/Forensics-red) ![picoGym Exclusive](https://img.shields.io/badge/picoGym-Exclusive-blue)

## Description
Can you find the flag in this disk image?
The right one is Linux! One wrong step and its all gone!
I attached the file in this directory.

- Hints
    - How can you extract/isolate a partition?

Challenge Link: https://play.picoctf.org/practice/challenge/506

---

## Solution
### 1. Extract the GZ file
Download and unzip the file:

```bash
gunzip disko-2.dd.gz
```

This extracts an disk image file name `disko-2.dd`.

### 2. Display all partitions on disk
You can use either `mmls` or `fdisk -l` to do this. Here, I used `fdisk -l` and recommend it.

```bash
─$ fdisk -l disko-2.dd 
Disk disko-2.dd: 100 MiB, 104857600 bytes, 204800 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0x8ef8eaee

Device      Boot Start    End Sectors Size Id Type
disko-2.dd1       2048  53247   51200  25M 83 Linux
disko-2.dd2      53248 118783   65536  32M  b W95 FAT32
```

### 3. Check whether you can read the flag from the image
The `strings` command extracts printable sequences, you can use it to locate hidden text, configuration data, URLs, flags, or other human-readable fragments embedded in non-text files (executables, disk images, memory dumps, etc.).

```bash
─$ strings disko-2.dd| grep -E "picoCTF{.*}" 
picoCTF{4_P4Rt_1t_i5_c03b93aa}
picoCTF{4_P4Rt_1t_i5_aa9cb033}
picoCTF{4_P4Rt_1t_i5_30ac9ba3}
picoCTF{4_P4Rt_1t_i5_03cba9a3}
picoCTF{4_P4Rt_1t_i5_039aca3b}
picoCTF{4_P4Rt_1t_i5_30ca93ba}
picoCTF{4_P4Rt_1t_i5_9c3a3a0b}
picoCTF{4_P4Rt_1t_i5_3a9ab3c0}
picoCTF{4_P4Rt_1t_i5_bc93aa30}
picoCTF{4_P4Rt_1t_i5_3aba039c}
picoCTF{4_P4Rt_1t_i5_3a3cba09}
picoCTF{4_P4Rt_1t_i5_a3c9ba30}
picoCTF{4_P4Rt_1t_i5_339b0aca}
picoCTF{4_P4Rt_1t_i5_a0bac933}
picoCTF{4_P4Rt_1t_i5_90b3ca3a}
picoCTF{4_P4Rt_1t_i5_aa39bc30}
picoCTF{4_P4Rt_1t_i5_a3ac039b}
picoCTF{4_P4Rt_1t_i5_9caab303}
picoCTF{4_P4Rt_1t_i5_0a93ba3c}
picoCTF{4_P4Rt_1t_i5_c33aab09}
picoCTF{4_P4Rt_1t_i5_a390a3cb}
picoCTF{4_P4Rt_1t_i5_aca3b309}
picoCTF{4_P4Rt_1t_i5_39a0bac3}
picoCTF{4_P4Rt_1t_i5_39c3aa0b}
picoCTF{4_P4Rt_1t_i5_0ba3a9c3}
picoCTF{4_P4Rt_1t_i5_a93c3ba0}
picoCTF{4_P4Rt_1t_i5_ba3a9c03}
picoCTF{4_P4Rt_1t_i5_0bca39a3}
picoCTF{4_P4Rt_1t_i5_9aa3cb03}-8: 
picoCTF{4_P4Rt_1t_i5_309cab3a}
dulo para que fupicoCTF{4_P4Rt_1t_i5_a303acb9} caso de hardware antiguo. Estos par
inen, tanskalainen, hollantilainen, Dvorak, Dzongkha, Esperanto, virolainen, etpicoCTF{4_P4Rt_1t_i5_b9ac33a0}kalainen, Georgia, saksalainen, kreikkalainen, Gujarati, Gurmukhi, heprealainen, Hindi, unkarilainen, islantilainen, irlantilainen, italialainen, japanilainen, Kannada, Kazakki, Khmer, kirgiisi, korealainen, Kurdi (F-asettelu), Kurdi (Q-asettelu), Lao, latinalais-amerikkalainen, latvianlainen, liettualainen, makedonialainen, malajalam, Nepali, pohjois-saame, norjalainen, persialainen, Filippiinit, puolalainen, portugalilainen, punjabi, romanialainen, ven
   picoCTF{4_P4Rt_1t_i5_0aac93b3}v.UTF-8: 
y cpicoCTF{4_P4Rt_1t_i5_baac0933}i gian.
Extended_description-mk.UTF-8:picoCTF{4_P4Rt_1t_i5_033c9baa}
picoCTF{4_P4Rt_1t_i5_b303a9ac}
picoCTF{4_P4Rt_1t_i5_3cab93a0}
picoCTF{4_P4Rt_1t_i5_9acab033} 
Extended_despicoCTF{4_P4Rt_1t_i5_a093ba3c}
picoCTF{4_P4Rt_1t_i5_3c9b3a0a}
picoCTF{4_P4Rt_1t_i5_93aacb03}
Extended_description-nl.UTF-8: De geselecteerde volumegroepnaam is reeds in gebruik. U dient een andere napicoCTF{4_P4Rt_1t_i5_0c3baa93}TF-8: Eit anna gruppert dataomr
Extended_description-cs.UTF-8: VybpicoCTF{4_P4Rt_1t_i5_c0933aab}pinu svazk
e spicoCTF{4_P4Rt_1t_i5_a9ca3b03} les volumes physiques. Veuillez vous assurer que le partitionnement actuel de ces disques vous convient.\n\n${ITEMS}
picoCTF{4_P4Rt_1t_i5_a9c3a0b3}
picoCTF{4_P4Rt_1t_i5_3baac930}
picoCTF{4_P4Rt_1t_i5_a0c933ab}
 i picoCTF{4_P4Rt_1t_i5_b3a039ca} 
parted_server: Closing inpicoCTF{4_P4Rt_1t_i5_0ca93ab3}: main_loop: iteration 31
Aug 30 01:56:45 kerpicoCTF{4_P4Rt_1t_i5_03bac9a3}00:03: resource 2 [mem 0xe7a00000-0xe7afffff 64bit pref]
Aug 30 02:00:49 in-target: Get:695 cdrom://[Kali GNU/Linux 2022.3rc2 _Kali-last-snapshot_ - Official amd64 BD Binary-1 with firmware 20220804-16:57] kali-rolling/main amd64 libruby3.0picoCTF{4_P4Rt_1t_i5_a93a30cb}ug 30 02:00:49 in-target: Get:696 cdrom://[Kali GNU/Linux 2022.3rc2 _Kali-last-snapshot_ - Official amd64 BD Binary-1 with firmware 20220804-16:57] kali-rolling/main amd64 ruby3.0 amd64 3.0.4-7+b1 [683 kB]
Aug 30 02:03:40 in-target: Selecting previopicoCTF{4_P4Rt_1t_i5_aba393c0}3-nplusone.^M
Aug 29 22:1picoCTF{4_P4Rt_1t_i5_3b0aca39} <info>  [1661825835.4061] manager: rfkill: WWAN enabled by radio killswitch; enabled by state file
picoCTF{4_P4Rt_1t_i5_abc3039a}8
picoCTF{4_P4Rt_1t_i5_acb0a339}
picoCTF{4_P4Rt_1t_i5_9a0ac33b}
picoCTF{4_P4Rt_1t_i5_a3c3b90a}
picoCTF{4_P4Rt_1t_i5_9b3a30ac}
picoCTF{4_P4Rt_1t_i5_933b0caa}
picoCTF{4_P4Rt_1t_i5_3cbaa930}
picoCTF{4_P4Rt_1t_i5_ca3a903b}8
picoCTF{4_P4Rt_1t_i5_39a03bac}
picoCTF{4_P4Rt_1t_i5_33aa0bc9}
picoCTF{4_P4Rt_1t_i5_3a0c3ba9}
picoCTF{4_P4Rt_1t_i5_bac3a039}
picoCTF{4_P4Rt_1t_i5_3ba93c0a}
picoCTF{4_P4Rt_1t_i5_3a93ca0b}
picoCTF{4_P4Rt_1t_i5_3a903abc}
picoCTF{4_P4Rt_1t_i5_ac3ab903}
picoCTF{4_P4Rt_1t_i5_93baa0c3}
picoCTF{4_P4Rt_1t_i5_30a3c9ba}
picoCTF{4_P4Rt_1t_i5_c30aa3b9}
picoCTF{4_P4Rt_1t_i5_3ca90a3b}
picoCTF{4_P4Rt_1t_i5_3bc90aa3} PCI Controller Driver version: 0.5
picoCTF{4_P4Rt_1t_i5_39a3acb0}=
MESSAGE=pci_bus 0000:02: resourcpicoCTF{4_P4Rt_1t_i5_cb39aa30} 64bit pref]
picoCTF{4_P4Rt_1t_i5_ab33c0a9}
picoCTF{4_P4Rt_1t_i5_30bac39a}
picoCTF{4_P4Rt_1t_i5_0ac3ba39}
picoCTF{4_P4Rt_1t_i5_b3a9ac03}
picoCTF{4_P4Rt_1t_i5_3c0ab3a9}
picoCTF{4_P4Rt_1t_i5_b0a33ac9}
picoCTF{4_P4Rt_1t_i5_cab39a30}
picoCTF{4_P4Rt_1t_i5_0a9a33bc}
picoCTF{4_P4Rt_1t_i5_903ca3ab}
picoCTF{4_P4Rt_1t_i5_3a9b30ca}
picoCTF{4_P4Rt_1t_i5_abca3930}
picoCTF{4_P4Rt_1t_i5_330baca9}
picoCTF{4_P4Rt_1t_i5_ac3ab903}
picoCTF{4_P4Rt_1t_i5_b9303aac}
picoCTF{4_P4Rt_1t_i5_0c3ab93a}
picoCTF{4_P4Rt_1t_i5_c9ba33a0}
picoCTF{4_P4Rt_1t_i5_9acb330a}
picoCTF{4_P4Rt_1t_i5_0c3a9ba3}
picoCTF{4_P4Rt_1t_i5_3a9ca03b}
picoCTF{4_P4Rt_1t_i5_0bc3a3a9}
picoCTF{4_P4Rt_1t_i5_bc339a0a}
picoCTF{4_P4Rt_1t_i5_ba330c9a}
picoCTF{4_P4Rt_1t_i5_93c0a3ba}
picoCTF{4_P4Rt_1t_i5_a330abc9}
picoCTF{4_P4Rt_1t_i5_339acab0}
picoCTF{4_P4Rt_1t_i5_093abac3}
picoCTF{4_P4Rt_1t_i5_a33cb0a9}
picoCTF{4_P4Rt_1t_i5_a90bc3a3}
picoCTF{4_P4Rt_1t_i5_ba39ca30}
picoCTF{4_P4Rt_1t_i5_ab3c30a9}
picoCTF{4_P4Rt_1t_i5_3acab930}
picoCTF{4_P4Rt_1t_i5_9aac03b3}
picoCTF{4_P4Rt_1t_i5_aac0933b}
picoCTF{4_P4Rt_1t_i5_a03a39cb}
picoCTF{4_P4Rt_1t_i5_9a0b3ca3}
picoCTF{4_P4Rt_1t_i5_aa093c3b}
picoCTF{4_P4Rt_1t_i5_03a3a9bc}
picoCTF{4_P4Rt_1t_i5_aab33c90}
picoCTF{4_P4Rt_1t_i5_ca3b09a3}
picoCTF{4_P4Rt_1t_i5_90b3aac3}
picoCTF{4_P4Rt_1t_i5_ac3a9b30}
picoCTF{4_P4Rt_1t_i5_3b3aa90c}
picoCTF{4_P4Rt_1t_i5_3c390baa}
picoCTF{4_P4Rt_1t_i5_39cba3a0}
picoCTF{4_P4Rt_1t_i5_baa90c33}
picoCTF{4_P4Rt_1t_i5_3b0a3ca9}
picoCTF{4_P4Rt_1t_i5_390ab3ac}
picoCTF{4_P4Rt_1t_i5_33ba9ac0}
picoCTF{4_P4Rt_1t_i5_30ba3a9c}
picoCTF{4_P4Rt_1t_i5_ba390c3a}
```

### 4. Which one is correct?
Based on the results, you can use that command to read the flag; however, you only need one. 
So, let's read the challenge description and hints again. 
They show that you have to extract/isolate the Linux partition before getting the flag.

```bash
─# dd if=disko-2.dd of=Linux.dd skip=2048 bs=512 count=51200
51200+0 records in
51200+0 records out
26214400 bytes (26 MB, 25 MiB) copied, 1.9521 s, 13.4 MB/s
```

- if: image input
- of: image output
- skip: start of Sector 
- bs: Sector size (default: bytes)
- count: Length of Sector 

### 5. Get flag from the Linux partition

```bash
─$ strings Linux.dd| grep -E "picoCTF{.*}"  
picoCTF{4_P4Rt_1t_i5_a93c3ba0}
```

That's all.
