# Safebox-Staj-Odev-3

Analitik işlemler SQL seviyesinde karmaşık raporlar oluşturmamıza olanak sağlayan işlemlerdir.Bu fonksiyonlar sayesinde daha az karmaşık sorgular oluşturarak istenilen raporlar elde edilir ve daha fazla performanslı sorgular elde edilir. Analitik fonksiyonlar genellikle aggregate fonksiyonlarla karıştırılır. Aggregate fonksiyonlarda GROUP BY ifadesi kullanılmak zorundadır. Analitik fonksiyonda böyle bir zorunluluk yoktur. Ayrıca aggreagate fonksiyonlar her bir grup için 1 satır sonuç üretirken analitik fonksiyonda toplam satır sayısı değişmiyor.
Şimdi örneklere geçelim : 
Örnek 1: Eğitimde bize verilen dvdrental datasetinde SELECT *, ROW_NUMBER() OVER(PARTITION BY category_id, ORDER BY film_id) FROM film_category; fonksiyonu analitik bir fonksiyondur ve category_id leri pencereleyerek o penceredeki film_id leri sıralar.
Örnek 2:DVDRENTAL.tar dosyasında içerisinde bulunan Film Tablosu bulunan "length" grup hakkında çalışma yaptım . 
Agg fonksiyonların içinde bulunan 'avg' fonksiyonu kullandım. Filmlerin ortalama uzunlukları buldum. Ve grubun ismini değiştirdim.
select avg (length) as uzunluk  from film ;
Örnek 3:dvdrental.tar dosyasının içindeki örneklerde bulunan "payment" tablosu üzerinden ROUND fonksiyonu kullanım örneğinde bulundum.
select payment_id, ROUND(amount,0) as FİYAT_YUVARLAMA
from payment;
Bu sayede amount yani fiyat kolonunun içindeki ondalıklı sayıları virgülden sonrasını almadan yuvarlayabiliyoruz. Örneğin 0,99 olan herhangi bir ürünün fiyatı yuvarladığımızda 1 olarak gözükür. Bu bize işlem kolaylığı sağlar.
