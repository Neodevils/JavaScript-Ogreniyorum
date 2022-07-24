# Form Doğrulama

HTML5, form doğrulamaya izin veren bazı özellikler ekler. Örneğin, **zorunlu** öznitelik, doldurulmasını zorunlu kılmak için bir giriş alanına eklenebilir.

JavaScript kullanılarak daha karmaşık form doğrulaması yapılabilir. 🤫

Form öğesi, doğrulama gerçekleştirmek için işlenebilecek bir `onsubmit` olayına sahiptir.

Örneğin iki girişli ve bir butonlu bir form oluşturalım. Doğrulamayı geçmek için her iki alandaki metin aynı olmalı ve boş olmamalıdır.

```html 
<form onsubmit="return ayniYazi()" method="post">
  Yazı: <input type="text" name="num1" id="num1"/>
  <br/>
  
  Tekrarla: <input type="text" name="num2" id="num2"/>
  <br/>
  
  <input type="submit" value="Doğrula"/>
</form>
```

Şimdi `ayniYazi()` fonksiyonunu tanımlamamız gerekiyor:

```javascript
function ayniYazi() {
  
  // Yazıları değişkenlerde depoluyoruz.
  var n1 = document.getElementById('num1');
  var n2 = document.getElementById('num2');
  
  // n1 değerli ve n1 ile n2'nin değeri eşitse true değerini döndürüyoruz.
  if(n1.value && n1.value == n2.value) {
    return true;
  }
  
  // Degilse...
  alert("Kutucuklar aynı olmalı ve boş bırakılmamalıdır.");
  
  return false;
}
```

Yalnızca değerler boş olmadığında ve eşit olduğunda **`true`** değerini döndürür.[^1]

  [^1]: **onsubmit** olayı `false` döndürürse form gönderilmez.
  
