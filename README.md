# CurrencyTracker – Döviz Takip Konsol Uygulaması

## Öğrenci Bilgileri
- **Ad Soyad:** Efe Düzçay  
- **Öğrenci Numarası:** 20230108057 

Bu proje, Türk Lirası (TRY) bazlı döviz kurlarını takip etmek amacıyla geliştirilmiş bir C# konsol uygulamasıdır. Uygulama, Frankfurter FREE API üzerinden canlı döviz verilerini alır, bu verileri hafızada tutar ve LINQ kullanarak çeşitli sorgular yapılmasını sağlar.

Uygulamanın amacı; bir finans firmasının TRY bazlı döviz kurlarını konsol üzerinden görüntüleyebilmesi, filtreleyebilmesi, sıralayabilmesi ve istatistiksel özet alabilmesidir.

Projede C# Console Application yapısı kullanılmıştır. API çağrıları HttpClient ile yapılmış, asenkron yapı için async/await kullanılmıştır. Döviz verileri List<Currency> yapısında tutulmuş ve tüm işlemler LINQ kullanılarak gerçekleştirilmiştir.

Kullanılan API:
https://api.frankfurter.app/latest?from=TRY

Uygulama çalıştığında aşağıdaki menü kullanıcıya sunulur:

===== CurrencyTracker =====  
1. Tüm dövizleri listele  
2. Koda göre döviz ara  
3. Belirli bir değerden büyük dövizleri listele  
4. Dövizleri değere göre sırala  
5. İstatistiksel özet göster  
0. Çıkış  

Menü seçenekleri şu işlemleri yapar:
- Tüm dövizleri listeleme işlemi LINQ Select kullanılarak yapılır.
- Döviz koduna göre arama işlemi LINQ Where ile yapılır ve büyük/küçük harf duyarsızdır.
- Belirli bir değerden büyük dövizler LINQ Where kullanılarak listelenir.
- Dövizler değere göre LINQ OrderBy veya OrderByDescending ile sıralanır.
- İstatistiksel özet kısmında toplam döviz sayısı, en yüksek kur, en düşük kur ve ortalama kur LINQ Count, Max, Min ve Average kullanılarak hesaplanır.

Projede hard-coded veri kullanılmamıştır. Tüm veriler canlı olarak API üzerinden alınmaktadır. LINQ kullanılmadan yapılmış herhangi bir çözüm bulunmamaktadır. GUI kullanılmamış, yalnızca konsol uygulaması geliştirilmiştir.

Projeyi çalıştırmak için proje klasöründe terminal açılarak aşağıdaki komutlar sırasıyla çalıştırılmalıdır:

dotnet restore  
dotnet build  
dotnet run  

Uygulama çalıştıktan sonra işlemler konsol menüsü üzerinden yapılabilir.
