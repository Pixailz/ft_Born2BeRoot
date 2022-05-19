# B0rnToBeRoot
note about this [project](https://projects.intra.42.fr/projects/born2beroot)

## Setup Virtual Machine

### Download link

[debian-XX.XX.X-amd64-DVD-1.iso](https://cdimage.debian.org/debian-cd/current/amd64/iso-dvd/)

---

<details>
	<summary>Create Virtual Machine</summary>

- Click `New` to create a new virtual machine<br>
![](./imgs/installation/vbox_create/new.png)
- Put a name, select `linux` as type and `Debian (64-bit)`<br>
![](./imgs/installation/vbox_create/name.png)
- Select the amount of memory you want to allocate to the virtual machine<br>
![](./imgs/installation/vbox_create/memory.png)
- Make sure `Create a virtual disk now` is selected<br>
![](./imgs/installation/vbox_create/disk_create.png)
- Click `Create`<br>
![](./imgs/installation/vbox_create/disk_type.png)
- Make sure to create a dynamic disk<br>
![](./imgs/installation/vbox_create/disk_physical.png)
- Choose a disk size<br>
![](./imgs/installation/vbox_create/disk_size.png)

</details>

---

<details>
	<summary>Config Virtual Machine</summary>

- Right click on `Born2beroot` and select `Settings`<br>
![](./imgs/installation/vbox_config/rightclick_settings.png)
- Go to `System`, here make sure you are happy with the amount of ram you have
allocated<br>
![](./imgs/installation/vbox_config/settings_sys_mother.png)
- Still on `System` > `Processor`, check the amount of proc<br>
![](./imgs/installation/vbox_config/settings_sys_proc.png)
- Now go to the `Storage` section, on `Controller: IDE` select the blue disk
then `Choose a disk`<br>
![](./imgs/installation/vbox_config/iso_section.png)
- Now choose the iso you've downloaded [here](./README.md#download-link)<br>
![](./imgs/installation/vbox_config/iso_selected.png)

> now you're ready to launch the Virtual Machine
</details>

---

<details>
	<summary>Setup Debian</summary>

- Select `Install`<br>
![](./imgs/installation/debian/main_menu.png)<br>
![](./imgs/installation/debian/language.png)<br>
![](./imgs/installation/debian/location1.png)<br>
![](./imgs/installation/debian/location2.png)<br>
![](./imgs/installation/debian/location3.png)<br>
![](./imgs/installation/debian/locals.png)<br>
- American English is QWERTY<br>
![](./imgs/installation/debian/keymap.png)
- Set the hostname according to `<42login>42`<br>
![](./imgs/installation/debian/hostname.png)
- leave blank<br>
![](./imgs/installation/debian/domain.png)
- Set `root` password, remember it<br>
![](./imgs/installation/debian/password_root.png)
- Set the `user` real name<br>
![](./imgs/installation/debian/realname.png)
- Set the `user` login name<br>
![](./imgs/installation/debian/loginname.png)
- Set `user` password, remember it<br>
![](./imgs/installation/debian/password_user.png)
- Select `Guided - use entire disk and set up encrypted LVM`<br>
![](./imgs/installation/debian/partition_encryption.png)<br>
![](./imgs/installation/debian/partition_disk_select.png)
- Separate /home /var and /tmp partition<br>
![](./imgs/installation/debian/partition_separated.png)<br>
![](./imgs/installation/debian/partition_write.png)
- Set encryption password<br>
![](./imgs/installation/debian/password_encryption.png)
- Set partition size<br>
![](./imgs/installation/debian/partition_size.png)
- Finish partitioning<br>
![](./imgs/installation/debian/partition_finish.png)
- Confirm write change<br>
![](./imgs/installation/debian/partition_confirm.png)<br>
![](./imgs/installation/debian/scan_no_extra.png)
- Setup mirror<br>
![](./imgs/installation/debian/setup_mirror.png)<br>
![](./imgs/installation/debian/setup_mirror_country.png)<br>
![](./imgs/installation/debian/setup_mirror_link.png)
- Leave blank here<br>
![](./imgs/installation/debian/setup_mirror_leaveblank.png)
- Choose whatever you wan't telemtry or not<br>
![](./imgs/installation/debian/telemetry.png)
- Unselect `Debian desktop environement`, `GNOME` and
`standard system utilities`<br>
![](./imgs/installation/debian/no_package.png)
  > we will install those later
- Install Grub<br>
![](./imgs/installation/debian/grub.png)<br>
![](./imgs/installation/debian/grub_disk.png)
- :tada: TADA :tada: it's finished
![](./imgs/installation/debian/finish.png)

</details>

---

<details>
	<summary>Bonus: Snapshot</summary>

- first click on the "3-dot" button on the right of the virtual machine,
and select snapshots<br>
![](./imgs/installation/vbox_snapshot/right_click.png)
- Then select `Take`<br>
![](./imgs/installation/vbox_snapshot/take.png)
- Name the snapshot and write some notes<br>
![](./imgs/installation/vbox_snapshot/name.png)
- Now when you broke all the things, you can recover it very quickly by
selecting the snapshot name and <br>
click on `Restore`<br>
![](./imgs/installation/vbox_snapshot/restore.png)
</details>

---

## Config Debian

### Clean `/etc/apt/sources.list`

remove line begin with `deb cdrom:[Debian`
file should look like this:<br>
![](./imgs/setup/exemple_sources.png)
