# JavaScript Yorumları

Çok iyi gidiyoruz! Yakında bir değişken ustası olacaksın. :smile:

Tamam neyse, JavaScript'teki **yorumlar** hakkında konuşalım.

**İfadeleri** biliyoruz, bunlar program çalıştığında "yürütülen" programımızın içindeki talimatlardır.
Fakat! Tüm JavaScript ifadeleri "yürütülmez".

Çift eğik çizgiden `//` sonra veya `/*` ile `*/` arasındaki herhangi bir kod, yorum olarak kabul edilir, yoksayılır ve yürütülmez.

Tek satırlık bir yorum yazmak için çift eğik çizgi kullanırız.[^1] Bunun gibi:

  [^1]: `alert()` bir mesaj kutusu oluşturmak için kullanılır.

```javascript
// Bu bir tek satırlık yorumdur.
alert("Bu bir mesaj kutusu mesajıdır!");
```

> Ama neden asla yürütülmeyecek bir kod yazalım. Bu zaman kaybı olmaz mı?

Hiç de bile! Yorumlar, özellikle büyük işlevlerle ilgili olanlar için iyi bir fikirdir, çünkü kodumuzu başkaları için daha okunabilir hale getirmeye yardımcı olurlar. Bu yüzden kibar olalım ve yorum yapalım!


## Çok Satırlı Yorumlar

> Ya söyleyecek daha çok şeyimiz varsa?

Çok satırlı bir yorum oluşturmak istiyorsak `/*` ile `*/` arasına yazıyoruz.[^2]
Bunun gibi:

  [^2]: Kodun ne yaptığını açıklamak ve açıklamak için yorumları kullanırız.

```javascript
/*
Bu kod 
bir mesaj kutusu
oluşturur.
*/
alert("Bu bir mesaj kutusu mesajıdır!");
```