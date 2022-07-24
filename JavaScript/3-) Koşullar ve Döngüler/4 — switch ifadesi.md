# `swtich` geçiş ifadesi

Peki ya birden fazla koşul için test yapmanız gerekirse? Bu durumlarda, her koşul için **if else** ifadesi yazmak en iyi çözüm olmayabilir.

Bunun yerine, farklı koşullara göre farklı eylemler gerçekleştirmek için **switch** ifadesini kullanabiliriz.

İşte neye benzediğini göstereyim:
  
```javascript 
switch (koşul) {
  case ilk: 
    // ifadeler
    break;
  case ikinci: 
    // ifadeler
    break;

  default: 
    // ifadeler
}
```

Switch ifadesi bir kez değerlendirilir. İfadenin değeri, her bir **durum**un değerleri ile karşılaştırılır ve eğer bir eşleşme varsa, o kod bloğu yürütülür.[^1]

  [^1]: Aynı sonucu birden fazla *if...else* ifadesi ile elde edebilirsin, ancak *switch* ifadesi bu gibi durumlarda daha etkilidir.

<hr>

Bir örnek ile ele alalım:

```javascript
var gün = 2;

switch (gün) {
  case 1:
    document.write("Pazartesi");
    break;
  case 2:
    document.write("Salı"); // Web Sayfasına "Salı" yazılır.
    break;
  case 3:
    document.write("Çarşamba");
    break;

  default:
    document.write("Başka bir gün");
}
```

Basit, değil mi?[^2] 🙃

[^2]: İstediğin kadar **case** ifadesi ekleyebilirsin.

## break (ara) Anahtar Kelimesi

Böylece *switch* ifadesinin bir kod bloğunu test ettiğini öğrendik, ancak her zaman tüm bloğu test etmesini istemeyeceğiz. **break** anahtar sözcüğü aslında **switch** ifadesini kapatır.

**switch** bloğunu durdurmak, blok içinde daha fazla kod ve **durum** yürütülmesini durdurur.[^3]

  [^3]: Genellikle, her durum ifadesinde bir **ara** verilmelidir.

## default (varsayılan) Anahtar Kelimesi

Çoğu zaman eşleşme olmaz, ancak yine de bir şey çıktısı için programa ihtiyacımız var... bunun için, büyük/küçük harf eşleşmesi olmadığında çalıştırılacak kodu belirten **varsayılan** anahtar kelimeyi kullanırız.[^4]

Bunun gibi:

```javascript
var renk ="sarı";
switch(renk) {
  case "mavi": 
    document.write("Bu mavidir.");
    break;
  case "kırmızı":     
    document.write("Bu kırmızıdır.");
    break;
  case "yeşil": 
    document.write("Bu yeşildir.");    
    break;
  case "turuncu":  
    document.write("Bu turuncudur."); 
    break;

  default: 
    document.write("Renk bulunamadı.");
}
```

  [^4]: Eşleşme bulunmadığında **durum**u ele almaya gerek yoksa, **varsayılan** blok atlanabilir.

