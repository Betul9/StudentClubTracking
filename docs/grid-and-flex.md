# Grid & Flex

Projede çalışırken grid ve flex yapılarına genel bir bakış atalım:

- **Grid:** Bir sayfada satır ve sütunlardan oluşturulmak istenen bir alan varsa kullanılır.
- **Flex:** Bir sayfada yalnızca satırlar üzerinde çalışılacak ise kullanılır.

Bu iki yapıyı projede class kavramına şöyle yerleştirdik:

-----

## 1) Group

Group aslında grid ile aynı işi yapıyor. 1-12 arasında değerler alabilir:

### group-${number}

```html
<div class="group-4">
    <div class="col">Test</div>
    <div class="col">Test 2</div>
    <div class="col">Test 3</div>
    <div class="col">Test 4</div>
    <div class="col">Test 5</div>
    <div class="col">Test 6</div>
    <div class="col">Test 7</div>
    <div class="col">Test 8</div>
    <div class="col">Test 9</div>
    <div class="col">Test 10</div>
    <div class="col">Test 11</div>
    <div class="col">Test 12</div>
</div>
```

İçerisine sonsuz sayıda div alabilir ama her 4 tanede bir alt satıra geçer. Otomatik olarak eşit bölümlere ayırır.

Dikkat: Buradaki number ibaresi 1-12 arasında değerler alır.

### group-gap-${number}

Bu gruplar arasında boşluk bırakmak isteyebiliriz. Genel tüm boşluk alanlarında kullanılan standart kural spaces.md dosyasında mevcut. Yine de şöyle bir kullanımı vardır:

```html
<div class="group-5 group-gap-15">
    <div class="col">Test</div>
    <div class="col">Test 2</div>
    <div class="col">Test 3</div>
    <div class="col">Test 4</div>
    <div class="col">Test 5</div>
    <div class="col">Test 6</div>
    <div class="col">Test 7</div>
    <div class="col">Test 8</div>
    <div class="col">Test 9</div>
    <div class="col">Test 10</div>
    <div class="col">Test 11</div>
    <div class="col">Test 12</div>
</div>
```

Örneğin burada her col arasına 15px boşluk bırakacaktır.

### Responsive

Farklı ekran boyutları için kullanırken **m, mh, t, l ve d** isimlendirmelerini kullanabilirsiniz.

```html
<div class="group-m-1 group-mh-2 group-t-3 group-l-6 group-8">
    <div class="column">Mert</div>
    <div class="column">Mert</div>
    <div class="column">Mert</div>
    <div class="column">Mert</div>
    <div class="column">Mert</div>
    <div class="column">Mert</div>
    <div class="column">Mert</div>
    <div class="column">Mert</div>
    <div class="column">Mert</div>
    <div class="column">Mert</div>
    <div class="column">Mert</div>
    <div class="column">Mert</div>
    <div class="column">Mert</div>
    <div class="column">Mert</div>
    <div class="column">Mert</div>
    <div class="column">Mert</div>
</div>
```

Bu örnek için;

- Mobil Cihazlarda (0-576px) : Bir satırda 1 tane gözükecektir.
- Mobil Yatay Olduğunda (576px-768px) : Bir satırda 2 tane gözükecektir.
- Tabletlerde (768px - 992px) : Bir satırda 3 tane gözükecektir.
- Laptoplarda (992px - 1200px) : Bir satırda 6 tane gözükecektir.
- Daha büyük ekranlarda (>1200px) : Bir satırda 8 tane gözükecektir.

---

## 2) Row

Row, flex'i temel almaktadır. Bir satır üzerinde işlemler yapmanızı sağlar.

Herhangi bir ekstra sayı girilmesine gerek yoktur. Tüm elemanlar tek satırda gözükür!

#### row

row'da tüm divler toplamda parent'ın genişliği kadar büyür.

```html
<div class="row">
    <div class="col2">Test 1</div>
    <div class="col2">Test 2</div>
    <div class="col2">Test 3</div>
    <div class="col2">Test 4</div>
    <div class="col2">Test 5</div>
</div>
```

Tüm hepsi yan yana gözükecektir.

#### row-fluid

row-fluid için içteki col divinin genişliğinden sonra devam eder, otomatik olarak tüm alanı doldurmaya çalışmaz. Dolayısıyla row-fluid ile birlikte space-between gibi özellikleri kullanabilirsiniz.

```html
<div class="row-fluid">
    <div class="col2">Test </div>
    <div class="col2">Test 2</div>
    <div class="col2">Test 2</div>
    <div class="col2">Test 2</div>
    <div class="col2">Test 2</div>
</div>
```

#### justify-content

flex için var olan justify-content özelliğini **jc** class'ı ile kullanabilirsiniz:

```html
<div class="row-fluid jc-center">
    ...
</div>
```

#### align-items

flex için var olan align-items özelliğini **ai** class'ı ile kullanabilirsiniz:

```html
<div class="row-fluid ai-center">
    ...
</div>
```