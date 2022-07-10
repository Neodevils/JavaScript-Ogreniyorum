# else if (yoksa) ifadesi

**Değilse**yi gördük, **eğer**i de gördük, gördük, **yoksa** ile buluşmanın zamanı geldi.

**else if** ifadesi, ilk koşul yanlışsa yeni bir koşul belirtmemize izin verdiği için kullanışlıdır.

Bunun gibi:

```javascript
var ders = 1; 

if (ders == 1) {
  document.write("<h1>HTML Eğitimi</h1>"); // HTML Eğitimi yazdırır.
} else if (ders == 2) {
  document.write("<h1>CSS Eğitimi</h1>"); 
} else {
  document.write("<h1>JavaScript Eğitimi</h1>");
} 
```

Bu, yukarıdaki kodda olan şeydir:
- ders 1'e eşitse, "HTML Eğitimi" çıktısını alırız;
- aksi takdirde, ders 2'ye eşitse, "CSS Eğitimi" çıktısını alırız;
- yukarıdaki koşullardan hiçbiri doğru değilse, "JavaScript Eğitimi" çıktısını alırız.

ders 1'e eşittir, bu nedenle aşağıdaki `HTML Eğitimi` çıktısını alırız.[^3]

  [^3]: Son *else* ifadesi, *else if* ifadesini "bitirir" ve her zaman *if* ve *else if* ifadelerinden sonra yazılmalıdır.

<hr>

Son **else** bloğu, koşullardan **hiçbiri** doğru olmadığında yürütülür.

Bir önceki örneğimizde **ders** değişkeninin değerini değiştirelim.[^4]

```javascript
var ders = 3;
if (ders == 1) {
  document.write("<h1>HTML Eğitimi</h1>");
} else if (ders == 2) {
  document.write("<h1>CSS Eğitimi</h1>");
} else {
  document.write("<h1>JavaScript Eğitimi</h1>"); // JavaScript Eğitimi yazdırır.
}
```

  [^4]: İhtiyaç duyduğunuz kadar *else if* ifadeleri yazabilirsiniz.

