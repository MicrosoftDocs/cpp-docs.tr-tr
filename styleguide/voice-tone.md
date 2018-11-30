# <a name="voice-and-tone-guidelines"></a>Ses ve sesi yönergeleri

Geliştiriciler, belgelerinizi .NET core öğrenmek ve normal çalışmalarını kullanmak için okuma.
Amacınız, YOLCULUĞUNA okuyucuyu yardımcı olan kullanışlı belgeler oluşturmaktır. Koşullarımıza ile yardımcı olur. Stil kılavuzunu dört öneriler içerir:
- [Konuşma sesini kullanın](#use-a-conversational-tone)
- [İkinci kişinin yazma](#write-in-2nd-person)
- [Etkin kullanın](#use-active-voice)
- [Bir 5 sınıf okuma düzeyi hedefleyin](#target-a-5th-grade-reading-level)

Her birinin bu stil Kılavuzu okurken örnekler görürsünüz. Az önce koşullarımıza aşağıdaki bu kılavuzda, .NET Core belgeleri oluşturdukça takip etmek için örnekler sağlamayı yazdığımız. Bizim yönergeleri izlediğinizde olmayan makaleler nasıl göründüğünü görebilirsiniz ayrıca karşıt örnekleri sağlarız.

## <a name="details-on-each-guideline"></a>Her kural ayrıntıları

### <a name="use-a-conversational-tone"></a>Konuşma sesini kullanın
#### <a name="appropriate-style"></a>Uygun stili:
Belgelerimizi konuşma sesini olmasını istiyoruz. Tüm öğreticileri veya açıklamaları okurken Yazar ile bir konuşma karşılaştığınız gibi sorgulamanıza gelecektir.
Deneyiminizi bir okuyucu olarak resmi olmayan, damıtarak konuşma bağlamında kullanılabilen ve açıklayıcı olmalıdır. Yazar dinleyen gibi sorgulamanıza gelecektir size kavramlarını açıklar.

#### <a name="inappropriate-style"></a>Uygunsuz stili:
Bir konuşma stili ve bir teknik konular daha akademik treatments ile bulur stilini arasındaki kontrastı görebilirsiniz. Bu kaynakları çok yararlı olur, ancak yazarlar, bu makaleler Belgelerimizi daha çok farklı bir stilde yazdınız. Bir akademik bir günlük okuduğunda, bir çok farklı bir üslup ve çok farklı bir yazı stili bulur.
Bir çok kuru konunun kuru bir hesabı okuyorsanız hissettirir.  

Yukarıdaki ilk paragrafa bizim öneri damıtarak konuşma bağlamında kullanılabilen stili izler. Daha fazla akademik stil saniyedir. Fark anında görün. 

### <a name="write-in-second-person"></a>İkinci kişinin yazma
#### <a name="appropriate-style"></a>Uygun stili:
Doğrudan okuyucu'nu konuşma gibi sorgulamanıza makalelerinizin yazmanız gerekir. İkinci kişinin kullanmanız gerekir (yalnızca bu iki cümlelerde sahibim gibi) genellikle. 2 kişi değil her zaman anlamına sözcüğün kullanıldığı ','. Okuyucu için doğrudan yazma. Kesinlik temelli bir cümle yazın.
Okuyucu, bunları öğrenmek istediklerinizi söyleyin.

#### <a name="inappropriate-style"></a>Uygunsuz stili: 
Yazar, ayrıca üçüncü kişi yazmak seçebilir. Bu modelde bazı gelebildiği veya Okuyucu için söz konusu olduğunda kullanılacak isim Yazar bulmanız gerekir. Okuyucu, genellikle daha ilgi çekici ve okumak daha az keyifli bu üçüncü kişi stili bulabilirsiniz.

İlk paragrafa bizim önerilen stili izler. İkinci üçüncü kişi kullanır. Lütfen ikinci kişinin yazın. Büyük olasılıkla, çok daha kolay bulundu.

### <a name="use-active-voice"></a>Etkin kullanın

Makalelerinize etken içinde yazın. Etkin ses cümlenin konusunun ilgili tümcenin (Fiili) eylem gerçekleştirir anlamına gelir. Edilgen cümlenin konu izlemede şekilde cümlenin burada düzenlenen ile karşılaştırır. Bu iki örnek karşılaştırın:

>Derleyici, kaynak kodu yürütülebilir bir dosyaya dönüştürülür.

>Kaynak kodu, derleyici tarafından yürütülebilir bir dosyaya dönüştürüldü.

İlk cümle etken kullanır. İkinci cümlenin edilgen yazılmıştır.
(Bu iki cümle her stilin başka bir örnek belirtin).

Daha okunabilir olduğundan etken öneririz. Edilgen okunacak daha zor olabilir.

### <a name="target-a-fifth-grade-reading-level"></a>Beşinci bir sınıf okuma düzeyi hedefleyin

Bizim okuyucular birçoğu yerel İngilizce konuşmacıları olmadığından bu son Kılavuzu sunuyoruz.
Uluslararası bir hedef kitle ile makalelerinizin ulaşıyor. Lütfen kullandığınız İngilizce sözlüğü olmayabilir dikkate alın.

Ancak, teknik uzmanlar için hala yazıyorsunuz. Okuyucularınızın programlama bilgi ve programlama terimleri için belirli sözlük olduğunu varsayabilirsiniz. Nesne yönelimli programlama, sınıf ve nesne, işlevi ve yöntemi tanıdık koşulları olacak. Ancak, herkes makalelerinizin okuma biçimsel bilgisayar bilimi derece sahip olur. Muhtemelen 'ıdempotent' benzer terimleri kullanırsanız tanımlanması gerekir:

>Close() yöntemi birden çok kez çağırabilir ve bir kez çağrılması halinde gibi etkisi aynıdır, etkilidir.