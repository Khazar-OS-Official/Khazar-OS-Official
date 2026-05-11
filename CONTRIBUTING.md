# KhazarOS-a Töhfə Vermək

KhazarOS sıfırdan yazılan kernel olduğu üçün töhfə vermək üçün aşağı səviyyə bilik tələb olunur. Lakin hər səviyyədən töhfə — kod, sənəd, test — dəyərlidir.

---

## Töhfə Sahələri

| Sahə | Tələb olunan bilik |
|---|---|
| Bootloader | NASM Assembly, x86 boot prosesi |
| Kernel | C, x86_64 arxitekturası, interrupt-lar |
| Driver-lər | C, hardware protokolları |
| Userland | C |
| Sənədlər | Azərbaycan / İngilis dili |
| Test | QEMU, VirtualBox, real hardware |

---

## Başlamaq

### 1. Fork et

GitHub-da **Fork** düyməsinə bas.

### 2. Klonla

```bash
git clone https://github.com/SƏNİN-ADIN/khazaros.git
cd khazaros
```

### 3. Branch yarat

```bash
# Xəta düzəltmə
git checkout -b fix/keyboard-interrupt

# Yeni funksionallıq
git checkout -b feat/filesystem
```

### 4. Dəyişiklik et

Build et və QEMU-da test et:

```bash
./build.sh
qemu-system-x86_64 -cdrom khazar_os.iso -m 512M
```

### 5. Commit et

```bash
git add .
git commit -m "fix: keyboard interrupt handler düzəldildi"
```

**Commit formatı:**

```
növ: qısa açıqlama

növlər: feat, fix, asm, driver, docs, refactor, test
```

### 6. Pull Request aç

```bash
git push origin fix/keyboard-interrupt
```

GitHub-da **Pull Request** aç, `main` branch-ə yönləndir.

---

## Qaydalar

- Dəyişiklikdən əvvəl mütləq `./build.sh` ilə build et
- PR-dən əvvəl QEMU-da test et, nəticəni qeyd et
- Böyük dəyişikliklər üçün əvvəlcə issue aç, müzakirə et
- Heç bir şəxsi məlumat, API key, parol commit etmə
- Commit mesajları **Azərbaycan** və ya **İngilis** dilində olmalıdır

---

## Bug Report

Issue açarkən daxil et:
- Xətanın tam mətni
- Hansı hardware / VM-də baş verib
- Addım-addım təkrarlama qaydası
- Build log (varsa)

---

## Suallar

[Discussions](https://github.com/khazaros/khazaros/discussions) bölməsindən soruş.
