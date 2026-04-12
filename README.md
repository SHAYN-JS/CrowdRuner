# 🏃‍♂️ Crowd Runner: Math Masters

Crowd Runner — bu ajoyib 3D giperkazual (hyper-casual) mobil uslubidagi o'yin. Asosiy maqsad — matematik darvozalardan o'tish orqali to'dani ko'paytirish, to'siqlardan o'tish va yakuniy bosqichda raqiblarni mag'lub etib g'alaba qozonishdir.

---

## 📁 Loyiha Arxitekturasi

Loyihaning amaldagi fayllar tizimi va ularning maqsadi:

```text
CrowdRunner/
├── index.html                  # O'yinning asosiy sahifasi, menyular va UI elementlari
├── style.css                   # Premium AAA darajasidagi dizayn, CSS animatsiyalar va stillar
├── game.js                     # Three.js 3D dvijogi asnosida qurilgan o'yin logikasi barining yuragi
├── expand.js                   # O'yinga qo'shimcha murakkab mexanika va effektlarni qo'shuvchi skript
├── PLAY_GAME.bat               # Windows tizimida o'yinni osonlikcha mahalliy serverda ishga tushirish skripti
├── README.md                   # Ushbu hujjat
└── Qo'shimcha Hujjatlar/
    ├── FIXES_APPLIED.md        # O'tmishda to'g'rilangan buglar va o'zgarishlar tarixi
    ├── VISIBILITY_FIXED.md     # Kadrlar ko'rinishi va vizual rendering bilan bog'liq yechimlar
    └── UNITY_SCRIPTS.md        # O'yinni kelajakda Unity ga ko'chirish yoki moslashtirish rejalari
```

---

## 🛠 Texnologiyalar

Ushbu o'yin veb-brauzerlar uchun yuksak sifatli ishlab chiqilgan bo'lib, o'zida quyidagi texnologiyalarni jamlagan:
* **HTML5 & Tailwind CSS** – O'yin bosh menyusi, savdo markazi (skinlar) va foydalanuvchi interfeyslari uchun.
* **Vanilla JavaScript** – Tezkor va optimallashtirilgan o'yin tsikli.
* **Three.js** – Muammosiz, yuqori sifatli (AAA) 3D grafikalar va modellar ustida ishlash.
* **Tween.js** – Ajoyib harakatlanish (bounce, float, hover) interpolatsiyalari va moslashuvchan animatsiyalar uchun.

## 📌 Asosiy Xususiyatlar
- **Matematik Mexanika:** Darvozalar ustidagi ko'paytirish, qo'shish, ayirish jarayonlari to'da sonini o'zgartiradi.
- **Kengaytirilgan O'yin Do'koni:** Tangalar yig'ish evaziga vizual jihatdan o'ziga xos skinlarni xarid etish mumkin.
- **Dinamik Atrof-Muhit:** Kun va tunga almashuvchi ob-havo (yomg'ir, qor tizimlari), harakatlanuvchi arra va ulkan lazer to'siqlari.

## 🚀 Qanday qilib ishga tushirish mumkin?
1. Windows muhitida o'yinni to'g'ridan-to'g'ri Localhost orqali ochish uchun \`PLAY_GAME.bat\` faylini ikki marta bosing.
2. Yoki **Live Server** dasturidan foydalanib `index.html` faylini brauzeringizda ochishingiz ham mumkin.
3. Klaviaturadagi (W, A, S, D yoki strelkalar) yordamida personajlarni boshqaring hamda sarguzashtdan rohatlaning!
