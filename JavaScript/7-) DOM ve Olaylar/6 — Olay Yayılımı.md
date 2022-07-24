# Olay Yayılımı

HTML DOM'de olay yaymanın iki yolu vardır: **köpürme** ve **yakalama**. 

Olay yayılımı, bir olay meydana geldiğinde eleman sırasının tanımlanmasına izin verir. Bir \<div> öğesinin içinde bir \<p> öğeniz varsa ve kullanıcı \<p> öğesini tıklarsa, önce hangi öğenin "click (tıklanma)" olayı ele alınmalıdır?

**Köpürmede**, önce en içteki elemanın olayı işlenir ve sonra dış elemanın olayı işlenir. Önce \<p> öğesinin tıklama olayı, ardından \<div> öğesinin tıklama olayı işlenir.

**Yakalamada**, önce en dıştaki öğenin olayı, ardından içteki olay ele alınır.  Önce \<div> öğesinin tıklanma olayı, ardından \<p> öğesinin tıklanma olayı işlenir.[^1]

  [^1]: Yakalama, DOM'den aşağı iner.  Kabarcıklanma DOM'da yükselir.
  
## Yakalama vs Köpürme

**addEventListener()** yöntemi, "useCapture" parametresiyle yayılma türünü belirtmenize olanak tanır.

```javascript
addEventListener(olay, fonksiyon, yakalamayı kullanma)
```

Varsayılan değer **false**'tur; bu, köpüren yayılımın kullanıldığı anlamına gelir;  değer **true** olarak ayarlandığında, olay yakalama yayılımını kullanır.[^2]

  [^2]: Bu, özellikle DOM hiyerarşisindeki birden çok öğe için aynı olayı ele aldığınızda kullanışlıdır. 👍🏻

```javascript
// Yayılımı yakalama
elem1.addEventListener("click", fonksiyonum, true);


// Köpüren yayılım
elem2.addEventListener("click", fonksiyonum, false);
```

