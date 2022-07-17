# DOM

Herhangi bir web sayfasını bir tarayıcıda açtığınızda, sayfanın HTML'si yüklenir ve ekranda görsel olarak oluşturulur.

Bunu başarmak için tarayıcı, mantıksal yapısının nesne yönelimli bir modeli olan o sayfanın Belge Nesne Modelini oluşturur.[^1]

Bir HTML belgesinin DOM'si iç içe kutular kümesi olarak temsil edilebilir:

![Örnek](https://media.discordapp.net/attachments/861208192121569280/998183791245938738/HTML_DOM.excalidraw_1.png?width=798&height=498)

  [^1]: JavaScript, öğeleri eklemek, silmek ve değiştirmek için bir sayfanın DOM'sini dinamik olarak değiştirmek için kullanılabilir.

## DOM Ağacı

DOM, bir belgeyi bir ağaç yapısı olarak temsil eder.

HTML öğeleri, ağaçta birbiriyle ilişkili **düğümler** haline gelir.

Ağaçtaki tüm bu düğümlerin kendi aralarında bir tür ilişkileri vardır.

Düğümlerin **alt düğümleri** olabilir. Aynı ağaç seviyesindeki düğümlere **kardeş** denir.[^2]

Örneğin, aşağıdaki yapıyı göz önünde bulunduralım:

![Örnek](https://media.discordapp.net/attachments/861208192121569280/998183791245938738/HTML_DOM.excalidraw_1.png?width=798&height=498)

Yukarıdaki örnek için:

```html
<html>'nin iki çocuğu var (<head> ve <body>);
<head>'in bir çocuğu (<title>) ve bir ebeveyni (<html>) var;
<title>'ın bir ebeveyni (<head>) var ve çocuğu yok;
<body>'nin iki çocuğu (<h1> ve <a>) ve bir ebeveyni (<html>) var;
```

  [^2]: Bir HTML belgesindeki öğeler arasındaki ilişkileri JavaScript ile manipüle edebilmek için anlamak önemlidir.

## Belge Nesnesi

JavaScript'te, DOM'daki tüm öğelere erişmek için kullanılabilecek önceden tanımlanmış bir **belge** nesnesi vardır.

Başka bir deyişle, **document** (belge) nesnesi, web sayfanızdaki tüm nesnelerin sahibidir (veya köküdür).

Bu nedenle, bir HTML sayfasındaki nesnelere erişmek istiyorsanız, her zaman belge nesnesine erişmekle başlarsınız.

**Örneğin:**

```javascript
document.body.innerHTML = "Birazcık metin";
```

Gövde DOM'nin bir öğesi olduğundan, ona **document** nesnesini kullanarak erişebilir ve **innerHTML** özelliğinin içeriğini değiştirebiliriz.[^3]

  [^3]: **innerHTML** özelliği, içeriğini değiştirmek için hemen hemen tüm HTML öğelerinde kullanılabilir.



