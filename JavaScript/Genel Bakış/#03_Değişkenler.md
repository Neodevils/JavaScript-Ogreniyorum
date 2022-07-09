# Değişkenler

Değişkenler, veri değerlerini depolamak için kapsayıcılardır. Bir değişkenin değeri program boyunca değişebilir.

Bir değişken bildirmek, var anahtar sözcüğünü kullanmak kadar basittir. Örneğin şöyle görünür:

```javascript	
var x = 10;
```

Bu örnekte **x** değişkenine **10** değeri atadık.

Burada kasıtlı olarak atanan kelimeyi kullandık, çünkü JavaScript'te eşittir işareti **(=)** aslında bir *"eşittir"* operatörü yerine **"atama"** operatörü olarak adlandırılır.

Bu, JavaScript'te **x = y**'nin **y** değerini **x** değişkenine atadığı anlamına gelir.[^1]

  [^1]: JavaScript duyarlı bir programlama dilidir, yani büyük/küçük harfe duyarlıdır. Yani **Soyadı** ve **soyadı** gibi değişkenler aynı değildir.

## Değişkenleri Kullanma

Tamam, öğrendiklerimizi bir araya getirelim!

Bir değişkene bir değer atayalım ve tarayıcıya çıktısını alalım. Bu halledebiliriz!

```javascript
var x = 10;
document.write(x);
```

> Ama yine de değişkenlerin tam olarak anlamı nedir ki? 

Programımızda *x* değişkenini içeren **1000** satırlık kod olduğunu hayal edin. Değişkenlerle değişkenlerin değerini değiştirebilir ve bunları kodunuzda birden çok kez kullanabilirsiniz.[^2]

  [^2]: Her yazılı "talimat"a **ifade** denir. JavaScript ifadeleri **noktalı virgülle** ayrılır.

Bunun gibi:

```javascript
var x = 10;
document.write(x);

x = 20;
document.write(x);
```

## Değişkenleri Adlandırma

Birazcık isimler hakkında konuşalım. JavaScript değişken isimlerinin büyük/küçük harfe duyarlı olduğunu hatırlamak çok önemlidir.

Sence, aşağıdaki kodun çıktısı ne olur?

```javascript	
var x = 10;
document.write(X);
```

Doğru! Bir hata çıkacaktır. Bunun nedeni, *x* ve *X*'in farklı olması ve *X* değişkenini bildirmemiş olmamızdır.[^3]

  [^3]: JavaScript kısa çizgi içermeyen bir dildir. Çıkarma işlemleri için ayrılmıştır.

Daha fazla kural için kendini hazırla bence!
- Değişken adının ilk karakteri bir harf, alt çizgi (_) veya dolar işareti ($) **olmalıdır** (Sonraki karakterler harf, rakam, alt çizgi veya dolar işareti olabilir).
- Değişken adının ilk karakteri sayı **olamaz**.
- Değişken adları, adlarında **matematiksel veya mantıksal bir işleç içeremez**. Örneğin, `2*birşey` veya `bu+bu`.
- Değişken isimleri boşluk **içeremez**.
- benim#num, num% vb. gibi özel semboller kullanmanıza izin verilmez.