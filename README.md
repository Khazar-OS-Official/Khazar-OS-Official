<div align="center">

<br/>

```
██╗  ██╗██╗  ██╗ █████╗ ███████╗ █████╗ ██████╗  ██████╗ ███████╗
██║ ██╔╝██║  ██║██╔══██╗╚══███╔╝██╔══██╗██╔══██╗██╔═══██╗██╔════╝
█████╔╝ ███████║███████║  ███╔╝ ███████║██████╔╝██║   ██║███████╗
██╔═██╗ ██╔══██║██╔══██║ ███╔╝  ██╔══██║██╔══██╗██║   ██║╚════██║
██║  ██╗██║  ██║██║  ██║███████╗██║  ██║██║  ██║╚██████╔╝███████║
╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝ ╚══════╝
```

**Azərbaycan üçün, sıfırdan yazılmış əməliyyat sistemi**

[![License](https://img.shields.io/badge/License-GPL%20v2-blue.svg?style=flat-square)](LICENSE)
[![Language](https://img.shields.io/badge/Language-Assembly%20%2F%20C-orange?style=flat-square)]()
[![Platform](https://img.shields.io/badge/Platform-x86__64-lightgrey?style=flat-square)]()
[![Status](https://img.shields.io/badge/Status-Active%20Development-brightgreen?style=flat-square)]()
[![Made in](https://img.shields.io/badge/Made%20in-Azerbaijan-blue?style=flat-square)]()

<br/>

</div>

---

## Haqqında

**KhazarOS** — Linux, BSD və ya digər mövcud nüvələrdən istifadə edilmədən **tamamilə sıfırdan** yazılmış əməliyyat sistemidir. Bootloader-dən başlayaraq kernel, userland və qrafik interfeysinə qədər hər komponent əldə yazılır.

Layihənin məqsədi Azərbaycan üçün — **təhlükəsiz, yüngül, Azərbaycan dilli** və daima inkişaf edən bir OS yaratmaqdır.

---

## Xüsusiyyətlər

| | |
|---|---|
| 🔧 **Sıfırdan yazılmış kernel** | Heç bir üçüncü tərəf nüvəyə asılılıq yoxdur |
| 🇦🇿 **Azərbaycan dili dəstəyi** | Sistem səviyyəsindən interfeysinə qədər |
| 🖥️ **Qrafik interfeys** | Real hardware-da işləyən desktop mühiti |
| 🔒 **Təhlükəsizlik** | Tam nəzarət — gizli kod yoxdur |
| ⚡ **Yüngül və sürətli** | Lazımsız komponent yoxdur |
| 🔄 **Aktiv inkişaf** | Tez-tez yeniləmələr və yeni funksiyalar |

---

## Repo Strukturu

```
khazaros/
├── boot/                   # Bootloader (Assembly)
├── kernel/                 # Kernel mənbə kodu
├── userland/               # İstifadəçi məkanı proqramları
├── build/                  # Build artefaktları
├── iso/                    # ISO yaratma konfiqurasiyası
├── docs/                   # Texniki sənədlər
├── scripts/                # Build və köməkçi skriptlər
├── Makefile                # Əsas build sistemi
├── linker.ld               # Linker skripti (32-bit)
├── linker64.ld             # Linker skripti (64-bit)
├── grub.cfg                # GRUB bootloader konfiqurasiyası
└── build.sh / rebuild.sh   # Build skriptləri
```

---

## Başlamaq

### Tələblər

```bash
sudo apt-get install nasm gcc make xorriso qemu-system-x86 grub-pc-bin
```

### Build

```bash
git clone https://github.com/khazaros/khazaros.git
cd khazaros
./build.sh
```

### Sürətli Başlanğıc

Ətraflı quraşdırma üçün → [`QUICKSTART.md`](QUICKSTART.md)

### QEMU ilə Test

```bash
qemu-system-x86_64 -cdrom khazar_os.iso -m 512M
```

### Virtual Machine ilə Test

`khazar_hd.img` və ya `khazar_hd.vdi` faylını VirtualBox / VMware-ə əlavə et.

---

## Hal-hazırkı Vəziyyət

- [x] Bootloader
- [x] Kernel yüklənməsi
- [x] Qrafik interfeys (real hardware-da test edilib)
- [x] ISO yaratma (`khazar_os.iso`)
- [x] Virtual disk dəstəyi (`khazar_hd.img`, `.vdi`)
- [ ] Azərbaycan dili tam inteqrasiyası
- [ ] Fayl sistemi
- [ ] Şəbəkə dəstəyi
- [ ] Genişləndirilmiş driver dəstəyi

---

## Töhfə Ver

Assembly və ya C bilirsənsə — töhfən xoş gəlir.
Ətraflı: [`CONTRIBUTING.md`](CONTRIBUTING.md)

---

## Lisenziya

GPL v2.0 — ətraflı: [`LICENSE`](LICENSE)

---

<div align="center">
<br/>
<sub>Azərbaycanda — sıfırdan, əldə, ürəklə yazılır.</sub>
<br/><br/>
</div>
