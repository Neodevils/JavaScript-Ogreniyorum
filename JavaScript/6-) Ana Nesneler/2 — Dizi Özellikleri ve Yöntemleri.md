# `length` Uzunluk Özelliği

JavaScript dizilerinin kullanışlı **yerleşik** özellikleri ve yöntemleri vardır.

Bir dizinin **uzunluk** özelliği, elemanlarının sayısını döndürür.[^1]

```javascript
var dersler = ["HTML", "CSS", "JS"];
document.write(dersler.length); // 3 yazdırır.
```

  [^1]: `length` özelliği her zaman en yüksek dizi dizininden bir fazladır. Dizi boşsa, uzunluk özelliği **0** değerini döndürür.

# `concat` Dizileri Birleştirme

JavaScript'in `concat()` yöntemi, dizileri birleştirmene ve tamamen yeni bir dizi oluşturmana olanak tanır.[^2]

**Örneğin:**

```javascript	
var c1 = ["HTML", "CSS"];
var c2 = ["JS", "C++"];
var dersler = c1.concat(c2);

document.write(dersler[2]); // "JS" yazdırır.
```

  [^2]: **concat** işlemi *c1* ve *c2* dizilerini etkilemez - elde edilen birleştirmeyi **yeni bir dizi** olarak döndürür.

