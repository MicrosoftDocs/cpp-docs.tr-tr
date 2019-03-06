---
title: x64 özel durum işleme
ms.date: 12/17/2018
helpviewer_keywords:
- C++ exception handling, x64
- exception handling, x64
ms.assetid: 41fecd2d-3717-4643-b21c-65dcd2f18c93
ms.openlocfilehash: 7dab7f3b6593bf4eaed1b8c804deb915677ccf5b
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422981"
---
# <a name="x64-exception-handling"></a>x64 özel durum işleme

Yapılandırılmış özel durum işleme ve kodlama kurallarını ve x64 davranışı C++ özel durum işleme genel bakış. Özel durum işleme hakkında genel bilgi için bkz. [özel durum işleme Visual C++'ta](../cpp/exception-handling-in-visual-cpp.md).

## <a name="unwind-data-for-exception-handling-debugger-support"></a>Özel durum işleme, hata ayıklayıcı desteği için veri bırakma

Çeşitli veri yapıları, özel durum işleme ve hata ayıklama desteği için gereklidir.

### <a name="struct-runtimefunction"></a>struct RUNTIME_FUNCTION

Tablo tabanlı özel durum işleme, yığın alanı tahsis edin ya da başka bir işlevi (örneğin, yapraksız işlevler) tüm işlevler için bir tablo girişi gerektirir. İşlev tablo girişleri biçime sahiptir:

|||
|-|-|
|ULONG|Başlangıç adresi işlevi|
|ULONG|Bitiş adresi işlevi|
|ULONG|Bırakma bilgisi adresi|

RUNTIME_FUNCTION yapısını bellekte DWORD hizalanmış olmalıdır. Görüntü göreli tüm adreslerin, diğer bir deyişle, 32-bit uzaklıkları görüntünün işlevi tablo girişi içeren başlangıç adresinden oldukları. Bu girişler sıralanır ve je typu PE32 + görüntü .pdata bölümünde yerleştirin. [JIT derleyicileri] dinamik olarak üretilen işlevler için bu işlevleri desteklemek için çalışma zamanı ya da RtlInstallFunctionTableCallback ya da RtlAddFunctionTable işletim sistemi için bu bilgiyi sağlamak için kullanmanız gerekir. Bunun yapılmaması, işleme ve işlemlerde hata ayıklamanın güvenilir özel durumu oluşur.

### <a name="struct-unwindinfo"></a>struct UNWIND_INFO

Geriye doğru izleme veri bilgisi yapısı, yığın işaretçisi ve kalıcı kayıtlar yığında kaydedildiği bir işleve sahip etkileri kaydetmek için kullanılır:

|||
|-|-|
|UBYTE: 3|Sürüm|
|UBYTE: 5|Bayraklar|
|UBYTE|Giriş boyutu|
|UBYTE|Geriye doğru izleme kodları sayısı|
|UBYTE: 4|Çerçeve kaydı|
|UBYTE: 4|Çerçeve kaydı uzaklık (ölçeği)|
|USHORT \* n|Bırakma kodları dizisi|
|değişken|Formun (1) veya (2) aşağıda olabilir|

(1) özel durum işleyicisi

|||
|-|-|
|ULONG|Özel durum işleyicisinin adresi|
|değişken|Dile özel işleyici veriler (isteğe bağlı)|

(2) Zincirleme Bırakma bilgi

|||
|-|-|
|ULONG|Başlangıç adresi işlevi|
|ULONG|Bitiş adresi işlevi|
|ULONG|Bırakma bilgisi adresi|

UNWIND_INFO yapısını bellekte DWORD hizalanmış olmalıdır. Her bir alan anlamı aşağıda verilmiştir:

- **Sürüm**

   Geriye doğru izleme verileri, şu anda 1 sürüm numarası.

- **bayrakları**

   Üç bayraktan şu anda tanımlanır:

   |Bayrağı|Açıklama|
   |-|-|
   |`UNW_FLAG_EHANDLER`| İşlevi, özel durumları incelemek için gereken işlevleri ararken çağrılması gereken bir özel durum işleyicisine sahiptir.|
   |`UNW_FLAG_UHANDLER`| İşlev bir özel durumu geriye doğru izleme sırasında çağrılması gereken bir sonlandırma işleyicisi sahiptir.|
   |`UNW_FLAG_CHAININFO`| Bu bilgileri yapısı, birincil bir yordam değil geriye doğru. Bunun yerine, zincirleme bir önceki RUNTIME_FUNCTION girişi içeriğini girdidir bilgilerindeki. Bilgiler için bkz: [Chained bırakma bilgi yapıları](#chained-unwind-info-structures). Bu bayrağı ayarlarsanız, UNW_FLAG_EHANDLER ve UNW_FLAG_UHANDLER bayrakları temizlenmelidir. Ayrıca, çerçeve kayıt ve sabit yığın ayırma alanları bilgilerindeki birincil aynı değerlere sahip olmalıdır.|

- **Giriş boyutu**

   İşlev giriş bayt cinsinden uzunluğu.

- **Geriye doğru izleme kodları sayısı**

   Geriye doğru izleme kodları dizideki yuva sayısı. Bazı kodları, örneğin, UWOP_SAVE_NONVOL bırakma dizideki birden fazla yuvası gerektirir.

- **Çerçeve kaydı**

   Sıfır olmayan, sonra işlev bir çerçeve işaretçisi (dp) kullanır ve bu alan UNWIND_CODE düğümleri işlemi bilgileri alan için aynı kodlama kullanılarak çerçeve işaretçisi olarak kullanılan kalıcı kayıt sayısıdır.

- **Çerçeve kaydı uzaklık (ölçeği Genişletilmiş)**

   Çerçeve yazmaç alanı sıfır değilse, bu alan için FP uygulanan RSP ölçeklendirilmiş uzaklığı olan oluşturulduğunda kaydedin. Gerçek FP kaydına ayarlanır RSP + 16 \* 0 uzaklıkları 240 izin vererek, bu sayı. Bu uzaklığı daha kısa yönergeleri (daha fazla yönerge 8-bit imzalı sapma formu kullanabilirsiniz) aracılığıyla daha iyi kod yoğunluğu izin vererek, dinamik yığın çerçevesi için yerel yığın ayırma ortasına FP kaydına işaret eden izin verir.

- **Bırakma kodları dizisi**

   Kalıcı kayıtlar ve RSP giriş etkisini açıklar öğelerin bir dizisi. Tek tek öğelerin anlamı UNWIND_CODE üzerinde bakın. Hizalama amacıyla, bu dizinin her zaman bir çift sayı girişlerinin sahiptir ve son giriş potansiyel olarak kullanılmaz. Bu durumda, geriye doğru izleme kodları alan sayısı tarafından belirtilenden uzun bir dizidir.

- **Özel durum işleyicisinin adresi**

   İşlevin dile özgü özel durum veya bayrak UNW_FLAG_CHAININFO açıktır ve UNW_FLAG_EHANDLER veya UNW_FLAG_UHANDLER bayraklarından birini ayarlanırsa sonlandırma işleyicisinde, bir resim göreli işaretçisi.

- **Dile özel işleyici veri**

   İşlevin dile özgü özel durum işleyicisi verileri. Bu verilerin biçimi belirtilmemiş ve tamamen kullanılan belirli bir özel durum işleyicisi tarafından belirlenir.

- **Zincirleme Bırakma bilgi**

   UNW_FLAG_CHAININFO bayrağı ayarlandıysa UNWIND_INFO yapısı üç UWORDs ile sona erer.  Bu UWORDs işlevi zincirleme RUNTIME_FUNCTION bilgilerini temsil eder.

### <a name="struct-unwindcode"></a>struct UNWIND_CODE

Geriye doğru izleme kodu dizi işlemlerin sırasını RSP ve kalıcı kayıtlar etkileyen giriş bölümünde kaydetmek için kullanılır. Her kod öğesi bu biçime sahiptir:

|||
|-|-|
|UBYTE|Uzaklık içinde giriş|
|UBYTE: 4|Bırakma işlemi kodu|
|UBYTE: 4|İşlem bilgileri|

Dizi giriş uzaklığı azalan göre sıralanır.

#### <a name="offset-in-prolog"></a>Uzaklık içinde giriş

Yönergenin bitiminden giriş başından uzaklığı, 1 (diğer bir deyişle, sonraki yönergesi başlangıç uzaklığını) yanı sıra bu işlemi gerçekleştirir.

#### <a name="unwind-operation-code"></a>Bırakma işlemi kodu

Not: Belirli işlem kodlarını yerel yığın çerçevesi bir değeri işaretsiz bir uzaklık gerektirir. Bu uzaklık, en başından itibaren diğer bir deyişle, en düşük sabit yığın ayırma adresi dayalıdır. Çerçeve kaydı alanı UNWIND_INFO sıfırsa bu uzaklık RSP dayalıdır. Çerçeve kaydı alanın sıfır değilse, FP kaydına oluşturulduğunda RSP bulunduğu gelen uzaklık budur. Bu FP kaydına FP kayıt uzaklığı eksi eşittir (16 \* ölçeklendirilmiş çerçeve UNWIND_INFO öğesinde uzaklık kaydı). Ardından FP kaydına kullanılıyorsa FP kaydına giriş bölümünde kurulduktan sonra bir uzaklık alma herhangi bir geriye doğru izleme kodu yalnızca kullanılmalıdır.

Tüm işlem için `UWOP_SAVE_XMM128` ve `UWOP_SAVE_XMM128_FAR`uzaklık her zaman 8'in katı, çünkü tüm yığın değerlerini gösteren öğelerdir (yığın, her zaman 16 bayt hizalı) 8 baytlık sınırlardaki depolanır. Kısa bir uzaklık (küçüktür, 512 K) alır işlem kodları için bu kod için düğümleri son USHORT 8 ile bölünen uzaklığı tutar. İşlem kodları, uzun bir uzaklık alır (512K < = < 4 GB uzaklık), bu kod için son iki USHORT düğüm uzaklık (küçük endian biçiminde) tutun.

İşlem için `UWOP_SAVE_XMM128` ve `UWOP_SAVE_XMM128_FAR`, tüm 128-bit XMM işlemleri 16 bayt hizalı bellek üzerinde gerçekleşmesi gerektiği uzaklık her zaman 16 sayısının katı değil. Bu nedenle, bir ölçek faktörü 16 için kullanılan `UWOP_SAVE_XMM128`, 1 milyondan az uzaklıklarını erişimine izin verme.

Geriye doğru izlemeyi işlem kodu şu değerlerden biri:

- `UWOP_PUSH_NONVOL` (0) 1 düğüm

  Kalıcı tamsayı kaydını, azaltma RSP 8 tarafından gönderin. İşlem bilgisi kayıt sayısıdır. Sonuç, kısıtlamalar nedeniyle `UWOP_PUSH_NONVOL` geriye doğru izleme kodları ilk giriş bölümünde görünür ve gelenlere, geriye doğru izleme kodu dizideki en son gerekir. Bu göreli sıralamasını diğer tüm geriye doğru izleme kodları uygular. `UWOP_PUSH_MACHFRAME`.

- `UWOP_ALLOC_LARGE` (1) 2 veya 3 düğüm

  Yığın üzerinde büyük ölçekli bir alan ayırın. İki biçimi vardır. İşlem bilgisi 0 ve ardından bölü ayırma boyutu eşitse 8 512 K - 8 adede kadar bir ayırma izin İleri yuvasında kaydedilir. İşlem bilgisi eşittir 1 sonra ayırma ölçeklendirilmemiş boyutunu sonraki iki yuvaları ayırmaya olanak vererek little endian biçiminde kaydedilir en fazla 4GB - 8.

- `UWOP_ALLOC_SMALL` (2) 1 düğüm

  Yığın üzerinde küçük ölçekli bir alan ayırın. Ayırmanın boyutu işlemi bilgileri alandır \* 8 + 8, 8 ayırma 128 bayt izin verme.

  Geriye doğru izleme kodu yığın ayırma için her zaman en kısa olası kodlamayı kullanmanız gerekir:

  |**Ayırma boyutu**|**Kod geriye doğru izleme**|
  |-|-|
  |8 ile 128 bayt|`UWOP_ALLOC_SMALL`|
  |136 için 512K - 8 bayt|`UWOP_ALLOC_LARGE`, işlem bilgisi = 0|
  |512K için 4G - 8 bayt|`UWOP_ALLOC_LARGE`, işlem bilgisi = 1|

- `UWOP_SET_FPREG` (3) 1 düğüm

  Bazı geçerli RSP uzaklığı için kayıt ayarlayarak çerçeve işaretçisi kaydı oluşturun. Uzaklık içinde UNWIND_INFO çerçeve kaydı uzaklık (Genişletilmiş) alanına eşittir \* 16, uzaklık 0 ile 240 izin verme. Bir uzaklık kullanımına kod yoğunluklu kısa yönerge formları kullanarak daha fazla erişim sağlayarak yardımcı sabit yığın ayırma ortasını işaret eden bir çerçeve işaretçisini oluşturma izin verir. İşlem bilgisi alanının ayrılmıştır ve kullanılmamalıdır.

- `UWOP_SAVE_NONVOL` (4) 2 düğüm

  Kalıcı tamsayı kaydını MOV yerine bir anında İLETME kullanarak tasarruf edin. Bu kod için öncelikle kullanılır *sabit*, önceden ayrılmış olan bir konumda yığınına bir kayıt kaydedildiği. İşlem bilgisi kayıt sayısıdır. Ölçeği genişletilmiş-8 yığın olarak uzaklık sonraki kaydedilen işlem kodu yuvası Not yukarıda açıklandığı gibi geriye doğru izleme.

- `UWOP_SAVE_NONVOL_FAR` (5) 3 düğüm

  Kalıcı tamsayı kaydını yığın MOV yerine PUSH kullanılarak mesafesi ile tasarruf edin. Bu kod için öncelikle kullanılır *sabit*, önceden ayrılmış olan bir konumda yığınına bir kayıt kaydedildiği. İşlem bilgisi kayıt sayısıdır. Ölçeklendirilmemiş yığın uzaklığı sonraki kaydedilir Not yukarıda açıklandığı gibi iki işlem kodu yuvaları bırakma.

- `UWOP_SAVE_XMM128` (8) 2 düğüm

  Tüm 128 bit XMM kaydının yığında kaydedin. İşlem bilgisi kayıt sayısıdır. Ölçeği genişletilmiş-16 yığın olarak uzaklık sonraki yuvaya kaydedilir.

- `UWOP_SAVE_XMM128_FAR` (9) 3 düğüm

  Tüm 128 bit XMM kaydının yığın mesafesi ile tasarruf edin. İşlem bilgisi kayıt sayısıdır. Ölçeklendirilmemiş yığın uzaklığı, sonraki iki yuvada da kaydedilir.

- `UWOP_PUSH_MACHFRAME` (10) 1 düğüm

  Makine çerçeve gönderin.  Bu, bir donanım kesme veya özel durum etkisini kaydetmek için kullanılır. İki biçimi vardır. İşlem bilgisi 0 eşitse, bu kareler birini yığına:

  |||
  |-|-|
  |RSP+32|SS|
  |RSP + 24|Eski RSP|
  |RSP + 16|EFLAGS|
  |RSP + 8|CS|
  |RSP|KOPYALAMA|

  Ardından işlem bilgisi 1 değerine eşitse, bu kareler birini itilmiş:

  |||
  |-|-|
  |RSP + 40|SS|
  |RSP+32|Eski RSP|
  |RSP + 24|EFLAGS|
  |RSP + 16|CS|
  |RSP + 8|KOPYALAMA|
  |RSP|Hata kodu|

  Bu geriye doğru izleme kodu asla gerçekten yürütülür ancak bunun yerine bir kesme yordamı gerçek giriş noktasından önce görünür ve yalnızca bir makine çerçevenin gönderme benzetimi için bir yer sağlamak için var olan bir kukla giriş bölümünde her zaman görünür. `UWOP_PUSH_MACHFRAME` Makine kavramsal olarak bu işlem yapmış gösteren benzetimi kaydeder:

  1. RIP dönüş adresi yığının en üstünden pop *Temp*
  
  1. Anında iletme SS

  1. Eski RSP anında iletme

  1. EFLAGS Gönder

  1. Anında iletme CS

  1. Anında iletme *Temp*

  1. Hata kodu (op bilgisi 1 değerine eşitse) anında iletme

  Benzetim `UWOP_PUSH_MACHFRAME` 40 işlemi azaltır RSP (op bilgisi 0 değerine eşittir) veya 48 (op bilgisi eşittir 1).

#### <a name="operation-info"></a>İşlem bilgileri

İşlem bilgileri BITS anlamını işlem koduna bağlıdır. Genel amaçlı (tamsayı) kaydı kodlamak için bu eşleme kullanılır:

|||
|-|-|
|0|RAX|
|1.|RCX|
|2|RDX|
|3|RBX|
|4|RSP|
|5|RBP|
|6|RSI|
|7|RDI|
|8-15|R8 R15 kayıtları için|

### <a name="chained-unwind-info-structures"></a>Zincirleme Bırakma bilgi yapıları

UNW_FLAG_CHAININFO bayrağı ayarlandıysa, bir geriye doğru izleme bilgisi yapısı ikincil bir ise ve paylaşılan özel durum işleyicisi/zincirleme-bilgisi adres alanı birincil geriye doğru izleme bilgileri içerir. Bu örnek kod, birincil alır. geriye doğru izleme bilgilerini olduğunu varsayarak, `unwindInfo` kümesine sahip yapı bayrağı ayarlanmış olduğu.

```cpp
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);
```

Zincir bilgisi iki durumlarda yararlı olur. İlk olarak, bitişik olmayan kod parçaları için kullanılabilir. Zincirleme bilgileri kullanarak, birincil geriye doğru izleme bilgisi geriye doğru izleme kodları diziden yinelenen olmadığı için gerekli geriye doğru izleme bilgileri boyutunu azaltabilirsiniz.

Zincirleme bilgi, geçici kayıtları gruplamak için de kullanabilirsiniz. Derleyici, işlev girişi giriş dışında oluncaya kadar bazı geçici kayıtları geciktirebilir. Bu işlev gruplandırılmış kodundan önce kısmı için birincil geriye doğru izleme bilgileri sağlayarak kaydedin ve ardından ayarlama burada geriye doğru izleme kodları zincirleme bilgileri kalıcı yazmaçların kaydeder yansıttığı sıfır boyutlu bilgisi zincirleme. Bu durumda, geriye doğru izleme kodları tüm UWOP_SAVE_NONVOL örnekleridir. Bir anında İLETME kullanarak kalıcı Yazmaçları kaydeder veya bir sabit ek yığın ayırma kullanarak RSP kaydı değiştirir, bir gruplandırma desteklenmiyor.

UNW_FLAG_CHAININFO kümesi can, UNWIND_INFO öğesi, UNW_FLAG_CHAININFO de sahip bir RUNTIME_FUNCTION girişi içeren sahip UNWIND_INFO öğesi olarak da adlandırılır *birden çok sabit*. Sonuç olarak, zincirleme işaretçileri, temizlenmiş kümesine sahip bir UNWIND_INFO öğe ulaşması bilgilerindeki; Gerçek yordam giriş noktasına işaret birincil UNWIND_INFO öğesi budur.

## <a name="unwind-procedure"></a>Bırakma yordamı

Geriye doğru izleme kodu dizisi, azalan düzende sıralanır. Bir özel durum oluştuğunda, bağlamı tam bir bağlam kaydını işletim sistemi tarafından depolanır. Özel durum dağıtma mantığı sonra çağrılan bir özel durum işleyici bulmak için şu adımları tekrar tekrar yürütür:

1. Bağlam kaydında depolanmış geçerli RIP geçerli işlevi (veya zincirleme UNWIND_INFO girişleri için işlev bölümü) açıklayan bir RUNTIME_FUNCTION tablo girişi aramak için kullanın.

1. İşlev tablo girişi bulunursa, bir yaprak işlevde ise ve RSP Dönüş işaretçisi doğrudan giderir. [Rsp] dönüş işaretçi güncelleştirilmiş bağlamında depolanır, 8 ile sanal RSP artırılır ve 1. adım yinelenir.

1. İşlev bir tablo girişi bulunursa RIP üç bölgede: a) bir sonuç, (b) giriş veya c) kodda özel durum işleyicisi tarafından ele alınacak.

   - Büyük/küçük harf bir) bir sonuç içinde olduğu sonra denetim işlevi bırakarak, bu işlev için bu durumla ilişkili hiçbir özel durum işleyicisi olabilir ve çağıran işlevin bağlamında işlem bitiş etkilerini ettirilmelidir. RIP içinde bir sonuç, kod akışı üzerinde olup olmadığını belirlemek için incelenir. Bu kod akış için meşru bir sonuç son kısmını eşleştirilebildiği sonra onu içindedir ve sonuç kalan kısmı kullanılmıştır, her yönerge olarak güncelleştirilen içerik kaydı ile işlenir. Bundan sonra 1. adım yinelenir.

   - Denetim RIP prolog içinde yer alıyorsa durumda b) işlev girilmeden, bu işlev için bu durumla ilişkili hiçbir özel durum işleyicisi olabilir ve çağıran işlevin bağlamında işlem için giriş etkilerini geri alınmalıdır. RIP işlevi başından uzaklık geriye doğru izleme bilgilerini kodlanmış giriş boyutuna eşit veya küçükse RIP giriş içindedir. Giriş etkilerini, İleri aracılığıyla geriye doğru izleme kodları dizi işlevi başından uzaklığı RIP eşit veya daha az bir uzaklık ile ilk giriş için tarama, daha sonra geri kalan tüm öğelerin bırakma kod dizideki etkisini sapmasına. 1. adım daha sonra yinelenir.

   - RIP bir giriş veya epilog ve işlev içinde değilse, büyük/küçük harf c) (UNW_FLAG_EHANDLER ayarlanır) bir özel durum işleyicisine sahiptir ve dile özel işleyici çağrılır. İşleyici verilerini tarar ve çağrıları işlevleri uygun şekilde filtreleyin. Dile özel işleyici, özel durumu işlenmiş veya arama devam etmesi gereken olduğunu döndürebilir. Bir bırakma doğrudan de başlatabilirsiniz.

1. İşlenmiş durumu dile özel işleyici döndürür, ardından yürütme devam edilir, özgün içerik kaydı kullanarak.

1. Dile özel işleyici yok ya da "aramaya devam" durum işleyicisini döndürür, ardından bağlam kaydı çağıran durumunu çözülmelidir. Bu, her birinin etkisi geri alma tüm geriye doğru izleme kodu dizi öğeleri işleme tarafından gerçekleştirilir. 1. adım daha sonra yinelenir.

Olduğunda zincirleme bırakma bilgi dahil, temel adımları hala izlenir. Tek fark, dizinin sonuna ulaşıldığında, bir girişin etkileri geriye doğru izleme bırakma kod dizisi yürüyen, ardından üst geriye doğru izleme bilgilerine bağlı olduğu ve burada bulunan tüm geriye doğru izleme kodu dizisi öğrendiniz. Bağlama sırasında bir geriye doğru izleme bilgisi UNW_CHAINED_INFO bayrağı olmadan kadar devam eder ve daha sonra geriye doğru izleme kodu dizisinin tamamlanır.

En küçük kümesini veri bırakma 8 bayt'tır. Bu, yalnızca 128 bayt veya daha az yığın ayrılan ve büyük olasılıkla bir kalıcı kayıt kaydedilmiş bir işlevi temsil eder. Bu da zincirleme bir boyutudur hiçbir geriye doğru izleme kodları ile sıfır uzunluklu giriş bilgileri yapısını geriye doğru izleme.

## <a name="language-specific-handler"></a>Dile özel işleyici

UNW_FLAG_EHANDLER veya UNW_FLAG_UHANDLER bayrakları ayarlanmış her dile özel işleyici göreli adresini UNWIND_INFO öğesinde mevcuttur. Önceki bölümde açıklandığı gibi dile özel işleyici, özel durum işleyicisi için arama bir parçası olarak veya bir geriye doğru izleme bir parçası olarak adlandırılır. Bu prototip şunları içerir:

```cpp
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (
    IN PEXCEPTION_RECORD ExceptionRecord,
    IN ULONG64 EstablisherFrame,
    IN OUT PCONTEXT ContextRecord,
    IN OUT PDISPATCHER_CONTEXT DispatcherContext
);
```

**ExceptionRecord** standart Win64 tanımını içeren bir özel durum kaydı için bir işaretçi sağlar.

**EstablisherFrame** bu işlev için sabit bir yığın ayırma taban adresidir.

**ContextRecord** noktaları (özel durum işleyicisi durumda) özel duruma neden zaman ya da geçerli özel durum bağlamı için "bırakma" bağlamında (sonlandırma işleyicisi durumda).

**DispatcherContext** bu işlev için dağıtıcı bağlamını işaret eder. Bu tanım içerir:

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

**ControlPc** RIP bu işlev içindeki değeridir. Bu, bir özel durum adresini veya denetim kurmanın işlevi sola adresi değerdir. RIP denetimi bu işlevin içindeki bazı korunan yapı içindeki gibi olup olmadığını belirlemek için kullanılan bir `__try` engellemek için `__try` / `__except` veya `__try` / `__finally`.

**ImageBase** temel (yük adresi), işlev girişi kullanılan 32-bit uzaklıkları eklenmesi ve göreli adreslerini kaydetmek için bu işlevi içeren modül görüntüsüdür.

**FunctionEntry** kaynakları RUNTIME_FUNCTION işaretçi bir işlev tutarak işlev giriş ve bu işlev için bilgileri görüntü tabanlı göreli adreslerini bırakma.

**EstablisherFrame** bu işlev için sabit bir yığın ayırma taban adresidir.

**TargetIp** geriye doğru izleme devamlılık adresini belirten bir isteğe bağlı bir yönerge adresi sağlar. Bu adres yoksayılır **EstablisherFrame** belirtilmedi.

**ContextRecord** gönderme ve bırakma Sistem özel durum kodu tarafından kullanılmak üzere özel durum bağlamı işaret eder.

**LanguageHandler** çağrılan dile özgü dil işleyici rutinini işaret eder.

**HandlerData** bu işlev için dile özel işleyici veri işaret eder.

## <a name="unwind-helpers-for-masm"></a>MASM için Yardımcıları Bırakma

Uygun derleme yordamları yazmak için bir dizi gerçek derleme yönergeleri ile paralel uygun .pdata ve .xdata oluşturmak için kullanılabilir sözde işlemlerini yoktur. Yok makroları sağlayan bir dizi sözde işlemler için en yaygın kullanımları kullanımını da Basitleştirilmiş.

### <a name="raw-pseudo-operations"></a>Ham sözde işlemler

|Sahte işlem|Açıklama|
|-|-|
|PROC çerçeve \[:*ehandler*]|Neden bir işlev oluşturmak için MASM tablo .pdata girişi ve geriye doğru izleme bilgilerini sanal işlem bulunur, bir işlevin yapılandırılmış özel durum işleme geriye doğru davranışı.  Varsa *ehandler* varsa, bu yordam xdata'daki dile özel işleyici olarak girilir.<br /><br /> Çerçeve öznitelik kullanıldığında, gelmelidir bir. ENDPROLOG yönergesi.  İşlev bir yaprak işlevi ise (sınıfında tanımlandığı gibi [işlev türleri](../build/stack-usage.md#function-types)) bu sözde işlemler geri kalanında olduğu gibi KARE öznitelik gereksizdir.|
|. PUSHREG *kaydetme*|Bir giriş geçerli kullanarak belirtilen kayıt numarası için UWOP_PUSH_NONVOL geriye doğru izleme kodu girişi oluşturur.<br /><br /> Bu, yalnızca kalıcı tamsayı yazmaçları ile kullanılmalıdır.  Volatile yazmaçların bildirimler için kullanın. bir. ALLOCSTACK 8'de, bunun yerine|
|. SETFRAME *kaydetme*, *uzaklığı*|Çerçeve doldurur, alan ve uzaklık uzaklığı ve belirtilen kaydı kullanarak geriye doğru izleme bilgileri kaydedin. Uzaklık 16 olmalıdır ve 240 küçüktür veya eşittir. Bu yönerge ayrıca UWOP_SET_FPREG bırakma kod girdisi geçerli başlangıç uzaklığını kullanarak belirtilen kayıt oluşturur.|
|. ALLOCSTACK *boyutu*|UWOP_ALLOC_SMALL veya geçerli uzaklık için belirtilen boyut UWOP_ALLOC_LARGE oluşturur.<br /><br /> *Boyutu* işlenen 8'in katı olmalıdır.|
|. SAVEREG *kaydetme*, *uzaklığı*|UWOP_SAVE_NONVOL ya da belirtilen ve geçerli prolog sapmasını kullanarak UWOP_SAVE_NONVOL_FAR geriye doğru izleme kod girişini oluşturur. En verimli kodlama MASM seçer.<br /><br /> *uzaklık* pozitif ve 8'in katı olmalıdır. *uzaklık* genellikle RSP içinde olan, yordam çerçevesinin tabanıdır göre veya bir çerçeve işaretçisi ölçeklendirilmemiş çerçeve işaretçisini kullanıyorsanız.|
|.SAVEXMM128 *register*, *offset*|UWOP_SAVE_XMM128 ya da belirtilen XMM kaydı ve geçerli prolog sapmasını kullanarak UWOP_SAVE_XMM128_FAR geriye doğru izleme kod girişini oluşturur. En verimli kodlama MASM seçer.<br /><br /> *uzaklık* pozitif ve 16 katı olmalıdır.  *uzaklık* genellikle RSP içinde olan, yordam çerçevesinin tabanıdır göre veya bir çerçeve işaretçisi ölçeklendirilmemiş çerçeve işaretçisini kullanıyorsanız.|
|. PUSHFRAME \[ *kod*]|UWOP_PUSH_MACHFRAME geriye doğru izleme kodu girişi oluşturur. İsteğe bağlı *kod* belirtilirse, geriye doğru izleme kodu giriş 1 değiştiricisi verilmiştir. Aksi takdirde değiştirici 0'dır.|
|.ENDPROLOG|Giriş bildirimlerinin sonuna işaret eder.  İşlevin ilk 255 bayt cinsinden olmalıdır.|

İşlem, en uygun kullanım ile örnek işlev girişi şu şekildedir:

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
; if we didn’t have a frame pointer, this would be illegal
; if we didn’t make this modification,
; there would be no need for a frame pointer

    sub rsp, 060h

; we can unwind from the next AV because of the frame pointer

    mov rax, 0
    mov rax, [rax] ; AV!

; restore the registers that weren’t saved with a push
; this isn’t part of the official epilog, as described in section 2.5

    movdqa xmm7, [rbp]
    mov rsi, [rbp+018h]
    mov rdi, [rbp-010h]

; Here’s the official epilog

    lea rsp, [rbp-020h]
    pop rbp
    ret
sample ENDP
```

### <a name="masm-macros"></a>MASM Makroları

Kullanımını kolaylaştırmak için [ham sözde işlemler](#raw-pseudo-operations), tipik yordamı öğesinin ve sonuçları oluşturmak için kullanılan ksamd64.inc içinde tanımlı makrolar, bir dizi yoktur.

|Makrosu|Açıklama|
|-|-|
|alloc_stack(n)|Bir yığın çerçevesini n bayt ayırır (kullanarak `sub rsp, n`) ve uygun geriye doğru izleme bilgilerini (.allocstack n)|
|save_reg *reg*, *loc*|Bir kayıt kaydeder *reg* üzerinde RSP yığında uzaklığı *loc*ve uygun geriye doğru izleme bilgilerini. (.savereg reg, loc)|
|push_reg *reg*|Bir kayıt gönderim *reg* yığında ve uygun geriye doğru izleme bilgilerini. (.pushreg reg)|
|rex_push_reg *reg*|2 bayt push kullanarak yığında bir kayıt kaydedin uygun geriye doğru izleme bilgilerini bu kullanılmalıdır anında iletme işlevi anında düzeltme eki eklenebilen olduğundan emin olmak için ilk yönerge işlevindeki ise (.pushreg reg).|
|save_xmm128 *reg*, *loc*|Kalıcı bir XMM kaydı kaydeder *reg* üzerinde RSP yığında uzaklığı *loc*ve uygun geriye doğru izleme bilgilerini (.savexmm128 reg, loc)|
|set_frame *reg*, *uzaklığı*|Çerçeve kaydı ayarlar *reg* rsp için + *uzaklığı* (kullanarak bir `mov`, veya bir `lea`) ve uygun geriye doğru izleme bilgilerini (.set_frame reg, uzaklık)|
|push_eflags|İle eflags gönderim bir `pushfq` yönerge ve bilgilerini (gösterir 8 .alloc_stack) uygun geriye doğru izleme|

Örnek işlevi giriş makroları uygun kullanımıyla birlikte aşağıda verilmiştir:

```MASM
SkFrame struct
    Fill    dq ?; fill to 8 mod 16
    SavedRdi dq ?; saved register RDI
    SavedRsi dq ?; saved register RSI
SkFrame ends

sampleFrame struct
    Filldq?; fill to 8 mod 16
    SavedRdidq?; Saved Register RDI
    SavedRsi  dq?; Saved Register RSI
sampleFrame ends

sample2 PROC FRAME
    alloc_stack(sizeof sampleFrame)
    save_reg rdi, sampleFrame.SavedRdi
    save_reg rsi, sampleFrame.SavedRsi
    .end_prolog

; function body

    mov rsi, sampleFrame.SavedRsi[rsp]
    mov rdi, sampleFrame.SavedRdi[rsp]

; Here’s the official epilog

    add rsp, (sizeof sampleFrame)
    ret
sample2 ENDP
```

## <a name="unwind-data-definitions-in-c"></a>C'de veri tanımlarını geriye doğru izleme

Geriye doğru izlenen veri C açıklaması aşağıda verilmiştir:

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
