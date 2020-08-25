---
title: x64 özel durum işleme
ms.date: 10/14/2019
helpviewer_keywords:
- C++ exception handling, x64
- exception handling, x64
ms.assetid: 41fecd2d-3717-4643-b21c-65dcd2f18c93
ms.openlocfilehash: 3d973354f94ca8c9f2e0901e60f2a8009ac08cd6
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835057"
---
# <a name="x64-exception-handling"></a>x64 özel durum işleme

Yapılandırılmış özel durum işleme ve C++ özel durum işleme kodlama kuralları ve x64 üzerindeki davranış hakkında genel bakış. Özel durum işleme hakkında genel bilgi için bkz. [Visual C++ özel durum işleme](../cpp/exception-handling-in-visual-cpp.md).

## <a name="unwind-data-for-exception-handling-debugger-support"></a>Özel durum işleme için veri bırakma, hata ayıklayıcı desteği

Özel durum işleme ve hata ayıklama desteği için çeşitli veri yapıları gereklidir.

### <a name="struct-runtime_function"></a>struct RUNTIME_FUNCTION

Tablo tabanlı özel durum işleme, yığın alanı ayıran veya başka bir işlev çağıran (örneğin yaprak olmayan işlevler) tüm işlevler için tablo girişi gerektirir. İşlev tablosu girdileri şu biçimdedir:

|Boyut|Değer|
|-|-|
|'TUR|İşlev başlangıç adresi|
|'TUR|İşlev bitiş adresi|
|'TUR|Geriye doğru bilgi adresi|

RUNTIME_FUNCTION yapısı, bellekte DWORD hizalı olmalıdır. Tüm adresler görüntüye göre değişir, diğer bir deyişle, işlev tablosu girişini içeren görüntünün başlangıç adresinden 32 bitlik uzaklıklardır. Bu girişler sıralanır ve bir PE32 + görüntüsünün. pdata bölümüne konur. Dinamik olarak oluşturulan işlevler [JıT derleyicileri] için, bu işlevleri desteklemeye yönelik çalışma zamanının, bu bilgileri işletim sistemine sağlaması için RtlInstallFunctionTableCallback veya RtlAddFunctionTable kullanması gerekir. Bunun yapılmaması, güvenli olmayan özel durum işleme ve hata ayıklama işlemlerine neden olur.

### <a name="struct-unwind_info"></a>struct UNWIND_INFO

Bırakma verileri bilgi yapısı, bir işlevin yığın işaretçisine sahip olduğu etkileri kaydetmek için kullanılır ve kalıcı kayıtların yığına kaydedildiği yerdir:

|Boyut|Değer|
|-|-|
|UBDE: 3|Sürüm|
|UBYELERI: 5|Bayraklar|
|UBDE|Giriş boyutu|
|UBDE|Bırakma kodlarının sayısı|
|UBDE: 4|Çerçeve kaydı|
|UBDE: 4|Çerçeve kayıt boşluğu (ölçeklendirilmiş)|
|USHORT \* n|Geriye doğru izleme kodları dizisi|
|değişken|Aşağıdaki biçimde (1) veya (2) olabilir|

(1) özel durum Işleyicisi

|Boyut|Değer|
|-|-|
|'TUR|Özel durum işleyicisinin adresi|
|değişken|Dile özgü işleyici verileri (isteğe bağlı)|

(2) zincirleme bırakma bilgileri

|Boyut|Değer|
|-|-|
|'TUR|İşlev başlangıç adresi|
|'TUR|İşlev bitiş adresi|
|'TUR|Geriye doğru bilgi adresi|

UNWIND_INFO yapısı, bellekte DWORD hizalı olmalıdır. Her alanın anlamı aşağıda verilmiştir:

- **Sürüm**

   Bırakma verilerinin sürüm numarası, şu anda 1.

- **Larına**

   Şu anda üç bayrak tanımlanmış:

   |Bayrak|Açıklama|
   |-|-|
   |`UNW_FLAG_EHANDLER`| İşlevin, özel durumları incelemesi gereken işlevleri ararken çağrılması gereken bir özel durum işleyicisi vardır.|
   |`UNW_FLAG_UHANDLER`| İşlevin bir özel durumu geriye doğru geri yüklerken çağrılması gereken bir sonlandırma işleyicisi vardır.|
   |`UNW_FLAG_CHAININFO`| Bu bırakma bilgisi yapısı, yordam için birincil bir değer değil. Bunun yerine, zincirleme bırakma bilgisi girişi, önceki bir RUNTIME_FUNCTION girişinin içeriğidir. Bilgi için bkz. [zincirleme bırakma bilgi yapıları](#chained-unwind-info-structures). Bu bayrak ayarlandıysa UNW_FLAG_EHANDLER ve UNW_FLAG_UHANDLER bayrakları temizlenmelidir. Ayrıca, çerçeve kaydı ve sabit yığın ayırma alanları, birincil bırakma bilgilerinde aynı değerlere sahip olmalıdır.|

- **Giriş boyutu**

   İşlev giriş bölümünün bayt cinsinden uzunluğu.

- **Bırakma kodlarının sayısı**

   Geriye doğru izleme kodları dizisindeki yuva sayısı. Örneğin UWOP_SAVE_NONVOL bazı bırakma kodları dizide birden fazla yuva gerektirir.

- **Çerçeve kaydı**

   Sıfır değilse, işlev bir çerçeve işaretçisi (FP) kullanır ve bu alan, UNWIND_CODE düğümlerinin işlem bilgileri alanı için aynı kodlamayı kullanarak çerçeve işaretçisi olarak kullanılan kalıcı kayıt numarasıdır.

- **Çerçeve kayıt boşluğu (ölçeklendirilmiş)**

   Çerçeve kayıt alanı sıfır değilse, bu alan, oluşturulduğunda FP kaydına uygulanan RSP 'den ölçeklenmiş bir uzaklığa sahiptir. Gerçek FP Register değeri RSP + 16 \* Bu sayı olarak ayarlanır ve 0 ' dan 240 ' a kadar uzaklıklara izin verir. Bu konum, FP 'nin dinamik yığın çerçeveleri için yerel yığın ayırmasının ortasına, daha kısa yönergeler aracılığıyla daha iyi kod yoğunluğu sağlayan şekilde belirtilmesine izin verir. (Diğer bir deyişle, daha fazla yönerge 8 bit işaretli fark formunu kullanabilir.)

- **Geriye doğru izleme kodları dizisi**

   Kalıcı yazmaçları ve RSP üzerinde giriş etkisini açıklayan öğelerin dizisi. Tek tek öğelerin anlamları için UNWIND_CODE bölümüne bakın. Hizalama amacıyla bu dizi her zaman çift sayıda girişe sahiptir ve son giriş muhtemelen kullanılmıyor olabilir. Bu durumda, dizi geriye doğru izleme kodları alanı tarafından gösterilenden daha uzun bir alandır.

- **Özel durum işleyicisinin adresi**

   İşlevin dile özgü özel duruma veya sonlandırma işleyicisine, bayrak UNW_FLAG_CHAININFO açık ve bayraklardan biri UNW_FLAG_EHANDLER veya UNW_FLAG_UHANDLER ayarlandıysa resim göreli bir işaretçi.

- **Dile özgü işleyici verileri**

   İşlevin dile özgü özel durum işleyicisi verileri. Bu verilerin biçimi belirtilmemiş ve kullanımda olan özel durum işleyicisi tarafından tamamen belirlenir.

- **Zincirleme bırakma bilgileri**

   Bayrak UNW_FLAG_CHAININFO ayarlandıysa, UNWIND_INFO yapısı üç Ukelimeyle sona erer.  Bu Ukelimeler, zincirleme bırakma işlevinin işlevine ilişkin RUNTIME_FUNCTION bilgilerini temsil eder.

### <a name="struct-unwind_code"></a>struct UNWIND_CODE

Açılım kodu dizisi, kalıcı yazmaçları ve RSP 'yi etkileyen giriş bölümündeki işlem dizisini kaydetmek için kullanılır. Her kod öğesi şu biçimdedir:

|Boyut|Değer|
|-|-|
|UBDE|Giriş bölümündeki konum|
|UBDE: 4|Geriye doğru işlem kodu|
|UBDE: 4|İşlem bilgisi|

Dizi, giriş bölümündeki uzaklığa göre azalan düzende sıralanır.

#### <a name="offset-in-prolog"></a>Giriş bölümündeki konum

Bu işlemi gerçekleştiren yönergenin sonundaki fark (giriş başından itibaren), artı 1 (yani, sonraki yönergenin başlangıcının sapmasını).

#### <a name="unwind-operation-code"></a>Geriye doğru işlem kodu

Note: belirli işlem kodları, yerel yığın çerçevesindeki bir değere işaretsiz bir konum gerektirir. Bu konum başlangıçtan, diğer bir deyişle, sabit yığın ayırmanın en düşük adresidir. UNWIND_INFO çerçeve kayıt alanı sıfırsa, bu fark RSP 'den olur. Çerçeve kayıt alanı sıfır değilse, bu fark, FP kaydı oluşturulduğunda RSP 'nin bulunduğu yerdir. Bu, FP kaydına eşittir ( \* UNWIND_INFO ölçeği ölçeklenmiş çerçeve kayıt boşluğu 16). Bir FP kaydı kullanılıyorsa, bir konum alan herhangi bir açılım kodu yalnızca giriş bölümünde FP kaydı kurulduktan sonra kullanılmalıdır.

Ve dışındaki tüm opkodlara `UWOP_SAVE_XMM128` yönelik `UWOP_SAVE_XMM128_FAR` tüm yığın değerleri 8 baytlık sınırlarda depolandığından, fark her zaman 8 ' in katı olur (yığının kendisi her zaman 16 bayt hizalı). Kısa bir uzaklığa (512K ' den az) sahip olan işlem kodları için, bu koda ait düğümlerdeki son USHORT, sapmayı 8 ' den bölünen olarak tutar. Uzun bir uzaklığa (512K <= fark < 4GB) sahip olan işlem kodları için, bu kod için son iki USHORT düğümü, sapmayı (küçük endian biçiminde) tutar.

`UWOP_SAVE_XMM128` `UWOP_SAVE_XMM128_FAR` Tüm 128-bit XMM işlemleri 16 baytlık hizalanmış bellekte gerçekleşdiğinden, işlem kodları ve, her zaman 16 ' dan fazla bir değer vardır. Bu nedenle, 1 ' den küçük bir ölçek faktörü kullanılır, 1 milyon `UWOP_SAVE_XMM128` ' den az uzaklıklara izin verilir.

Geriye doğru izleme işlemi kodu şu değerlerden biridir:

- `UWOP_PUSH_NONVOL` (0) 1 düğüm

  Kalıcı tamsayı kaydını göndererek RSP 'yi 8 ' den azaltarak. İşlem bilgisi kayıt sayısıdır. Epıng 'lerdeki kısıtlamalar nedeniyle, açılım `UWOP_PUSH_NONVOL` kodları giriş ve geri doğru, en son bırakma kodu dizisinde yer almalıdır. Bu göreli sıralama, hariç olmak üzere diğer tüm bırakma kodları için geçerlidir `UWOP_PUSH_MACHFRAME` .

- `UWOP_ALLOC_LARGE` (1) 2 veya 3 düğümleri

  Yığında büyük ölçekli bir alan ayırın. İki biçim vardır. İşlem bilgileri 0 ' a eşitse, ayırmanın boyutu 8 ' e bölünür bir sonraki yuvaya kaydedilir ve 512K-8 ' e kadar bir ayırmaya izin verilir. İşlem bilgileri 1 eşitse, ayırmaların ölçeklendirilmemiş boyutu, küçük endian biçiminde bir sonraki iki yuvaya kaydedilir ve bu da 4 GB-8 ' e kadar ayırmaya izin verir.

- `UWOP_ALLOC_SMALL` (2) 1 düğüm

  Yığında küçük ölçekli bir alan ayırın. Ayırma boyutu, 8 + 8 olan işlem bilgileri alanıdır \* ve 8 ile 128 bayta ayırmaya izin verir.

  Yığın ayırma için bırakma kodu, her zaman mümkün olan en kısa kodlamayı kullanmalıdır:

  |**Ayırma boyutu**|**Bırakma kodu**|
  |-|-|
  |8-128 bayt|`UWOP_ALLOC_SMALL`|
  |136 512K-8 bayt|`UWOP_ALLOC_LARGE`, işlem bilgisi = 0|
  |512K-4G-8 bayt|`UWOP_ALLOC_LARGE`, işlem bilgisi = 1|

- `UWOP_SET_FPREG` (3) 1 düğüm

  Kaydı geçerli RSP 'nin bir uzaklığa ayarlayarak çerçeve işaretçisi kaydını oluşturun. Uzaklık, \* 0 ile 240 arasında uzaklıklara izin veren UNWIND_INFO 16 ' daki çerçeve kayıt boşluğu (ölçeklendirilmiş) alanına eşittir. Bir konum kullanımı, sabit yığın ayırmanın ortasına işaret eden bir çerçeve işaretçisinin oluşturulmasına izin verir ve daha fazla erişimin kısa yönerge formlarını kullanmasına izin vererek kod yoğunluğuna yardımcı olur. İşlem bilgisi alanı ayrılmıştır ve kullanılmamalıdır.

- `UWOP_SAVE_NONVOL` (4) 2 düğüm

  Kalıcı tamsayı kaydını, PUSH yerine MOV kullanarak yığına kaydedin. Bu kod öncelikle, kalıcı kaydın daha önce ayrılmış bir konumda yığına kaydedildiği, *küçültme kaydırması*için kullanılır. İşlem bilgisi kayıt sayısıdır. Ölçeği, yukarıdaki notta açıklandığı gibi sonraki geriye doğru izleme işlemi kod yuvasına kaydedilir.

- `UWOP_SAVE_NONVOL_FAR` (5) 3 düğüm

  Bir kalıcı tamsayı kaydını, bir PUSH yerine MOV kullanarak uzun bir uzaklığa sahip yığına kaydedin. Bu kod öncelikle, kalıcı kaydın daha önce ayrılmış bir konumda yığına kaydedildiği, *küçültme kaydırması*için kullanılır. İşlem bilgisi kayıt sayısıdır. Ölçeklendirilmemiş yığın boşluğu, yukarıdaki notta açıklandığı gibi sonraki iki geriye doğru izleme işlem kodu yuvalarında kaydedilir.

- `UWOP_SAVE_XMM128` (8) 2 düğüm

  Yığında kalıcı bir XMM kaydının tüm 128 bitlerini kaydedin. İşlem bilgisi kayıt sayısıdır. Ölçeklenmiş 16 yığın boşluğu bir sonraki yuvaya kaydedilir.

- `UWOP_SAVE_XMM128_FAR` (9) 3 düğümleri

  Kalıcı bir XMM kaydının tüm 128 bitlerini yığın üzerinde uzun bir uzaklığa sahip olacak şekilde kaydedin. İşlem bilgisi kayıt sayısıdır. Ölçeklendirilmemiş yığın boşluğu sonraki iki yuvaya kaydedilir.

- `UWOP_PUSH_MACHFRAME` (10) 1 düğüm

  Bir makine çerçevesini gönderin.  Bu bırakma kodu, bir donanım kesmesi veya özel durumunun etkisini kaydetmek için kullanılır. İki biçim vardır. İşlem bilgileri 0 eşitse, bu çerçevelerden biri yığına itildi:

  |Konum|Değer|
  |-|-|
  |RSP + 32|SS|
  |RSP + 24|Eski RSP|
  |RSP + 16|EFLAGS|
  |RSP + 8|CS|
  |RSP|'TE|

  İşlem bilgisi 1 eşitse, bu çerçevelerden biri itildi:

  |Konum|Değer|
  |-|-|
  |RSP + 40|SS|
  |RSP + 32|Eski RSP|
  |RSP + 24|EFLAGS|
  |RSP + 16|CS|
  |RSP + 8|'TE|
  |RSP|Hata kodu|

  Bu bırakma kodu, hiçbir zaman aslında Yürütülmeyen, ancak bunun yerine bir kesme yordamının gerçek giriş noktasına ait olan ve yalnızca bir makine çerçevesinin göndermesinin benzetimini yapmak için mevcut olan bir kukla giriş içinde görüntülenir. `UWOP_PUSH_MACHFRAME` makinenin bu işlemi kavramsal olarak yaptığını belirten simülasyonu kaydeder:

  1. Yığının üstünden *Temp* 'e açılan RIP dönüş adresi
  
  1. Gönderim SS

  1. Eski RSP gönder

  1. EFLAGS gönder

  1. CS gönder

  1. *Geçici* gönder

  1. Gönderim hata kodu (op bilgisinin 1 ' e eşit olması halinde)

  Sanal `UWOP_PUSH_MACHFRAME` Işlem RSP 'yi 40 (op bilgisi eşittir 0) veya 48 (op bilgisi eşittir 1) ile azaltır.

#### <a name="operation-info"></a>İşlem bilgisi

İşlem bilgisi bitlerinin anlamı işlem koduna bağlıdır. Genel amaçlı (tamsayı) kayıt kodlamak için bu eşleme kullanılır:

|Sürümleri|Kaydol|
|-|-|
|0|RAX|
|1|RCX|
|2|RDX|
|3|RBX|
|4|RSP|
|5|RBP|
|6|RSı|
|7|RDı|
|8-15|R8 to R15|

### <a name="chained-unwind-info-structures"></a>Zincirleme bırakma bilgi yapıları

UNW_FLAG_CHAININFO bayrağı ayarlandıysa, geriye doğru izleme bilgisi yapısı ikincil bir durumdur ve paylaşılan özel durum işleyici/zincirleme-bilgi adresi alanı birincil geriye doğru bırakma bilgilerini içerir. Bu örnek kod, `unwindInfo` UNW_FLAG_CHAININFO bayrak ayarlanmış yapı olduğunu varsayarak, birincil geriye doğru izleme bilgilerini alır.

```cpp
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);
```

Zincirleme bilgileri iki durumda faydalıdır. İlk olarak, bitişik olmayan kod kesimleri için kullanılabilir. Zincirleme bilgilerini kullanarak, gerekli geriye doğru bırakma bilgisinin boyutunu azaltabilirsiniz, çünkü geriye doğru bırakma bilgilerinizden bırakma kodları dizisini çoğaltmak zorunda değilsiniz.

Geçici kayıt kaydetmeyi gruplandırmak için zincirleme bilgilerini de kullanabilirsiniz. Derleyici, işlev girdisi giriş girişinin dışına çıkana kadar bazı geçici yazmaçların kaydedilmesini erteleyebilir. Gruplanmış koddan önce işlevin bölümü için birincil geriye doğru bilgi vererek ve sonra zincirleme bilgileri, zincirleme olmayan bir giriş ile, zincirleme bilgilerinin kalıcı yazmaçların kaydedilmelerini yansıtarak kayıt bilgilerini ayarlayarak kaydedebilirsiniz. Bu durumda, geriye doğru izleme kodları UWOP_SAVE_NONVOL örneklerinden oluşur. Kalıcı kayıtları bir PUSH kullanarak kaydeden veya ek bir sabit yığın ayırması kullanarak RSP kaydını değiştiren bir gruplama desteklenmez.

UNW_FLAG_CHAININFO kümesine sahip bir UNWIND_INFO öğesi, bazı durumlarda *birden çok küçültme*olarak adlandırılan UNWIND_INFO öğesi UNW_FLAG_CHAININFO ayarlanmış olan bir RUNTIME_FUNCTION girişi içerebilir. Sonuç olarak, zincirleme bırakma bilgileri işaretçileri, UNW_FLAG_CHAININFO temizlenmiş bir UNWIND_INFO öğesine ulaşır. Bu öğe, gerçek yordam giriş noktasını işaret eden birincil UNWIND_INFO öğesidir.

## <a name="unwind-procedure"></a>Geriye doğru izleme prosedürü

Bırakma kodu dizisi azalan düzende sıralanır. Bir özel durum oluştuğunda, tüm bağlam, işletim sistemi tarafından bir bağlam kaydında saklanır. Özel durum gönderme mantığı çağrılır ve bu adımlar bir özel durum işleyicisini bulmak için art arda çalıştırılır:

1. Geçerli işlevi (veya zincirleme UNWIND_INFO girişleri için işlev bölümünü) açıklayan bir RUNTIME_FUNCTION tablo girişi aramak için bağlam kaydında depolanan geçerli RIP 'yi kullanın.

1. Hiçbir işlev tablosu girişi bulunamazsa, bir yaprak fonksiyonda olur ve RSP doğrudan dönüş işaretçisine yöneliktir. [RSP] konumundaki dönüş işaretçisi güncelleştirilmiş bağlamda saklanır, sanal RSP 8 ile artırılır ve 1. adım yinelenir.

1. Bir işlev tablosu girişi bulunursa, RIP, bir özel durum işleyicisi tarafından kapsanacak kodda, giriş veya c) içindeki bir bitiş, b) içinde üç bölgede yer alabilir: a).

   - Büyük/küçük harf a) kopyalama bir bitiş içindeyse, denetim işlevden ayrıldığında, bu işlev için bu özel durumla ilişkili bir özel durum işleyici olmayabilir ve bu işlem, çağıran işlevin bağlamını hesaplamaya devam etmelidir. RIP 'in bir bitiş içinde olup olmadığını anlamak için, RIP 'ten alınan kod akışı incelenir. Bu kod akışı, yasal bir bitiş bölümünün sonundaki kısmı ile eşleştirilabiliyorsanız, bu, bir bir bitişdir ve her yönerge işlendiği için bağlam kaydı güncelleştirilerek, bitiş alanının kalan kısmı benzetilir. Bu işlemden sonra 1. adım yinelenir.

   - Büyük/küçük harf b) RIP, işlem içinde yer alıyorsa denetim işlevi girilmedi, bu işlev için bu özel durumla ilişkili bir özel durum işleyici olmayabilir ve çağıran işlevin bağlamını hesaplamak için giriş durumunun geri alınmalıdır. İşlevden başlayan uzaklık, geriye doğru izleme bilgilerinde kodlanmış giriş boyutundan küçükse, RIP giriş içindedir. Girişin etkileri, ilk girdinin geri sarma kodları dizisi aracılığıyla, bir değerden sıfırdan küçük veya buna eşit olan bir uzaklığa göre geriye doğru tarama yaparak, geriye kalan tüm öğelerin etkisini geri alarak geri alınıyor. 1. adım daha sonra tekrarlanır.

   - Durum c) RIP bir giriş veya bitiş içinde değilse ve işlevin bir özel durum işleyicisi (UNW_FLAG_EHANDLER ayarlandıysa) varsa, dile özgü işleyici çağırılır. İşleyici verilerini tarar ve filtre işlevlerini uygun şekilde çağırır. Dile özgü işleyici, özel durumun işlenmiş olduğunu veya aramanın devam ettirilemeyeceğini döndürebilir. Ayrıca, doğrudan bir geriye doğru izleme başlatabilir.

1. Dile özel işleyici işlenmiş bir durum döndürürse, yürütme özgün bağlam kaydı kullanılarak devam eder.

1. Dile özgü işleyici yoksa veya işleyici bir "devam araması" durumu döndürürse, bağlam kaydının çağıranın durumuna kaldırılması gerekir. Tüm geriye doğru kod dizisi öğelerinin işlenmesiyle yapılır, her birinin etkisini geri alabilir. 1. adım daha sonra tekrarlanır.

Zincirleme bırakma bilgileri dahil edildiğinde, bu temel adımlar yine de izlenir. Tek fark, geriye doğru izleme kodu dizisinin bir prolog 'ın etkilerini geriye doğru bir şekilde yürümesi sırasında, dizinin sonuna ulaşıldığında, daha sonra üst geriye doğru bağlantı bilgisine bağlanır ve bu, tüm bırakma kodu dizisinin bir işaret olduğunu tespit edilir. Bu bağlama, UNW_CHAINED_INFO bayrağı olmadan bir geriye doğru izleme bilgisine gelene kadar devam eder ve ardından geriye doğru izleme kod dizisini yürüder.

En küçük bırakma verisi kümesi 8 bayttır. Bu, yalnızca 128 baytlık yığını veya daha azını ayrılan ve muhtemelen bir adet kalıcı kayıt kaydeden bir işlevi temsil eder. Aynı zamanda, geriye doğru izleme kodu olmayan sıfır uzunluklu bir giriş için zincirleme bırakma bilgi yapısının boyutudur.

## <a name="language-specific-handler"></a>Dile özel işleyici

Her bayrak UNW_FLAG_EHANDLER veya UNW_FLAG_UHANDLER ayarlandığında dile özgü işleyicinin göreli adresi UNWIND_INFO vardır. Önceki bölümde açıklandığı gibi dile özgü işleyici, bir özel durum işleyici aramasının parçası olarak veya bir geriye doğru izleme kapsamında çağırılır. Bu prototipi içerir:

```cpp
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (
    IN PEXCEPTION_RECORD ExceptionRecord,
    IN ULONG64 EstablisherFrame,
    IN OUT PCONTEXT ContextRecord,
    IN OUT PDISPATCHER_CONTEXT DispatcherContext
);
```

**ExceptionRecord** , standart Win64 tanımına sahip bir özel durum kaydına yönelik bir işaretçi sağlar.

**EstablisherFrame** , bu işlevin sabit yığın ayırma tabanının adresidir.

**ContextRecord** , özel durum oluşturulduğu zaman özel durum bağlamına işaret eder (özel durum işleyici durumunda) veya geçerli "geriye doğru izleme" bağlamı (sonlandırma işleyicisi durumunda).

**DispatcherContext** , bu işlev için dağıtıcı bağlamına işaret ediyor. Şu tanıma sahiptir:

```cpp
typedef struct _DISPATCHER_CONTEXT {
    ULONG64 ControlPc;
    ULONG64 ImageBase;
    PRUNTIME_FUNCTION FunctionEntry;
    ULONG64 EstablisherFrame;
    ULONG64 TargetIp;
    PCONTEXT ContextRecord;
    PEXCEPTION_ROUTINE LanguageHandler;
    PVOID HandlerData;
} DISPATCHER_CONTEXT, *PDISPATCHER_CONTEXT;
```

**ControlPc** , bu Işlev içindeki RIP 'in değeridir. Bu değer bir özel durum adresidir veya denetimin oluşturma işlevinin solundaki adrestir. Bu işlevin içinde denetimin bazı korunan bir yapı içinde olup olmadığını, örneğin `__try` veya için bloğunu denetlemek için RIP kullanılır `__try` / **`__except`** `__try` / **`__finally`** .

**ImageBase** , bu işlevi içeren modülün (yükleme adresi), işlev girişinde kullanılan 32 bitlik uzaklıklara eklenmek üzere ve ilgili adresleri kaydetmek üzere geriye doğru izleme bilgisi olarak görüntülenir.

**FunctionEntry** , bu işlev için işlev ve bırakma bilgisi görüntüsünü tutan RUNTIME_FUNCTION işlevi girişi için bir işaretçi sağlar.

**EstablisherFrame** , bu işlevin sabit yığın ayırma tabanının adresidir.

**Targetip** Geriye doğru izleme için devamlılık adresini belirten isteğe bağlı bir yönerge adresi sağlar. **EstablisherFrame** belirtilmemişse bu adres yok sayılır.

**ContextRecord** , sistem özel durum gönderme/bırakma kodu tarafından kullanılmak üzere özel durum bağlamına işaret eder.

**LanguageHandler** , Çağrılmakta olan dile özgü dil işleyicisi yordamına işaret eder.

**HandlerData** , bu işlev için dile özgü işleyici verilerine işaret eder.

## <a name="unwind-helpers-for-masm"></a>Masd için bırakma yardımcıları

Doğru derleme yordamlarını yazmak için, uygun. pdata ve. xdata ' ı oluşturmak için gerçek derleme yönergeleriyle paralel olarak kullanılabilecek bir dizi sözde işlem vardır. Ve, en yaygın kullanımları için sözde işlemlerin basitleştirilmiş kullanımını sağlayan bir makrolar kümesi vardır.

### <a name="raw-pseudo-operations"></a>Ham sözde işlemler

|Sözde işlem|Açıklama|
|-|-|
|PROC ÇERÇEVESI \[ :*ehandler*]|Bir işlevin yapılandırılmış özel durum işleme geri alma davranışı için. pdata içinde bir işlev tablosu girişi ve. xdata içindeki bırakma bilgilerini oluşturmak için MASı 'nin oluşmasına neden olur.  *Ehandler* varsa, bu proc. xdata 'a dile özgü işleyici olarak girilir.<br /><br /> ÇERÇEVE özniteliği kullanıldığında, arkasından bir gelmelidir. ENDPROLOG yönergesi.  İşlev bir yaprak işlevsiyse ( [işlev türlerinde](../build/stack-usage.md#function-types)tanımlandığı gibi), bu sözde işlemlerin geri KALANı gibi çerçeve özniteliği gereksizdir.|
|. PUSHREG *kaydı*|Belirtilen kayıt numarası için, prolog 'deki geçerli sapmayı kullanarak bir UWOP_PUSH_NONVOL bırakma kodu girişi oluşturur.<br /><br /> Yalnızca kalıcı tamsayı Yazmaçları ile kullanın.  Geçici yazmaçların gönderimleri için bir kullanın. Bunun yerine ALLOCSTACK 8|
|. SETFRAME *kaydı*, *konum*|Belirtilen yazmaç ve sapmayı kullanarak, çerçeve kaydı alanını ve geriye doğru izleme bilgilerinde yer alan kaydırmayı doldurur. Aralık 16 ' dan büyük ve 240 ' e eşit veya daha küçük olmalıdır. Bu yönerge Ayrıca, geçerli prolog sapmasını kullanarak belirtilen kayıt için bir UWOP_SET_FPREG bırakma kodu girişi oluşturur.|
|. ALLOCSTACK *boyutu*|Prolog 'daki geçerli fark için belirtilen boyuta sahip bir UWOP_ALLOC_SMALL veya UWOP_ALLOC_LARGE oluşturur.<br /><br /> *Boyut* işleneni 8 ' in katı olmalıdır.|
|. SAVEREG *kaydı*, *konum*|Geçerli başlangıç sapmasını kullanarak belirtilen yazmaç ve uzaklığa yönelik bir UWOP_SAVE_NONVOL ya da UWOP_SAVE_NONVOL_FAR bırakma kodu girişi oluşturur. Masa en verimli kodlamayı seçer.<br /><br /> *kaydırın* pozitif olması ve 8 ' in katı olması gerekir. *göreli konum* , genellikle RSP 'deki veya bir çerçeve işaretçisi kullanılıyorsa, ölçeklendirilmemiş çerçeve işaretçisi olan yordamın çerçevesinin tabanına göredir.|
|. SAVEXMM128 *kaydı*, *konum*|Belirtilen XMM kaydı için bir UWOP_SAVE_XMM128 veya UWOP_SAVE_XMM128_FAR geriye doğru izleme kodu girdisi ya da geçerli prolog sapmasını kullanarak bir konum üretir. Masa en verimli kodlamayı seçer.<br /><br /> *kaydırın* pozitif ve 16 ' dan fazla olması gerekir.  *göreli konum* , genellikle RSP 'deki veya bir çerçeve işaretçisi kullanılıyorsa, ölçeklendirilmemiş çerçeve işaretçisi olan yordamın çerçevesinin tabanına göredir.|
|. PUSHFRAME \[ *kodu*]|Bir UWOP_PUSH_MACHFRAME bırakma kodu girişi oluşturur. İsteğe bağlı *kod* belirtilmişse, geriye doğru izleme kod girişine 1 değiştiricisi verilir. Aksi takdirde değiştirici 0 ' dır.|
|.ENDPROLOG|Prolog bildirimlerinin sonuna işaret eder.  İşlevin ilk 255 baytından oluşmalıdır.|

Aşağıda opkodların çoğunun uygun kullanımı ile birlikte örnek bir işlev girişi verilmiştir:

```MASM
sample PROC FRAME
    db      048h; emit a REX prefix, to enable hot-patching
    push rbp
    .pushreg rbp
    sub rsp, 040h
    .allocstack 040h
    lea rbp, [rsp+020h]
    .setframe rbp, 020h
    movdqa [rbp], xmm7
    .savexmm128 xmm7, 020h ;the offset is from the base of the frame
                           ;not the scaled offset of the frame
    mov [rbp+018h], rsi
    .savereg rsi, 038h
    mov [rsp+010h], rdi
    .savereg rdi, 010h ; you can still use RSP as the base of the frame
                       ; or any other register you choose
    .endprolog

; you can modify the stack pointer outside of the prologue (similar to alloca)
; because we have a frame pointer.
; if we didn't have a frame pointer, this would be illegal
; if we didn't make this modification,
; there would be no need for a frame pointer

    sub rsp, 060h

; we can unwind from the next AV because of the frame pointer

    mov rax, 0
    mov rax, [rax] ; AV!

; restore the registers that weren't saved with a push
; this isn't part of the official epilog, as described in section 2.5

    movdqa xmm7, [rbp]
    mov rsi, [rbp+018h]
    mov rdi, [rbp-010h]

; Here's the official epilog

    lea rsp, [rbp+020h] ; deallocate both fixed and dynamic portions of the frame
    pop rbp
    ret
sample ENDP
```

Bitiş örneği hakkında daha fazla bilgi için bkz. [x64 giriş ve bitiş](prolog-and-epilog.md) [kodu](prolog-and-epilog.md#epilog-code) .

### <a name="masm-macros"></a>Masa makroları

[Ham sözde işlemlerin](#raw-pseudo-operations)kullanımını basitleştirmek için, ksamd64. inc ' de tanımlanan ve tipik yordam ve epengues oluşturmak için kullanılabilen bir dizi makro vardır.

|Makroya|Açıklama|
|-|-|
|alloc_stack (n)|N baytlık bir yığın çerçevesini ayırır (kullanarak `sub rsp, n` ) ve uygun geriye doğru izleme bilgilerini (. ALLOCSTACK n) yayar|
|save_reg *reg*, *loc*|Kalıcı kayıt *reg* ' i RSP kayması *loc*' de yığına kaydeder ve uygun geriye doğru izleme bilgilerini yayar. (. savereg Reg, Loc)|
|push_reg *reg*|Yığında kalıcı kayıt *reg* gönderir ve uygun geriye doğru izleme bilgilerini yayar. (. PUSHREG reg)|
|rex_push_reg *reg*|2 baytlık gönderim kullanarak yığında kalıcı kayıt kaydeder ve uygun geriye doğru izleme bilgilerini (. PUSHREG reg) yayar.  İşlevin çalışır durumda olduğundan emin olmak için bu makroyu, işlev içindeki ilk yönerge ise kullanın.|
|save_xmm128 *reg*, *loc*|Kalıcı bir XMM kayıt *reg* dosyasını RSP kayması *loc*yığınına kaydeder ve uygun geriye doğru izleme bilgilerini (. SAVEXMM128 Reg, Loc) yayar|
|set_frame *reg*, *konum*|Çerçeve kaydı *reg* ' i RSP + *kayması* ( `mov` ya da bir kullanarak) olarak ayarlar `lea` ve uygun geriye doğru izleme bilgilerini (. set_frame Reg, sapmayı) yayar|
|push_eflags|EFLAGS `pushfq` yönergesini bir yönergeyle iter ve uygun geriye doğru izleme bilgilerini (. alloc_stack 8) yayar|

Makroların uygun kullanımıyla birlikte örnek bir işlev girişi aşağıda verilmiştir:

```MASM
sampleFrame struct
    Fill     dq ?; fill to 8 mod 16
    SavedRdi dq ?; Saved Register RDI
    SavedRsi dq ?; Saved Register RSI
sampleFrame ends

sample2 PROC FRAME
    alloc_stack(sizeof sampleFrame)
    save_reg rdi, sampleFrame.SavedRdi
    save_reg rsi, sampleFrame.SavedRsi
    .end_prolog

; function body

    mov rsi, sampleFrame.SavedRsi[rsp]
    mov rdi, sampleFrame.SavedRdi[rsp]

; Here's the official epilog

    add rsp, (sizeof sampleFrame)
    ret
sample2 ENDP
```

## <a name="unwind-data-definitions-in-c"></a>C 'de veri bırakma tanımları

Geriye doğru izleme verilerinin C açıklaması aşağıdadır:

```C
typedef enum _UNWIND_OP_CODES {
    UWOP_PUSH_NONVOL = 0, /* info == register number */
    UWOP_ALLOC_LARGE,     /* no info, alloc size in next 2 slots */
    UWOP_ALLOC_SMALL,     /* info == size of allocation / 8 - 1 */
    UWOP_SET_FPREG,       /* no info, FP = RSP + UNWIND_INFO.FPRegOffset*16 */
    UWOP_SAVE_NONVOL,     /* info == register number, offset in next slot */
    UWOP_SAVE_NONVOL_FAR, /* info == register number, offset in next 2 slots */
    UWOP_SAVE_XMM128 = 8, /* info == XMM reg number, offset in next slot */
    UWOP_SAVE_XMM128_FAR, /* info == XMM reg number, offset in next 2 slots */
    UWOP_PUSH_MACHFRAME   /* info == 0: no error-code, 1: error-code */
} UNWIND_CODE_OPS;

typedef union _UNWIND_CODE {
    struct {
        UBYTE CodeOffset;
        UBYTE UnwindOp : 4;
        UBYTE OpInfo   : 4;
    };
    USHORT FrameOffset;
} UNWIND_CODE, *PUNWIND_CODE;

#define UNW_FLAG_EHANDLER  0x01
#define UNW_FLAG_UHANDLER  0x02
#define UNW_FLAG_CHAININFO 0x04

typedef struct _UNWIND_INFO {
    UBYTE Version       : 3;
    UBYTE Flags         : 5;
    UBYTE SizeOfProlog;
    UBYTE CountOfCodes;
    UBYTE FrameRegister : 4;
    UBYTE FrameOffset   : 4;
    UNWIND_CODE UnwindCode[1];
/*  UNWIND_CODE MoreUnwindCode[((CountOfCodes + 1) & ~1) - 1];
*   union {
*       OPTIONAL ULONG ExceptionHandler;
*       OPTIONAL ULONG FunctionEntry;
*   };
*   OPTIONAL ULONG ExceptionData[]; */
} UNWIND_INFO, *PUNWIND_INFO;

typedef struct _RUNTIME_FUNCTION {
    ULONG BeginAddress;
    ULONG EndAddress;
    ULONG UnwindData;
} RUNTIME_FUNCTION, *PRUNTIME_FUNCTION;

#define GetUnwindCodeEntry(info, index) \
    ((info)->UnwindCode[index])

#define GetLanguageSpecificDataPtr(info) \
    ((PVOID)&GetUnwindCodeEntry((info),((info)->CountOfCodes + 1) & ~1))

#define GetExceptionHandler(base, info) \
    ((PEXCEPTION_HANDLER)((base) + *(PULONG)GetLanguageSpecificDataPtr(info)))

#define GetChainedFunctionEntry(base, info) \
    ((PRUNTIME_FUNCTION)((base) + *(PULONG)GetLanguageSpecificDataPtr(info)))

#define GetExceptionDataPtr(info) \
    ((PVOID)((PULONG)GetLanguageSpecificData(info) + 1)
```

## <a name="see-also"></a>Ayrıca bkz.

[x64 yazılım kuralları](../build/x64-software-conventions.md)
