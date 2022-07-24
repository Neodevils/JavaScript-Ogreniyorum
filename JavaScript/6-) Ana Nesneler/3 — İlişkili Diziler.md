# İlişkisel Diziler

Birçok programlama dili, adlandırılmış dizinlere (sayılar yerine metin) sahip dizileri desteklerken, **ilişkisel diziler** olarak adlandırılan JavaScript'i **desteklemez**.

Ancak yine de bir nesne üretecek olan adlandırılmış dizi sözdizimini kullanabilirsiniz.

**Örneğin:**

```javascript
var kisi = []; // boş dizi
kisi["ad"] = "Neo";
kisi["yaş"] = 20;

document.write(kisi["yaş"]); // 20
```

Artık **kişi** bir dizi olmaktan çok bir nesne olarak ele alınmaktadır.

Adlandırılmış dizinler "ad" ve "yaş" **kişi** nesnesinin özellikleri haline gelir.[^1]

  [^1]: Kişi dizisi bir nesne olarak ele alındığından, standart dizi yöntemleri ve özellikleri yanlış sonuçlar üretecektir. Örneğin, `kisi.length` **0** döndürür.

<hr>

JavaScript'in adlandırılmış dizinlere sahip dizileri **desteklemediğini unutma**.

JavaScript'te diziler her zaman numaralı dizinleri kullanır.

Dizinin bir **dize (metin)** olmasını istediğinizde bir **nesne** kullanmak daha iyidir.

Dizinin bir **sayı** olmasını istediğinizde bir **dizi** kullanın.[^2]

  [^2]: Adlandırılmış bir dizin kullanırsanız, JavaScript diziyi standart bir nesne olarak yeniden tanımlayacaktır.


