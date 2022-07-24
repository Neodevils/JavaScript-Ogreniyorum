# Diziler Oluşturma

Bu arada, bir dizi bildirebilir, depolayacağı öğe sayısını söyleyebilir ve öğeleri daha sonra ekleyebilirsin.[^1]

```javascript
var dersler = new Array(3);
dersler[0] = "HTML";
dersler[1] = "CSS";
dersler[2] = "JS";

document.write(dersler[2]); // JS yazdırır.
```

  [^1]: Dizi, özel bir **nesne** türüdür. Bir dizi, öğelerine erişmek için **sayıları** kullanır, üyelerine erişmek için ise **adları** kullanır.

<hr>

JavaScript dizileri dinamiktir, bu nedenle bir dizi bildirebilir, `Array()` yapıcısıyla herhangi bir argüman iletemezsin. Ama daha sonra öğeleri dinamik olarak ekleyebilirsin.[^2]

```javascript
var dersler = new Array();
dersler[0] = "HTML";
dersler[1] = "CSS";
dersler[2] = "JS";
dersler[3] = "C++";

document.write(dersler[2]); // JS yazdırır.
```

  [^2]: İstediğin kadar eleman ekleyebilirsin.

## Dizi Değişmezi

Daha fazla basitlik, okunabilirlik ve yürütme hızı için, **dizi değişmezi** sözdizimini kullanarak dizileri de bildirebilirsin.

```javascript	
var dersler = ["HTML", "CSS", "JS"]; 

document.write(dersler[2]); // JS yazdırır.
```

Bu, **new Array()** sözdizimi ile oluşturulan diziyle aynı diziyle sonucu verir.[^3]

  [^3]: Daha önce yaptığımız gibi dizin numarasını kullanarak dizinin öğelerine erişebilir ve bunları değiştirebiliriz. Dizi değişmez sözdizimi, dizileri bildirmek için önerilen yoldur.

