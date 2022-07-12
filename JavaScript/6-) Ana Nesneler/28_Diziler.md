# JavaScript Dizileri

**Diziler**, birden çok değeri tek bir değişkende saklar.

Üç ders adını saklamak için üç değişkene ihtiyacınız var değil mi?

```javascript
var ders1 = "HTML"; 
var ders2 = "CSS"; 
var ders3 = "JS"; 
```

Peki ya 500 dersiniz varsa? Çözüm bir **dizi**dir.[^1]

```javascript
var dersler = new Array("HTML", "CSS", "JS"); 
```

  [^1]: Bu sözdizimi, üç değeri veya öğeyi depolayan, **dersler** adlı bir dizi bildirir.


## Diziye Erişmek

Köşeli parantez içinde yazılan **dizin numarası**na başvurarak bir **dizi öğesi**ne başvururuz.

Bu ifade, **dersler**deki ilk elemanın değerine erişir ve ikinci elemanın değerini değiştirir.[^2]

```javascript
var dersler = new Array("HTML", "CSS", "JS"); 
var ders = dersler[0]; // HTML

dersler[1] = "C++"; // CSS değeri C++ olarak değiştirilir.
```	

  [^2]: [0] bir dizideki ilk öğedir. [1] ikincisidir. Dizi indeksleri **0** ile başlar.

<hr>

Dizinin dışındaki bir dizine erişmeye çalışmak, **tanımsız** değerini döndürür.

```javascript	
var dersler = new Array("HTML", "CSS", "JS"); 

document.write(dersler[10]); // "undefined" döndürür.
```	

`dersler` dizimiz sadece 3 elemana sahip, dolayısıyla 11. eleman olan 10. dizin mevcut değil (yani tanımsız).


