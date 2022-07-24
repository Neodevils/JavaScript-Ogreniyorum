# Matematik Nesnesi

**Math** nesnesi, matematiksel görevleri gerçekleştirmene olanak tanır ve çeşitli özellikler içerir.[^1]

| Özellik | Açıklama |
| ------ | ------- |
| **E** | Euler sabitleri |
| **LN2** | 2'nin logaritması |
| **LN10** | 10'un logaritması |
| **LOG2E** | E'nin logaritması |
| **LOG10E** | E'nin logaritması |
| **PI** | Pi sabitleri |
| **SQRT1_2** | 1/2'nin karekökü |

```javascript
document.write(Math.PI); // 3.141592653589793
```

  [^1]: Math'ın yapıcısı yoktur. Önce bir Math nesnesi oluşturmaya gerek yoktur.

## Matematik Nesne Yöntemleri

Math nesnesi, hesaplamalar için kullanılan birkaç yöntem içerir[^2]

| Yöntem | Açıklama |
| ------ | ------- |
| **abs(x)** | Sayının mutlak değeri |
| **acos(x)** | Arccosinüsü |
| **asin(x)** | Arcsinüsü |
| **atan(x)** | Arctanısı |
| **atan2(y, x)** | Arctanısı |
| **ceil(x)** | Sayının yukarı kırpılmış değeri |
| **cos(x)** | Cosinüsü |
| **exp(x)** | E'nin üsü |
| **floor(x)** | Sayının aşağı kırpılmış değeri |
| **log(x)** | Logaritması |
| **max(x, y)** | En büyük sayı |
| **min(x, y)** | En küçük sayı |
| **pow(x, y)** | Üsü |
| **random()** | Rastgele sayı |
| **round(x)** | Sayının yuvarlanmış değeri |
| **sin(x)** | Sinüsü |
| **sqrt(x)** | Karekökü |
| **tan(x)** | Tanjantı |

```javascript	
var rakam = Math.sqrt(4); 

document.write(rakam); // 2 (4'in karekökü)
```

  [^2]: 1-10 arasında rastgele bir sayı elde etmek için, size 0-1 arasında bir sayı veren Math.random()'u kullanın. Ardından sayıyı 10 ile çarpın ve ardından Math.ceil()'i ondan alın: Math.ceil(Math.random() * 10).

<hr>

Kullanıcıdan bir sayı girmesini ve karekökünü uyarmasını isteyen bir program oluşturalım.[^3]

```javascript	
var n = prompt("Lütfen bir sayı gir.", "4");
var cevap = Math.sqrt(n);

alert( n + "sayısının karekökü: " + cevap); 
```

  [^3]: Matematik kullanışlı bir nesnedir. Her seferinde kendi fonksiyonlarınızı yazmak yerine Math kullanarak çok zaman kazanabilirsiniz.

  
