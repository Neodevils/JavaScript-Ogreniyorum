# break (ara)

Bu modülde daha önce *break* deyimiyle tanışmıştık, onu bir döngüden **"atlamak"** için kullanıyorduk ve döngüden sonra kodu çalıştırmaya devam ettiriyorduk.[^1]

**Mesela bunun gibi:**

```javascript
for (i = 0; i <= 10; i++) {
  if (i == 5) {
    break; 
  }
  
  document.write(i + "<br />"); // Alt alta 0, 1, 2, 3, 4, 5 yazar.
}
```

*Bu örnekte, 5'e ulaştığımda döngüden çıkacak.*

  [^1]: Bir işlevin içindeki döngüden hemen bir değer döndürmek için *return* anahtar sözcüğünü kullanabilirsiniz. Bu da döngüyü kıracaktır.

# continue (devam et)

Modül 3'ü neredeyse bitirdik! Kapatılacak son bir şey kaldı.

*break* ifadesinin aksine, *continue* ifadesi döngüde yalnızca bir yinelemeyi keser ve bir sonraki yinelemeyle devam eder.[^2]

**Bunun gibi:**

```javascript
for (i = 0; i <= 10; i++) {
  if (i == 5) {
    continue;
  }

  document.write(i + "<br />"); // Alt alta 0, 1, 2, 3, 4, 6, 7, 8, 9, 10 yazar. 
}
```

  [^2]: **continue**, döngünün bu yinelemesini atladığı için 5 değeri yazdırılmaz.
