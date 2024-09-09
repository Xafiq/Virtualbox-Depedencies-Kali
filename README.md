# Virtualbox-Depedencies

Installing VirtualBox in Kali, expect some twists like missing dependencies or kernel issues. The follow these steps, are some of the possibilities.

---

Dependency issues like:  Package 'libvpx*' is not installed. Package 'libqt5opengl*' is missing.'
You may encounter dependency issues like:

```bash
Package 'libvpx*' is not installed.
Package 'libqt5opengl*' is missing.'
```

---

### Fix Dependency Problems

Let's install the missing packages manually. Here are a couple of common ones:

```bash
sudo apt install libvpx*
sudo apt install libqt5opengl*
```

If you get errors like "package not found," try grabbing them from [pkgs.org](https://pkgs.org/) or download the `.deb` files from the Debian repo

---

### Install Linux Headers

VirtualBox needs your kernel headers to compile modules for your kernel version. Make sure you've got them:

```bash
sudo apt install linux-headers-$(uname -r)
```

If you still hit kernel issues, you might need to:

```bash
sudo dpkg-reconfigure virtualbox-dkms
```

This should help VirtualBox find and compile the right modules. ⚙️

---

> #### Enable Virtualization in BIOS (If Needed)

> If VirtualBox throws "VT-x/AMD-V hardware acceleration is not available," check your BIOS and enable virtualization (Intel VT or AMD-V).

---

### Launch VirtualBox

Finally, launch VirtualBox:

```bash
virtualbox
```
