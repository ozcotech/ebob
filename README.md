# Udemy 54.Ders Ödev-2

## Girilen 2 Sayının En büyük Ortak Bölenini Bulan Program

* Kullanıcıdan 2 tane sayı alarak bu sayıların en büyük ortak bölenini (EBOB) dönen bir tane fonksiyon yazacağız.
* İlk önce 2 tane sayı alıyoruz.
* Daha sonra fonksiyonlarımızı oluşturuyoruz, 2 farklı sayı için 2 farklı fonksiyon oluşturduk, muhtemelen tek fonksiyonla da bu yapılabilir ancak şimdilik 2 farklı sayının bölenlerini çıkarabilmek için 2 farklı liste oluşturarak algoritmamı tasarladım o yüzden 2 farklı fonksiyon ortaya çıktı.
```
list1 =[]

for i in range(1,sayi+1):
  if (sayi % i == 0):
    list1.append(i)
print(list1)
```
Yukarıdaki kodu şu şekilde kısalttım (<b>List Comprehension</b>);
```
list1 = [i for i in range(1,sayi+1) if sayi % i == 0]
print(list1)
```
* Burada 1'den başladım 2 sayısından da başlanabilir.
* Buradaki olay şu; 1'den girilen sayıya kadar listenin içinde gez gezerken bölenlerini çıkar ve bu bölenleri boş bir listeye ekle.
* Bu kodlarla 2 farklı fonksiyon oluşturdum, daha sonra kolayca çağırmak için. Buradaki amaç; girilen sayının bölenlerini listelemek.
* Daha sonra bu 2 liste (bölenler listesi) arasında gezinti yaparak ortak olanları ayrı bir listede listeledim.
* İlk önce şöyle kodlamıştım;
```
list3 = []
for i in bolen1():
  for j in bolen2():
    if (i == j):
      list3.append(i)
```
*Daha sonra bunu da bir fonksiyona ekleyeyim ve bu fonksiyonu da <b>*list comprehension*</b> yöntemiyle kodlayayım dedim.
O da şöyle oldu;
```
def ortak ():
  list3 = [j for i in bolen1() for j in bolen2() if i == j]
  return list3
```
* Bu fonksiyonlardaki <b>*return*</b> ifadesini unutmamak lazım yoksa <b>*none*</b> sonucunu alırsın.
* Bu son fonksiyondaki olay şu; bölenlerini listele, listelerin içinde gez, bu iki listede olan ortak elemanları da ayrı bir listeye ekle, tabi bu ayrı liste baştan boş olmalı.
* Son olarak da çıktı alırken <b>print()</b> fonksiyonun içerisinde <b>ortak()</b> fonksiyonunu çağırarak , o fonksiyonda <b>pop()</b> fonksiyonunu kullandık, yani <b>pop()</b> fonksiyonu içerisine sayı yazmazsak yani kaçıncı elemanı çıkarmak istediğimizi söylemezsek listedeki son elemanı çıkarır ve bize gösterir. (Tabiki <b>print()</b> fonksiyonun içinde kullandığımız için.)