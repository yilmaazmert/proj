# Canlı Kodlama

Sonic Pi'ın en eğlenceli yönlerinden biri de size canlı bir şekilde müzik yazma ve değiştirme fırsatı vermesi, canlı bir gitar performansı gibi. Canlı kodlamanın öbür avantajı ise müziği oluştururken geri bildirim alabilmek (örneğin basit bir döngü yaratıp ses istediğiniz hale gelene kadar üzerinde oynamak gibi). Ancak, asıl avantajı sahneye Sonic Pi ile çıkıp ortamı hareketlendirmeye başlayabilmeniz.

Bu bölümde kodunuzu dinamik performanslara çevirmenin gerekliliklerini göreceğiz.

Sıkı tutunun...

Evet şu an eğlenebilmemizi sağlayacak kadar Sonic Pi öğrendik. Bu bölümde önceki bütün bölümlerden parçalar alıp sizin canlı olarak kendi müziğinizi bestelemenizi ve bunu bir şova çevirmenizi sağlayacağız. Bunun için 3 ana unsura ihtiyacımız var:

  - Ses oluşturan kod yazma becerisi - Hazır!
  - Fonksiyon yazma becerisi - Hazır!
  - Adlandırılmış "thread" kullanma becerisi - Hazır!

Tamamdır, hadi başlayalım. İlk seslerimizi canlı kodlayalım. Öncelikle çalmak istediğimiz kodu içeren bir fonksiyona ihtiyacımız var. Ayrıca bu fonksiyonu çağırıcağımız bir döngüye ihtiyacımız var
```
define :my_loop do
  play 50
  sleep 1
end

in_thread(name: :looper) do
  loop do
    my_loop
  end
end 
```
Eğer bu size karmaşık geliyorsa, geriye gidin, thread ve fonksiyonlarla ilgili bölümleri tekrar okuyun. Eğer bu başlıkları kafanızda oturtabildiyseniz zaten karmaşık gelmemiştir.
Yukarıda 50. notayı çalan ve 1 vuruş boyunca uyuyan bir fonksiyonumuz var ve :looper adını verdiğimiz bir "thread" bu my_loop fonksiyonunu durmadan çağırıp döngüye sokuyor.
Eğer bu kodu çalıştırırsanız 1 vuruş arayla kendini durmadan tekrar eden 50. notayı duyacaksınız.

## Kodu Değiştirmek
İşte eğlence tam olarak burada başlıyor. Bir önceki bölümdeki kod çalışmaya devam ederken 50 yi farklı bir sayıya, diyelim ki 55, çevirip tekrar çalıştır butonuna bastığınızda ses değişir.Canlı olarak!

Bu yaptığımız işlem yeni bir katman oluşturmadı çünkü kullandığımız adlandırılmış "thread" aynı ada sahip bir tane çalıştırmaya izin veriyor. Ayrıca, ses değişti çünkü fonksiyonu yeniden tanımladık. :my_loop fonksiyonuna yeni bir tanım verdik ve :looper bir sonraki çalışımızda yeni tanımı çalmaya başladı.

Tekrar değiştirmeyi deneyin, notayı ve uyuma süresini değiştirin.Ya da yeni bir birleştirici ekleyin. Örneğin kodumuzu şu hale getirelim:
```
define :my_loop do
  use_synth :tb303
  play 50, release: 0.3
  sleep 0.25
end 
```
Şu an ses daha ilgi çekici geliyor, fakat bunu daha ilgi çekici hale getirebiliriz. Her seferinde aynı notayı çalmak yerine bu sefer bir akor çalmayı deneyelim:
```
define :my_loop do
  use_synth :tb303
  play chord(:e3, :minor), release: 0.3
  sleep 0.5
end 
```
Peki ya bu akordan farklı notalar çalsak:
```
define :my_loop do
  use_synth :tb303
  play choose(chord(:e3, :minor)), release: 0.3
  sleep 0.25
end 
```
Son olarak da biraz davul ekleyelim:
```
define :my_loop do
  use_synth :tb303
  sample :drum_bass_hard, rate: rrand(0.5, 2)
  play choose(chord(:e3, :minor)), release: 0.2
  sleep 0.25
end 
```
İşte şimdi işler daha eğlenceli hale geliyor!
Ancak hemen fonksiyonlar ve "thread"'ler kullanıp canlı kodlamaya başlamadan önce bir sonraki bölümde canlı döngüler (live_loop) bölümünü de okuyun, Sonic Pi'daki kodlama şeklinizi tamamen değiştirecek...














