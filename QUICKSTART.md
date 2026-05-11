# KhazarOS — Sürətli Başlanğıc

Bu sənəd KhazarOS-u mümkün qədər tez işə salmaq üçündür.

---

## 1. Tələblər

### Build üçün (mənbədən yığmaq istəyirsənsə)

```bash
sudo apt-get update
sudo apt-get install -y nasm gcc make xorriso qemu-system-x86 grub-pc-bin grub-common
```

### Yalnız test etmək istəyirsənsə

- [QEMU](https://www.qemu.org/) — terminaldan
- [VirtualBox](https://www.virtualbox.org/) — GUI ilə
- Ya da real USB — Ventoy / `dd` ilə

---

## 2. Mənbədən Build Et

```bash
# Klonla
git clone https://github.com/khazaros/khazaros.git
cd khazaros

# Build et
./build.sh
```

Uğurlu build-dən sonra aşağıdakı fayllar yaranır:

```
khazar_os.iso       ← bootable ISO
khazar_kernel.bin   ← kernel binary
khazar_hd.img       ← virtual disk (QEMU / VMware)
khazar_hd.vdi       ← virtual disk (VirtualBox)
```

Yenidən build etmək lazımdırsa:

```bash
./rebuild.sh
```

---

## 3. QEMU ilə Test Et (ən sürətli yol)

```bash
qemu-system-x86_64 -cdrom khazar_os.iso -m 512M
```

Disk image ilə:

```bash
qemu-system-x86_64 -hda khazar_hd.img -m 512M
```

---

## 4. VirtualBox ilə Test Et

1. VirtualBox aç → **New**
2. Type: **Other**, Version: **Other/Unknown (64-bit)**
3. RAM: minimum **512 MB**
4. **Use an existing virtual hard disk** → `khazar_hd.vdi` seç
5. Ya da: **Settings → Storage → Add optical drive** → `khazar_os.iso` seç
6. **Start**

---

## 5. Real Hardware-da Test Et (USB)

> ⚠️ USB-dəki bütün məlumatlar silinəcək.

**Linux:**
```bash
sudo dd if=khazar_os.iso of=/dev/sdX bs=4M status=progress && sync
```
`/dev/sdX` — USB-nin yolu (məs. `/dev/sdb`)

**Windows:**
[Rufus](https://rufus.ie) ilə `khazar_os.iso`-nu USB-yə yaz.

---

## 6. Problemlər

| Problem | Həll |
|---|---|
| `nasm: command not found` | `sudo apt install nasm` |
| `xorriso: command not found` | `sudo apt install xorriso` |
| QEMU açılmır | `sudo apt install qemu-system-x86` |
| Build xətası | `./rebuild.sh` ilə yenidən cəhd et |
| VirtualBox boot olmur | Boot order-i **Optical** ilə başlat |

Həll tapa bilmirsənsə → [Issue aç](https://github.com/khazaros/khazaros/issues)

---

Ətraflı texniki sənədlər üçün → [`docs/`](docs/) qovluğuna bax.
