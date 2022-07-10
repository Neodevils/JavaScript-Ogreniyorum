# Çoklu Parametreler

Bir fonksiyon için birden çok parametreyi **virgülle ayırarak** tanımlayabilirsin.[^1]

```javascript	
function fonksiyonum(x, y) {
   // bazı işlemler
}
```

  [^1]: Yukarıdaki örnek, *fonksiyonum* fonksiyonunun iki parametre alacak şekilde tanımlar.

<hr>

Parametreler, işlevin tanımı içinde kullanılır.[^2]

```javascript
function hakkimda(isim, yaş) {
  document.write(isim + ", " + yaş + " yaşında."); 
}
```

  [^2]: Fonksiyon parametreleri, fonksiyon tanımında listelenen isimlerdir.

<hr>

*Fonksiyonu çağırırken, argümanları tanımladığın sırayla sağla!*[^3]

```javascript
function hakkimda(isim, yaş) {
  document.write(isim + ", " + yaş + " yaşında."); 
}

hakkimda("Neo", 20); // "Neo, 20 yaşında." mesajını web sayfasına yazdırır.
```

  [^3]: Tanımlanandan daha fazla argüman iletirsen, bunlar *argümanlar* adlı bir diziye atanacaktır. Bunlar şu şekilde kullanılabilir: argümanlar[0], argümanlar[1], vb. şekilde.

<hr>

Fonksiyonu tanımladıktan sonra gerektiği kadar çağırabilirsin. JavaScript işlevleri, alınan argümanların sayısını kontrol etmez.[^4]

  [^4]: Bir işlev eksik argümanlarla (bildirilenden daha az) çağrılırsa, eksik değerler ***undefined*** olarak ayarlanır; bu, bir değişkene bir değer atanmadığını gösterir.
