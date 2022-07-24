## Çıktı

Tarayıcıya "Merhaba Dünya" yazdırmak için JavaScript kullanalım. İşte böyle görünecek.

```html
<script>
  document.write("Merhaba Dünya!");
</script>
```

Orada bazı ekstra şeyler fark ettin mi? Senden de birşey kaçmıyor!

`document.write()` işlevini tanıtma zamanı. HTML belgemize metin yazmak için kullanmamız gereken şey budur.[^1]

  [^1]: Dikkatli ol! `document.write()` yalnızca test için kullanılmalıdır. Diğer bazı çıktı mekanizmalarını çok yakında ele alacağız.

Keyifli mi hissediyorsun? Tabiki öyle hissedeceksin! Çıktıdaki görünüm metnini özelleştirmek için standart HTML biçimlendirme dilini de kullanabilirsin:

```html
<script>
  document.write("<h1>Merhaba Dünya!</h1>");
</script>
```

## Konsola Çıktı Yazma

Doğru, artık `document.write()` ile HTML çıktısı yazma konusunda uzmanız :smile:.

Farklı bir çıktı türü zamanı. Tarayıcı konsolunun çıktısını öğrenelim.

Bunun için güvenilir *`console.log()`* işlevine ihtiyacımız olacak.[^2]

  [^2]: Geliştiriciler, JavaScript kodlarını test etmek için çoğunlukla konsolu kullanır.

> Bekle, o kadar acele etme ya! Bahsettiğin şu konsol nedir?

Konsol, web tarayıcısının bir parçasıdır ve mesajları günlüğe kaydetmene, JavaScript kodunu çalıştırmana, hataları ve uyarıları görmene olanak tanır.

Örneğin şu:

```javascript
console.log('Merhaba.');
```
