# Görüntü Kaydırıcısı

Şimdi örnek bir resim kaydırıcı projesi oluşturabiliriz. Görüntüler "İleri" ve "Önceki" düğmeleri kullanılarak değiştirilecektir.

Şimdi, bir resim ve iki gezinme düğmesi içeren sayfamızı oluşturalım:

* HTML

```html
<!DOCTYPE html>
<html>
  <head>
    <meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
    
    <title>Page Title</title>
  </head>
  
  <body>
    <div>
      <button> Önceki </button>
        
      <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTjdJH9lihC1qeHgf7xEff3rAQuG2AF6WvXIA&usqp=CAU" width="200px" height="100px" />
        
      <button> Sonraki </button>
    </div>
  </body>
</html>
```

* CSS

```css
button {
  margin-top: 30px;
  float: left;
  height: 50px;
}

img {
  float: left;
  margin-right: 10px;
  margin-left: 10px;
}
```

Ardından örnek resimlerimizi bir dizide tanımlayalım[^1]

```javascript
var resimler = [
  "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTjdJH9lihC1qeHgf7xEff3rAQuG2AF6WvXIA&usqp=CAU", 
  "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSaRG5-CeuHB0Ww4lQVeuv6fnNLolKdOcRWNg&usqp=CAU", 
  "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQwd3jOzwSM4qN9-B21wZ7OF-pl8uNim3V06g&usqp=CAU"
];
```

  [^1]: İstediğiniz sayıda görsel kullanabilirsiniz.
  
## Görüntü Kaydırıcı

Şimdi, Sonraki ve Önceki düğme tıklamalarını ele almamız ve görüntüyü değiştirmek için ilgili işlevleri çağırmamız gerekir.

* HTML

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
    <meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
    <link rel="stylesheet" href="style.css">
    <script src="script.js"></script>
  </head>
  
  <body>
    <div>
      <button onclick="onceki()"> Önceki </button>
      <img id="kaydirici" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTjdJH9lihC1qeHgf7xEff3rAQuG2AF6WvXIA&usqp=CAU" 
        width="200px" height="100px"/>
      <button onclick="sonraki()"> Sonraki </button>
    </div>
  </body>
</html>
```

* CSS
 
```css
button {
  margin-top: 30px;
  float: left;
  height: 50px;
}

img {
  float: left;
  margin-right: 10px;
  margin-left: 10px;
}
```

* JS

```javascript
var resimler = [
  "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTjdJH9lihC1qeHgf7xEff3rAQuG2AF6WvXIA&usqp=CAU", 
  "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSaRG5-CeuHB0Ww4lQVeuv6fnNLolKdOcRWNg&usqp=CAU", 
  "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQwd3jOzwSM4qN9-B21wZ7OF-pl8uNim3V06g&usqp=CAU"
];

var numara = 0;

function sonraki() {
  var kaydirici = document.getElementById('kaydirici');
  
  numara++;
  
  if(numara >= resimler.length) {
    numara = 0;
  }
  
  kaydirici.src = resimler[numara];
}

function onceki() {
  var kaydirici = document.getElementById('kaydirici');
    
  numara--;
    
  if(numara < 0) {
    num = resimler.length-1;
  }
  
  kaydirici.src = resimler[numara];
}
```

**numara** değişkeni geçerli görüntüyü tutar. Sonraki ve önceki düğme tıklamaları, görüntünün kaynağını dizideki sonraki/önceki görüntüye değiştiren, karşılık gelen işlevleri tarafından işlenir.[^2]

  [^2]: Çalışan bir görüntü kaydırıcısı oluşturduk! Harika değil mi? 🤭

