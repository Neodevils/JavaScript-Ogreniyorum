# Nitelikleri Değiştirme

Çalışmak istediğiniz eleman(lar)ı seçtikten sonra niteliklerini değiştirebilirsiniz.

Önceki derslerde gördüğümüz gibi **innerHTML** özelliğini kullanarak bir elemanın metin içeriğini değiştirebiliriz.

Benzer şekilde, öğelerin niteliklerini de değiştirebiliriz.

Örneğin, bir görüntünün **src** niteliğini değiştirebiliriz:

```html	
<img id="fotom" src="portakal.png" alt="" />

<script>
  var element = document.getElementById("fotom");

  element.src = "elma.png";
</script>
```

Bir bağlantının **href** niteliğini değiştirebiliriz:

```html	
<!DOCTYPE html>
<html>

  <head>
    <title>Sayfa Başlığı</title>
  </head>

  <body>
    <a href="http://www.ornek.com">Bir link.</a>
  </body>

</html>

<script>
window.onload = function() {
  var element = document.getElementsByTagName('a');

  element[0].href= 'https://discord.gg/AzmQGCyk';
} //HTML'nin yüklendiğinden emin olmak için window.onload'da işlevi çağırma
</script>
```

> Pratik olarak bir elemanın tüm nitelikleri JavaScript kullanılarak değiştirilebilir.

## Stil Değiştirme

HTML öğelerinin stili, JavaScript kullanılarak da değiştirilebilir.

Tüm stil niteliklerine, öğenin **style** nesnesi kullanılarak erişilebilir.

**Örneğin:**

```html	
<!DOCTYPE html>
<html>

  <head>
    <title>Page Title</title>
  </head>

  <body>
    <div id="demo" style="width: 200px">biraz metin</div>
  </body>

  <script>
    window.onload = function() {
      var x = document.getElementById("demo");

      x.style.color = '#FF0000';
      x.style.width = '100px';
    }; //Yazı rengini kırmızı yapıp genişliğini 100px yapmak için window.onload'da işlevi çağırdık
  </script>
</html>
```

Yukarıdaki kod, div öğesinin **metin rengini** ve **genişliğini** değiştirir.[^1]

  [^1]: Tüm CSS özellikleri JavaScript kullanılarak ayarlanabilir ve değiştirilebilir. Özellik adlarında tire (-) kullanamayacağınızı unutmayın: bunlar, bileşik sözcüklerin büyük harfle başladığı camelCase sürümleriyle değiştirilir. Örneğin: **background-color** özelliği, **backgroundColor** olarak adlandırılmalıdır.


