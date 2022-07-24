# Fonksiyon Parametreleri


Fonksiyonlar **parametre** alabilir.
Fonksiyon **parametre**leri, fonksiyonun tanımında listelenen adlardır.[^1]

**Sözdizimi:**

```javascript	
function fonksiyonAdi(param1, param2, ...) {
  // İşlemler
}
```

  
  [^1]: Değişkenlerde olduğu gibi, parametrelere parantez içinde **virgülle** ayrılmış **isimler** verilmelidir.

## Parametreleri Kullanma

Parametreleri tanımladıktan sonra fonksiyon içerisinde kullanabiliriz.

```javascript
function merhabaDe(isim) {
  alert("Merhaba, " + isim);
}

merhabaDe("Neo"); // "Merhaba, Neo" mesajını gösterir.
```

Bu fonksiyon, adı **isim** verilen bir parametre alır. Fonksiyonu çağırırken, parantez içinde parametrenin değerini sağlarız.[^2]
  
  [^2]: Fonksiyon argümanları, işleve iletilen (ve alınan) gerçek değerlerdir.

<hr>

Tek bir fonksiyon tanımlayabilir ve ona farklı parametre değerleri (argümanlar) iletebilirsiniz.[^3]

```javascript
function sayac(rakam) {
  alert("Rakam, " + rakam); // "Rakam, bir", "Rakam, iki", "Rakam, üç" mesajlarını gösterir.
}

sayac("bir");
sayac("iki");
sayac("üç"); 
```	

  [^3]: Bu, sağlanan argüman için her seferinde işlevin kodunu yürütecektir.

