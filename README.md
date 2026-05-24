# 🏃‍♂️ Crowd Runner: Math Masters

A high-performance, premium 3D hyper-casual runner game built using **Vanilla JavaScript**, **Three.js**, and **Tailwind CSS**. Experience fluid rendering, advanced powerups, dynamic obstacles, and a responsive upgrades system.

---

## 📁 Loyiha Arxitekturasi / Directory Structure

Loyiha giperkazual o'yinlar uchun moslashtirilgan bo'lib, aktivlarning yuklanish vaqtini kamaytirish va ishlash tezligini maksimal darajada oshirish uchun yagona sahifali (SPA) dizayn arxitekturasiga asoslangan.

```text
CrowdRunner/
├── index.html                  # O'yin interfeysi, menyular, do'kon va Tailwind stillari
├── style.css                   # Custom CSS stillar va animatsiyalar
├── game.js                     # O'yin dvijogi (Three.js), fizika, xotira va pooling tizimi (Yuragi)
├── expand.js                   # Custom darajalar va o'yin qumdoni (sandbox) moduli
├── three.min.js                # WebGL 3D vizuallashtirish kutubxonasi (v0.160.0)
├── tween.umd.js                # Silliq animatsiyalar yaratish dvijogi (v23.1.1)
├── PLAY_GAME.bat               # Windows tizimida o'yinni local serverda boshlash skripti
└── README.md                   # Texnik hujjat va arxitektura bo'yicha yo'riqnoma
```

---

## 🛠 Texnik Arxitektura (Technical Architecture)

### 1. Game State Management (`GAME_STATE`)
O'yindagi barcha dinamik o'zgaruvchilar va 3D obyektlar yagona global holatda boshqariladi:
* **Legion/To'dani kuzatish:** Faol 3D stickman obyektlari ro'yxati, pool massivlari va to'da soni.
* **Progression:** Daraja raqami, tangalar, jami tangalar va do'kondan sotib olingan skinlar.
* **Boshqaruv:** Sichqoncha, klaviatura va mobil sensorli boshqaruv holati.

### 2. High-Performance Stickman Pooling System (Odamchalarni qayta ishlash)
O'yinda minglab odamchalar yaratilishida mobil qurilmalarda sekinlashuv (Garbage Collection lag) yuzaga kelmasligi uchun **Object Pooling Pattern** joriy qilingan:
* Odamchalar nobud bo'lganda, Three.js sahnasidan butunlay o'chirib tashlanmay, `visible = false` qilinadi va `GAME_STATE.stickmanPool` massiviga joylanadi.
* Yangi odamchalar kerak bo'lganda (masalan, ko'paytiruvchi darvozadan o'tganda), tizim yangi mesh yaratmasdan, pool ichidan eski stickmanni oladi, rangini sozlaydi va `visible = true` qilib sahnaga qaytaradi.
* Bu GPU va CPU yuklamasini keskin kamaytirib, 5,000 tagacha odamchani bir vaqtda silliq render qilish imkonini beradi.

### 3. Procedural Level Generation (Tasodifiy darajalar yaratish)
Darajalar o'yinchi darajasidan kelib chiqib avtomatik shakllantiriladi:
* **Uzunlik:** Daraja oshgan sari yo'lak uzunligi `150 + currentLevel * 10` ko'rinishida o'sadi.
* **To'siqlar:** Arralar, aylanuvchi bolta va maydonlar, lazer to'siqlari va dushman askarlari tasodifiy taqsimlanadi.
* **Matematik Darvozalar:** Matematik amallar (`+`, `x`, `-`, `/`) tasodifiy joylashtirilib, legion sonini o'zgartiradi.

### 4. GPU VRAM Memory Management (Xotirani tozalash)
O'yinda xotira sizib chiqishi (Memory Leak) va vaqt o'tishi bilan o'yin qotishining oldi olingan:
* O'yinchi ortda qoldirgan darvozalar va modellar Three.js sahnasidan o'chiriladi.
* Yangi daraja boshlanganda, eski modellarning barcha 3D geometriya, material hamda teksturalari `traverse(disposeNode)` orqali GPU xotirasidan butunlay tozalanadi (`dispose`).

---

## 🚀 Ishga Tushirish (Quick Start)

### Mahalliy server orqali ishlatish:
O'yin mahalliy fayllarni brauzerda CORS xatoligisiz to'g'ri yuklashi uchun local serverda ishlashi lozim.

#### 1-usul: Bat skript (Windows uchun eng oson)
Loyiha jildidagi `PLAY_GAME.bat` faylini ikki marta bosing. U avtomatik tarzda brauzerni ishga tushiradi.

#### 2-usul: Python HTTP Server (Tavsiya etilgan)
Terminalda loyiha jildiga kiring va quyidagi buyruqni bosing:
```powershell
python -m http.server 8000
```
So'ng brauzerda: `http://localhost:8000` manzilini oching.

---

## 🎮 Boshqaruv elementlari (Controls)
* **Klaviatura:** `W`, `A`, `S`, `D` yoki **Strelkalar** yordamida legionni boshqaring.
* **Sichqoncha/Touch:** Ekran bo'ylab surish orqali to'dani o'ngga yoki chamga yo'naltiring.
* **Maqsad:** Yashil darvozalardan o'tib legion sonini ko'paytirish, to'siqlardan qochish va yakuniy Bossni mag'lub etib eng yuqori bonus tangalarni to'plash!
