# Akfa obyekt treking

## Loyiha maqsadi
Ushbu loyiha videodagi odamlarni aniqlaydi, ularni track qiladi va video davomida qatnashgan odamlar sonini hisoblaydi.

Yakuniy natija quyidagicha bo‘ladi:
- `odam yo'q` — agar videoda odam topilmasa
- `odam N ta` — agar videoda odamlar aniqlansa

Bundan tashqari, loyiha output video ham yaratadi. Unda:
- odamlar bounding box bilan ko‘rsatiladi
- har bir sanalgan odamga `id` biriktiriladi
- umumiy count video ustida yozib boriladi

---

## Ishlatilgan texnologiyalar
- Python
- OpenCV
- Ultralytics YOLO (`yolo26x.pt`)
- BoT-SORT tracker
- Google Colab

---

## Muhim eslatma
Bu loyiha **Google Colab** muhitida ishlatish uchun tayyorlangan.

Shu sababli alohida `requirements.txt` fayli berilmagan.


## Kirish ma’lumoti
Loyiha input sifatida 1 ta video qabul qiladi.

Misol:
```python
VIDEO_PATH = "/content/video1.mp4"
```

- video repoda berilgan, lokal yuklab, colab ga yuklaysiz

---

## Chiqish natijasi
Loyiha 2 xil natija beradi:

1. **Console natija**
   - yakuniy odamlar soni

2. **Output video**
   - track qilingan va count yozilgan video
   - avtomatik ravishda saqlanadi

Misol:
```python
video1_counted.mp4
```

---

## Loyiha qanday ishlaydi
Dastur quyidagi bosqichlarda ishlaydi:

1. OpenCV yordamida videoni ochadi
2. YOLO26x modeli bilan faqat odamlarni aniqlaydi
3. BoT-SORT tracker yordamida odamlarni frame’lar bo‘ylab kuzatadi
4. Har bir sanalgan odamga `0` dan boshlab ID beradi
5. Video ustiga:
   - sariq box
   - sariq border
   - qora matn
   yozadi
6. Yakuniy videoni saqlaydi

---

## Asosiy parametrlar
- har bir giperparameter va parameterlarga kodning ichida izoh berilgan.
---

## Colab’da ishlatish tartibi

### 1. Google Colab oching
Yangi notebook oching.

### 2. Python faylni yuklang
Loyihadagi `.ipynb` faylni Colab’ga yuklang.

### 3. Videoni yuklang
Input videoni Colab ichiga yuklang. Video odatda `/content/` ichida saqlanadi.

Misol:
```python
VIDEO_PATH = "/content/video1.mp4"
```

### 4. Natijani ko‘ring
Ishga tushgandan so‘ng:
- console’da yakuniy count chiqadi
- output video saqlanadi va ko‘rsatiladi
---

## Natija namunasi
Misol uchun yakuniy natija quyidagicha chiqishi mumkin:

```python
odam 7 ta
```

yoki

```python
odam yo'q
```

---

## Qo‘shimcha eslatmalar
- Model faqat `person` klassini aniqlaydi
- Sanalgan odamlar uchun ID `0` dan boshlanadi

---