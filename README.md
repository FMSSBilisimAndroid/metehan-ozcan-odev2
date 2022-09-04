# A basic Authentication UI
![Cover](https://user-images.githubusercontent.com/70481060/188327732-3f314b4c-af31-4e81-a977-4c8e4f7e5cee.jpg)

`This application is an example of an authentication activity, with Material Components and Jetpack DataStore.`


# Eager Loading vs  Lazy Loading 
Eager , bir değişkene bir ifade atadığınızda, ifadenin hemen değerlendirildiği ve değişkenin değerinin ayarlandığı anlamına gelir.
Lazy ise yalnızca değere ihtiyaç duyulmadan önce mümkün olan en son anda değerlendirme yapar. Değere hiç erişmezseniz, değeri belirleyen kod asla çalıştırılmaz.
Birçok fonksiyonel programlama dilinde eager varsayılandır. Lazy operatörlerin ise en son ana kadar bekleme eğiliminde olduğunu söylemek yeterlidir.
Eager Loading nesneleri hemen yaratır ve kullanmak için bekletir.
Nesne oluşturma, kurucu çağrıldığında o sınıfta tanımlanan tüm public ve private özellikleri başlattığı için ağır bir süreç olduğundan,
Kotlin'in gerektiğinde özellikleri daha sonra başlatmak için birkaç yolu vardır. Lateinit veya lazy olarak bunları tanımlayabiliriz.
Lazy Loading bir öğenin çağıralmasını geciktirir öğeye ihtiyaç duyana kadar çağırılmaz. Tüm veri bir anda çekilmez parça parça verileri çeker.


## Peki bu kotlinde nasıl kullanılır?
Verileri dönüştürmek, filtrelemek, manipüle etmek ve veriler üzerinde işlem yapmak her geliştiricinin neredeyse her gün işinde yaptığı şeydir. 
Uygulamalarınızı yazmak için Kotlin kullanıyorsanız, bir koleksiyonu bir formdan diğerine dönüştürmek için map veya filter operatörünü kullanmış olabilirsiniz.

Kotlin.collections paketi ile birlikte Kotlin, bir veri koleksiyonunu lazy bir şekilde temsil etmek ve değerlendirmek için bir yol da sağlar. 
Bu, Sequences kullanılarak gerçekleştirilir.

Peki Lazy Sequences'in Eager olarak nitelendirdiğimiz Iterable'dan farkı nedir?


### Eager Iterable List
Kotlin resmi dokümantasyonunda anlatıldığı üzere aşağıdaki kod parçasını iterable bir şekilde filtreleyip 3 karakterden uzun ilk 4 kelimeleri filtreliyor.
Tüm işlemi yapması 23 adım sürüyor.

![image](https://user-images.githubusercontent.com/70481060/188328818-efcde022-6956-487c-8e46-6b00f76b8869.png)
![list-processing](https://user-images.githubusercontent.com/70481060/188328784-45cee719-8ffc-4368-bf48-688f54919b88.png)

### Lazy Sequences
Ancak Sequences verileri eager aksine toptan değil öğeleri tek tek alıp tüm işlemleri öğe üzerinde yapacağı 23 adımda yapılan filtreleme işleminin 18 adıma indiğini görüyoruz.

![image](https://user-images.githubusercontent.com/70481060/188328949-b4c45e9f-1da9-42df-a49b-6c1ff0db0f70.png)
![sequence-processing](https://user-images.githubusercontent.com/70481060/188328962-b0b332e3-f990-4091-81dd-f7a795d6b9bd.png)

