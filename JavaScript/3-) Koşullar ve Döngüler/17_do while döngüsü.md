# do...while (yaparken) Döngüsü

Döngülerle işin neredeyse bitti! Harika gidiyorsun! 😀

Bu modülde incelediğimiz son döngü `do...while` döngüsüdür, *while* döngüsünün bir çeşididir ancak önemli bir fark vardır.

Bu döngü, koşulun doğru olup olmadığını **kontrol etmeden önce** kod bloğunu bir kez çalıştıracak ve ardından koşul doğru olduğu sürece döngüyü tekrarlayacaktır.[^1]

**İşte Sözdizimi:**

```javascript	
do {
  // Kod bloğu
}
while (koşul);
```

  
  [^1]: **do...while** döngüsünün sonunda kullanılan *noktalı virgüle* dikkat edin. Bu önemlidir.

Bir örnekle başlayalım:

```javascript
var i=20;

do {
  document.write(i + "<br />"); // Alt alta 20, 21, 22, 23, 24, 25 yazar.

  i++;  
}
while (i<=25); 
```

*Bu örnek, 20'den 25'e kadar sayıları yazdırır.*[^2]

  [^2]: Kod bloğu koşul test edilmeden önce yürütüldüğünden, koşul yanlış olsa bile döngü her zaman **en az bir kez yürütülür**.

