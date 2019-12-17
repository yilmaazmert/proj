###PART 2: BRLEŞ
  Tamam bu kadar intro yeterli. Biraz sese bakalım

  Bu bölümde brleşlerin (synth) çalıştırılması ve değiştirilmesini inceleyeceğiz. Brleş,ses çıkaran bir şey için süslü bir kelime olan 
  birleştiricinin kısaltılmış hali.
  Genelde brleşleri kullanmak biraz komplikedir, özellikle Eurorack modülleri gibi analog brleşler bir kablo karmaşası ile birbirlerine
  bağlandığı için bizi zor duruma sokar. Fakat, Sonic Pi bize bu brleşleri daha basit ve ulaşılabilir bir şekilde sunmaktadır.

  Sonic Pi arayüzünün basitliğine aldanmayın. Eğer ses üzerinde daha sofistike değişiklikler yapmayı planlıyorsanız göründüğünden
  çok daha derinlere gidebilirsiniz.Kemerlerinizi bağlayın!

PART 2.1: İLK BİPLERİNİZ
  Aşağıdaki koda bakın:
  
  play 70
  
  İşte her şey burada başlıyor.Durma, kodu kopyalayıp uygulamanın üstündeki pencereye yapıştır (Çalıştır butonunun altındaki büyük 
  beyaz boşluk).Şimdi, Çalıştır butonuna bas.
  
  BİP!
  
  Etkileyici.Tekrar bas. Ve tekrar. Ve tekrar...
  
  Vay, şahane. Eminim bunu bütün gün yapabilirsin. Ama dur, kendini sonsuz bir bip döngüsünde kaybetmeden önce, sayıyı değiştirmeyi dene
  
  play 75
  
  Aradaki farkı duydun mu ? Daha düşük bir sayı dene: 
  
  play 60
  
  Gördüğün üzere, daha düşük sayılar daha kalın sesler çıkarırken yüksek sayılar daha ince sesler çıkarıyor. Tıpkı piyano gibi,
  piyanonun sol tarafındaki tuşlar kalın ve sağ tarafındaki tuşlar ince sesler çıkarıyor. Ayrıca kullandığımız sayılar aslında piyanodan
  bağımsız değil. play 47 aslında piyanodaki 47. notayı çal anlamına geliyor. Bu da demek oluyor ki play 48 bir nota yükseltiyor.
  
  4. oktavdaki C akoru 60 numaraya denk geliyor. Hadi çalmayı dene: play 60
  
  Merak etme eğer bu şu an sana bir şey ifade etmiyorsa, ilk başladığımda bana da bir şey ifade etmiyordu. Şu an tek önemli olan
  düşük sayıların kalın yüksek sayıların ince sesler çıkardığını bilmen.
  
  AKORLAR
  
  Nota çalmak bir miktar eğlenceli, ama bir kaçını aynı anda çalmak çok daha iyi.Dene bakalım:
  play 72
  play 75
  play 79
  
  Jazımsı! Sonuç olarak, birden fazla play yazdığında, hepsi aynı anda çalıyor. Kendin dene, hangi notalar birlikte güzel hangileri 
  de berbat ses çıkarıyor. Gözlemle, araştır ve kendin için bul.
  
  MELODİ
  
  Evet, nota ve akor çalmak eğlenceli, ama melodi çalmak? Ya notaları aynı anda değil de arka arkaya çalmak istiyorsan? Bu da kolay
  sadece notalar arasında uyumalısın (sleep):
  
  play 72
  sleep 1 
  play 75
  sleep 1 
  play 79
  
  Ne kadar güzel, minik bir arpej. Peki sleep 1 komutundaki 1 ne demek? Bu sayı uyuma süresi anlamına geliyor. Tam olarak 1 darbe
  süresinde uyumak anlamına geliyor. Arpejimizi daha hızlı yapmak istiyorsak ne yapmalıyız? O zaman da daha kısa uyku komutları
  kullanmalıyız. Yarısını (0.5) kullanmaya ne dersiniz.
  
  play 72
  sleep 0.5
  play 75
  sleep 0.5
  play 79
  
  Nasıl daha hızlı çaldığını fark ettin mi? Şimdi kendin dene, zamanı değiştir - farklı zaman ve notalar kullan.
  
  Denenebilecek başka bir şey de play 52.3 ve play 52.63 gibi ara notalar çalmak. Bütün notalara takılı kalmaya hiç gerek yok.
  Biraz dene ve eğlenmene bak.
  
  GELENEKSEL NOTA İSİMLERİ
  
  Birazcık müzik bilgisi olanlar olarak (eğer değilseniz de önemli değil, eğlenmek için bilmenize gerek yok) C ve F# gibi nota isimleri
  kullanarak melodi yazmak isteyebilirsiniz. SonicPi arkanızda! Aşağıdaki şekilde yapabilirsiniz
  
  play :C
  sleep 0.5
  play :D
  sleep 0.5
  play :E
  
  Notanızın pembe olması için harften önce ":" koymayı unutmayın. Ayrıca notanın ardından sayı ekleyerek kullanmak istediğiniz
  oktavı belirtebilirsiniz.
  
  play :C3
  sleep 0.5
  play :D3
  sleep 0.5
  play :E4
  
  Eğer bir notayı daha tiz yapmak isterseniz nota harfinden sonra "s" eklemeyi deneyin, play :Fs3 gibi ve bemol yapmak isterseniz
  "b" ekleyin, play :Eb3 gibi.
  
  Şimdi kendini kaybet ve kendi tonlarını yapmanın tadını çıkar!
