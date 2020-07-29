---
title: ARM ABı kurallarına genel bakış
ms.date: 07/11/2018
ms.assetid: 23f4ae8c-3148-4657-8c47-e933a9f387de
ms.openlocfilehash: fc211b887b2b82f533c1e36bf95e6fd6b8e24728
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229772"
---
# <a name="overview-of-arm32-abi-conventions"></a>ARM32 ABı kurallarına genel bakış

ARM işlemcilerde Windows için derlenen kod için uygulama ikili arabirimi (ABı), standart ARM EABI 'yi temel alır. Bu makalede, ARM ve standart için pencereler arasındaki temel farklılıklar vurgulanmıştır. Bu belge ARM32 ABı ' i içerir. ARM64 ABı hakkında daha fazla bilgi için bkz. [ARM64 ABI kurallarına genel bakış](arm64-windows-abi-conventions.md). Standart ARM EABI hakkında daha fazla bilgi için bkz. ARM mimarisi (dış bağlantı) [Için uygulama Ikili arabirimi (ABI)](http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.subset.swdev.abi/index.html) .

## <a name="base-requirements"></a>Temel gereksinimler

ARM 'de Windows, her zaman bir ARMv7 mimarisinde çalıştığını varsayar. VFPv3-D32 veya üzeri biçiminde kayan nokta desteğinin donanımda mevcut olması gerekir. VFP, donanımda hem tek duyarlıklı hem de çift duyarlıklı kayan nokta desteği sağlamalıdır. Windows çalışma zamanı, VNET olmayan donanımda çalışmayı etkinleştirmek için kayan nokta öykünmesini desteklemez.

Gelişmiş SıMD uzantıları (NEON) desteği — hem tamsayı hem de kayan nokta işlemlerini barındırır, ayrıca donanımda de bulunmalıdır. Öykünme için çalışma zamanı desteği sağlanmaz.

Tamsayı bölme desteği (UDIV/SDIV) kesinlikle önerilir, ancak gerekli değildir. Tamsayı bölme desteği olmayan platformlar, bu işlemlerin yakalandığı ve muhtemelen düzeltme eki uygulanmış olması gerektiği için bir performans cezası gerektirebilir.

## <a name="endianness"></a>Endian

ARM 'de Windows, küçük endian modunda yürütülür. Hem MSVC derleyicisinin hem de Windows çalışma zamanının her zaman az endian veri beklemesi. ARM yönerge kümesi mimarisi (ISA) içindeki SETEND yönergesi, Kullanıcı modu kodunun geçerli bitikliği değiştirmesine izin verse de, bir uygulama için tehlikeli olması önerilmez. Büyük endian modunda bir özel durum oluşturulursa, davranış tahmin edilemez ve kullanıcı modunda bir uygulama hatasına veya çekirdek modunda bir hata denetimi oluşmasına neden olabilir.

## <a name="alignment"></a>Hizalama

Windows ARM donanımının hatalı hizalanmış tamsayı erişimlerini saydam olarak işlemesini sağlasa da, bazı durumlarda hizalama hataları yine de oluşturulabilir. Hizalama için bu kuralları izleyin:

- Yarım sözcük boyutlu (16 bit) ve sözcük boyutlu (32-bit) tamsayı yüklemelerinin ve mağazaların hizalı olması gerekmez. Donanım bunları etkili ve şeffaf bir şekilde işler.

- Kayan nokta yükleri ve mağazaları hizalı olmalıdır. Çekirdek, hizalanmamış yükler ve depolar, ancak önemli ek yüklerle saklanır.

- Load veya Store Double (LDRD/STRD) ve çoklu (LDM/STM) işlemleri hizalı olmalıdır. Çekirdek, bunların çoğunu saydam olarak, ancak önemli bir ek yük ile işler.

- Tüm önbelleğe alınmamış bellek erişimleri, tamsayı erişimleri için bile hizalı olmalıdır. Hizalanmamış erişimler bir hizalama hatasına neden olur.

## <a name="instruction-set"></a>Yönerge kümesi

ARM 'de Windows için olan yönerge kümesi, Thumb-2 ile kesinlikle sınırlıdır. Bu platformda yürütülen tüm kodların başlaması beklenir ve her zaman parmak modunda kalır. Eski ARM yönerge kümesine geçme girişimi başarılı olabilir, ancak bunu yaparsanız, oluşan tüm özel durumlar veya kesintiler Kullanıcı modunda bir uygulama hatasına veya çekirdek modunda bir hata denetimi oluşmasına neden olabilir.

Bu gereksinimin yan etkisi, tüm kod işaretçilerinin düşük bit kümesine sahip olması gerekir. Bu, paket olarak BLX veya BX aracılığıyla yüklenip dallandırıldı ve hedef kodu 32-bit ARM yönergeleri olarak yürütmeye çalıştıklarında, işlemcinin parmak izde kalacağından ve

### <a name="it-instructions"></a>BT yönergeleri

Bu özel durumlar dışında, Thumb-2 kodundaki BT yönergelerinin kullanımına izin verilmez:

- BT yönergesi yalnızca bir hedef yönergeyi değiştirmek için kullanılabilir.

- Hedef yönerge 16 bit yönerge olmalıdır.

- Hedef yönerge aşağıdakilerden biri olmalıdır:

   |16 bit OpCodes|Sınıf|Kısıtlamalar|
   |---------------------|-----------|------------------|
   |MOV, MVN|Taşı|RM! = PC, RD! = PC|
   |LDR, LDR [S] B, LDR [S] H|Bellekten yükleme|Ancak LDR değişmez form|
   |STR, STRB, STRH|Belleğe depola||
   |ADD, ADC, RSB, SBC, SUB|Ekle veya çıkart|Değil, ADD/SUB SP, SP, imm7 Forms<br /><br /> RM! = PC, RDN! = PC, RDM! = PC|
   |CMP, CMN|Karşılaştır|RM! = PC, RN! = PC|
   |MUL|Çarp||
   |ASR, LSL, LSR, ROR|Bit kaydırma||
   |VE, BIC, EOR, ORR, TST|Bit düzeyinde aritmetik||
   |BILGISAYARıN|Kaydolmak için dal|RM! = PC|

Geçerli ARMv7 CPU 'Ları izin verilmeyen yönerge formlarının kullanımını bildiremese de, gelecekteki nesiller için bekleniyor. Bu formlar algılanırsa, bunları kullanan herhangi bir program tanımsız yönerge özel durumuyla sonlandırılabilir.

### <a name="sdivudiv-instructions"></a>SDIV/UDIV yönergeleri

Tamsayı bölme yönergelerinin kullanımı SDIV ve UDIV, yerel donanım olmayan platformlarda bile bunları işlemek için tam olarak desteklenir. SDIV veya UDIV başına ek yük, bir Cortex-A9 Processor 'a bölme işlemi, girdilere bağlı olarak 20-250 döngülerinin genel bölme süresine ek olarak yaklaşık 80 döngüdir.

## <a name="integer-registers"></a>Tamsayı Yazmaçları

ARM işlemcisi 16 tamsayı kaydını destekler:

|Kaydettir|Katılımcıdan?|Rol|
|--------------|---------------|----------|
|R0|Katılımcıdan|Parametre, sonuç, karalama kayıt 1|
|R1|Katılımcıdan|Parametre, sonuç, karalama kaydı 2|
|r2'de|Katılımcıdan|Parametre, karalama kaydı 3|
|R3|Katılımcıdan|Parametre, karalama kaydı 4|
|R4|Geçici olmayan||
|r5|Geçici olmayan||
|r6|Geçici olmayan||
|R7|Geçici olmayan||
|R8|Geçici olmayan||
|R9|Geçici olmayan||
|r10|Geçici olmayan||
|r11|Geçici olmayan|Çerçeve işaretçisi|
|r12|Katılımcıdan|Yordam içi çağrı kayıt kaydı|
|R13 (SP)|Geçici olmayan|Yığın işaretçisi|
|R14 (LR)|Geçici olmayan|Bağlantı kaydı|
|R15 (bılgısayar)|Geçici olmayan|Program sayacı|

Parametresinin ve dönüş değeri yazmaçlarının nasıl kullanılacağına ilişkin ayrıntılar için, bu makaledeki parametre geçirme bölümüne bakın.

Windows, yığın çerçevesinin hızlı yürümesi için r11 kullanır. Daha fazla bilgi için yığın yürüme bölümüne bakın. Bu gereksinim nedeniyle, R11 her zaman zincirdeki en üstteki bağlantıya işaret etmelidir. Genel amaçlar için R11 kullanmayın — kodunuz, analiz sırasında doğru yığın hakkında bir adım oluşturmaz.

## <a name="vfp-registers"></a>VFP Yazmaçları

Windows yalnızca VFPv3-D32 Eşişlemcisi desteği olan ARM türevlerini destekler. Bu, kayan nokta yazmaçlarının her zaman mevcut olduğu ve parametre geçirme için tam olarak 32 kayıt kümesinin kullanılabilir olduğu anlamına gelir. VFP kayıtları ve kullanımları bu tabloda özetlenmiştir:

|Tekler|Double değerleri|Quads|Katılımcıdan?|Rol|
|-------------|-------------|-----------|---------------|----------|
|S0-S3|D0-D1|q0|Katılımcıdan|Parametreler, sonuç, karalama kaydı|
|S4-S7|D2-D3|Q1|Katılımcıdan|Parametreler, karalama kaydı|
|S8-S11|D4-D5|üç|Katılımcıdan|Parametreler, karalama kaydı|
|S12-S15|d6-d7|S3|Katılımcıdan|Parametreler, karalama kaydı|
|s16-s19|D8-D9|ç|Geçici olmayan||
|s20-s23|D10-D11|q5|Geçici olmayan||
|s24-s27|D12-D13|q6|Geçici olmayan||
|s28-s31|D14-D15|q7|Geçici olmayan||
||D16-d31|S8-q15|Katılımcıdan||

Sonraki tabloda kayan nokta durum ve denetim yazmacı (FPSCR) Bitfields gösterilmektedir:

|Bits|Anlamı|Katılımcıdan?|Rol|
|----------|-------------|---------------|----------|
|31-28|NZCV|Katılımcıdan|Durum bayrakları|
|27|QC|Katılımcıdan|Kümülatif doygunluk|
|26|AHP|Geçici olmayan|Alternatif yarı duyarlık denetimi|
|25|DEĞERI|Geçici olmayan|Varsayılan NaN mod denetimi|
|24|FZ|Geçici olmayan|Sıfıra yasla mod denetimi|
|23-22|RMode|Geçici olmayan|Yuvarlama modu denetimi|
|21-20|Adım|Geçici olmayan|Vektör Ilerlemesiyle her zaman 0 olmalıdır|
|18-16|Len|Geçici olmayan|Vektör uzunluğu her zaman 0 olmalıdır|
|15, 12-8|IDE, ıXE, vb.|Geçici olmayan|Özel durum yakalama bitlerini etkinleştir, her zaman 0 olmalıdır|
|7, 4-0|IDC, IXC, vb.|Katılımcıdan|Birikmeli özel durum bayrakları|

## <a name="floating-point-exceptions"></a>Kayan nokta özel durumları

Çoğu ARM donanımı IEEE kayan nokta özel durumlarını desteklemez. Donanım kayan nokta özel durumları olan işlemci çeşitleri üzerinde, Windows çekirdeği özel durumları sessizce yakalar ve bunları FPSCR kaydındaki örtük olarak devre dışı bırakır. Bu, işlemci çeşitleri arasında normalleştirilmiş davranışı sağlar. Aksi takdirde, özel durum desteği olmayan bir platformda geliştirilen kod, özel durum desteği olan bir platformda çalışırken beklenmedik özel durumlar alabilir.

## <a name="parameter-passing"></a>Parametre geçirme

Bağımsız değişken olmayan bağımsız işlevlerde Windows ARM ABı, parametre geçirme için ARM kurallarını izler; bu, VFP ve Advanced SıMD uzantılarını içerir. Bu kurallar, VFP uzantılarıyla birleştirilmiş [ARM mimarisine yönelik yordam çağrısı standardını](http://infocenter.arm.com/help/topic/com.arm.doc.ihi0042c/IHI0042C_aapcs.pdf)izler. Varsayılan olarak, ilk dört tamsayı bağımsız değişkeni ve en fazla sekiz kayan nokta veya vektör bağımsız değişkeni yazmaçlara geçirilir ve ek bağımsız değişkenler yığına geçirilir. Bağımsız değişkenler, bu yordamı kullanarak kayıt veya yığına atanır:

### <a name="stage-a-initialization"></a>Aşama A: başlatma

Başlatma, bağımsız değişken işleme başlamadan önce tam olarak bir kez gerçekleştirilir:

1. Sonraki çekirdek kayıt numarası (NCRN), R0 olarak ayarlanmıştır.

1. VFP kayıtları ayrılmamış olarak işaretlenir.

1. Sonraki yığılmış bağımsız değişken adresi (NSAA) geçerli SP olarak ayarlanır.

1. Bellekte bir sonuç döndüren bir işlev çağrılırsa, sonucun adresi R0 içine yerleştirilir ve NCRN, R1 olarak ayarlanır.

### <a name="stage-b-pre-padding-and-extension-of-arguments"></a>Aşama B: bağımsız değişkenlerin ön doldurma ve uzantısı

Listedeki her bağımsız değişken için, aşağıdaki listeden ilk eşleşen kural uygulanır:

1. Bağımsız değişken, boyutu hem çağıran hem de aranan tarafından statik olarak belirlenemediği bir bileşik türdür, bağımsız değişken belleğe kopyalanır ve kopyaya bir işaretçi ile değiştirilmiştir.

1. Bağımsız değişken bir bayt veya 16 bit yarım sözcüktür ise, sıfır genişletilmiş veya imza, 32 bitlik bir tam sözcüğe kaydedilir ve 4 baytlık bir bağımsız değişken olarak kabul edilir.

1. Bağımsız değişken bileşik bir tür ise, boyutu 4 ' ün en yakın katına yuvarlanır.

### <a name="stage-c-assignment-of-arguments-to-registers-and-stack"></a>C aşaması: kayıt ve yığın için bağımsız değişkenlerin atanması

Listedeki her bağımsız değişken için, bağımsız değişken ayrılana kadar sırasıyla aşağıdaki kurallar uygulanır:

1. Bağımsız değişken bir VFP türüdür ve uygun türe ait yeterince ardışık ayrılmamış VFP kayıtları varsa, bağımsız değişken bu tür yazmaçların en düşük sayılı dizisine ayrılır.

1. Bağımsız değişken bir VFP türü ise, kalan tüm ayrılmamış Yazmaçları kullanılamaz olarak işaretlenir. Bağımsız değişken türü için doğru hizalanana ve bağımsız değişken ayarlanan NSAA 'da yığına kopyalandığı sürece NSAA, yukarı doğru ayarlanır. NSAA, daha sonra bağımsız değişkenin boyutuyla artırılır.

1. Bağımsız değişken 8 baytlık hizalama gerektiriyorsa, NCRN, sonraki çift kayıt numarasına yuvarlanır.

1. 32 bitlik sözcüklerin bağımsız değişkeninin boyutu R4 eksi NCRN 'den daha fazla değilse, bağımsız değişken, NCRN 'den başlayarak, düşük sayılı kayıtları kaplayan en az önemli bitlerle birlikte, ana kayıtlara kopyalanır. NCRN, kullanılan kayıt sayısına göre artırılır.

1. NCRN, R4 'den küçükse ve NSAA, SP 'ye eşitse, bağımsız değişken çekirdek Yazmaçları ve yığın arasında bölünür. Bağımsız değişkenin ilk bölümü, NCRN 'den başlayarak R3 dahil olmak üzere temel kayıtlara kopyalanır. Bağımsız değişkenin geri kalanı, NSAA 'dan başlayarak yığına kopyalanır. NCRN, R4 olarak ayarlanır ve NSAA bağımsız değişkeninin boyutu tarafından, Yazmaçlarda geçirilen miktar çıkarılarak artırılır.

1. Bağımsız değişken 8 baytlık hizalama gerektiriyorsa, NSAA sonraki 8 baytlık hizalanmış adrese yuvarlanır.

1. Bağımsız değişkeni NSAA 'da belleğe kopyalanır. NSAA, bağımsız değişkenin boyutuyla artırılır.

VFP kayıtları, değişen sayıda bağımsız değişken işlevleri için kullanılmaz ve 1 ve 2. aşama yok sayılır. Bu, değişen sayıda bağımsız değişken, çağıran tarafından geçirilen diğer bağımsız değişkenlere kayıt bağımsız değişkenlerini eklemek için isteğe bağlı bir push {R0-R3} ile başlayabileceği anlamına gelir ve sonra bağımsız değişken listesinin tamamına doğrudan yığından erişebilirsiniz.

Tamsayı türü değerleri r0 içinde döndürülür ve isteğe bağlı olarak 64 bitlik dönüş değerleri için R1 olarak genişletilir. VFP/NEON kayan nokta veya SIMD türü değerleri, uygun şekilde S0, D0 veya Q0 içinde döndürülür.

## <a name="stack"></a>Yığın

Yığın her zaman 4 baytlık hizalı olmalıdır ve herhangi bir işlev sınırında 8 baytlık hizalı olmalıdır. Bu, 64 bitlik yığın değişkenlerinde birbirine kenetlenmiş işlemlerin sık kullanımını desteklemek için gereklidir. ARM EABI, yığının herhangi bir genel arabirimde 8 bayt hizalı olduğunu belirtir. Tutarlılık için ARM ABı, tüm işlev sınırlarını bir ortak arabirim olacak şekilde değerlendirir.

Bir çerçeve işaretçisi kullanmak zorunda olan işlevler — Örneğin, `alloca` yığın işaretçisini dinamik olarak değiştiren ya da değiştiren işlevler), R11 içinde çerçeve işaretçisini, bir OG işlevi içinde ayarlaması ve epıg 'ye kadar değişmeden bırakmalıdır. Çerçeve işaretçisi gerektirmeyen işlevler, prolog 'daki tüm yığın güncelleştirmelerini gerçekleştirmelidir ve yığın işaretçisini epıg 'ye kadar değişmeden bırakır.

Yığın üzerinde 4 KB veya daha fazla alan işlevleri, son sayfadan önceki her sayfanın sırayla dokunulmamasını sağlamalıdır. Bu, hiçbir kodun, Windows 'un yığını genişletmek için kullandığı koruma sayfalarını "artık" kullanmasını sağlar. Genellikle, bu, `__chkstk` toplam yığın ayırmayı R4 içinde 4 ' te bölünen ve son yığın ayırma miktarını R4 ' de geri döndüren yardımcı tarafından yapılır.

### <a name="red-zone"></a>Kırmızı bölge

Geçerli yığın işaretçisinin hemen altındaki 8 baytlık alan, analiz ve dinamik düzeltme eki uygulama için ayrılmıştır. Bu, [SP, #-8] konumunda 2 kayıt depolayan ve bunları geçici olarak rastgele amaçlar için kullanan dikkatle oluşturulmuş kodun eklenmesine izin verir. Windows çekirdeği, hem kullanıcı modunda hem de çekirdek modunda bir özel durum veya kesme gerçekleşirse, bu 8 baytın üzerine yazılmayacak olmasını garanti eder.

### <a name="kernel-stack"></a>Çekirdek yığını

Windows 'daki varsayılan çekirdek modu yığını üç sayfalardır (12 KB). Çekirdek modunda büyük yığın arabellekleri olan işlevler oluşturmamaya dikkat edin. Kesme, çok az yığın olan bir alan ile gelebilir ve yığın panik hata denetimi hatasına neden olabilir.

## <a name="cc-specifics"></a>C/C++ özellikleri

Numaralandırmadaki en az bir değer 64-bit çift sözcüklü depolama alanı gerektirmediği için numaralandırmalar 32 bitlik tamsayı türleridir. Bu durumda, numaralandırma 64 bitlik bir tamsayı türüne yükseltilir.

**`wchar_t`****`unsigned short`**, diğer platformlarla uyumluluğu korumak için ile eşdeğer olacak şekilde tanımlanır.

## <a name="stack-walking"></a>Yığın yürüme

Windows kodu, hızlı yığın yürümesini etkinleştirmek için çerçeve işaretçileri etkinleştirilmiş ([/oy (çerçeve Işaretçisi atlama)](reference/oy-frame-pointer-omission.md)) ile derlenir. Genellikle, R11 kaydı zincirde bir sonraki bağlantıyı işaret eder; bu, yığındaki önceki çerçeveye yönelik işaretçiyi belirten bir {R11, LR} çiftidir ve dönüş adresidir. Kodunuzun, geliştirilmiş profil oluşturma ve izleme için çerçeve işaretçilerini de etkinleştirmenizi öneririz.

## <a name="exception-unwinding"></a>Özel durum geri sarma

Özel durum işleme sırasında yığın geri sarma, geriye doğru izleme kodları kullanılarak etkinleştirilir. Geriye doğru izleme kodları, yürütülebilir görüntünün. xdata bölümünde depolanan baytların bir dizisidir. Bu, işlev için işlem ve epıg kodunun bir soyut bir şekilde tanıtılmasını sağlar, böylece bir işlevin prolog 'nin etkileri, çağıranın yığın çerçevesinin geri sarılığının hazırlanmasında hazırlanmaya devam edebilir.

ARM EABI, geriye doğru izleme kodları kullanan bir özel durum izleme modeli belirtir. Bununla birlikte, bu belirtim Windows 'da geriye doğru izleme için yeterli değildir; bu, işlemcinin bir işlevin işlem veya başlangıç sayısının ortasında olduğu durumları ele almalıdır. ARM özel durum verilerinde Windows ve geri sarma hakkında daha fazla bilgi için bkz. [ARM özel durum işleme](arm-exception-handling.md).

`RtlAddFunctionTable`Oluşturulan kodun özel durum işleme katılmasını sağlamak için, ve ilişkili işlevlere yapılan çağrılarında belirtilen dinamik işlev tabloları kullanılarak, dinamik olarak üretilen kodun açıklanmasını öneririz.

## <a name="cycle-counter"></a>Bisiklet sayacı

Windows çalıştıran ARM işlemcileri bir bisiklet sayacını desteklemek için gereklidir, ancak sayacı doğrudan kullanmak sorunlara neden olabilir. Bu sorunlardan kaçınmak için ARM 'de Windows, normalleştirilmiş bir 64 bit kullanım sayacı değeri istemek için tanımsız bir Opcode kullanır. C veya C++ ' dan, `__rdpmccntr64` uygun Opcode 'ı oluşturmak için iç öğesini kullanın; derlemeden `__rdpmccntr64` yönergesini kullanın. Döngü sayacını okumak Cortex-A9 üzerinde yaklaşık 60 döngü sürer.

Sayaç, saat değil, doğru bir geçiş sayacıdır; Bu nedenle, sayım sıklığı işlemci sıklığıyla farklılık gösterir. Geçen saat süresini ölçmek istiyorsanız kullanın `QueryPerformanceCounter` .

## <a name="see-also"></a>Ayrıca bkz.

[Genel Visual C++ ARM Geçiş Sorunları](common-visual-cpp-arm-migration-issues.md)<br/>
[ARM özel durum Işleme](arm-exception-handling.md)
