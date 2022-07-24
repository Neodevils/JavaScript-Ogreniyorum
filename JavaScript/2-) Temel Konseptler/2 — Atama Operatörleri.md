# Atama Operatörleri

Çok mantıklı bir şekilde adlandırılmış operatörler dizisinin bir sonraki adımı... **Atama operatörleri!**

Tahmin ettiniz gibi, bunları JavaScript değişkenlerine değer atamak için kullanıyoruz.[^1]

| Operatör | Örnek | Şuna eşdeğerdir |
| -------- | ---- | -------- |
| = | x = y | x = y |
| += | x += y | x = x + y |
| -= | x -= y | x = x - y |
| *= | x *= y | x = x * y |
| /= | x /= y | x = x / y |
| %= | x %= y | x = x % y |

  [^1]: Bir satırda `x -= y += 9` gibi birden çok atama operatörü kullanabilirsiniz.

```javascript
var sayı = 10;
sayı *= 9;
console.log(sayı); // 90
```
