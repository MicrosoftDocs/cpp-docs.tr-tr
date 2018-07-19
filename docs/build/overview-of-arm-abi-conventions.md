---
title: ARM ABI kurallarına genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 23f4ae8c-3148-4657-8c47-e933a9f387de
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e5ee2ddc29c2a014aceb8ac6356cae9e42a916d
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027329"
---
# <a name="overview-of-arm32-abi-conventions"></a>ARM32 ABI kurallarına genel bakış

Windows için ARM işlemciler üzerinde derlenmiş kod için uygulama ikili arabiriminde (ABI) üzerinde standart ARM EABI temel alır. Bu makalede Windows ARM temel ve standart arasındaki farklar vurgulanmaktadır. Bu belge ARM32 ABI kapsar. ARM64 ABI hakkında daha fazla bilgi için bkz. [ARM64 genel bakış ABI kurallarına](arm64-windows-abi-conventions.md). Standart ARM EABI hakkında daha fazla bilgi için bkz: [uygulama ikili arabirimi (ABI) ARM mimarisi için](http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.subset.swdev.abi/index.html) (dış bağlantı).

## <a name="base-requirements"></a>Temel gereksinimleri

ARM üzerinde Windows her zaman bir ARMv7 mimari üzerinde çalıştığından emin varsayılır. Kayan nokta desteği VFPv3 D32 veya sonraki sürümüne yükseltilmesi biçiminde donanımda bulunması gerekir. VFP hem tek duyarlık hem çift duyarlıklı donanım kayan nokta desteklemesi gerekir. Windows çalışma zamanı VFP olmayan donanım üzerinde çalışmasını sağlamak için kayan nokta öykünmesini desteklemez.

Gelişmiş SIMD Uzantıları (NEON) desteği — bu, hem tamsayı ve kayan nokta işlemleri içerir — donanımında bulunmalıdır. Öykünme için hiçbir çalışma zamanı desteği sağlanır.

Tamsayı bölme desteği (UDIV/SDIV) önerilir ancak gerekli değildir. Yakalanan ve büyük olasılıkla yama bu işlemler olduğundan tamsayı bölme desteği eksik platformları bir performans cezasına sebep.

## <a name="endianness"></a>Endianness

ARM üzerinde Windows endian modunda yürütülür. Visual C++ derleyicisi hem de Windows çalışma zamanı endian verileri her zaman bekler. ARM yönerge SETEND yönergesinde ayarlayın ancak geçerli endianness değiştirmek için bile kullanıcı modu kod mimari (ISA) sayesinde, bunun yapılması, bir uygulama için tehlikeli olduğundan bu nedenle önerilmez. Bir özel durum ise büyük endian modunda oluşturulan davranışı tahmin edilemez ve bir uygulama hatası kullanıcı modunda veya çekirdek modunda hata denetimi neden olabilir.

## <a name="alignment"></a>Hizalama

Yanlış hizalanmış tamsayı işlemek ARM donanım Windows sağlar, ancak hataları yine de bazı durumlarda oluşturulan hizalama saydam bir şekilde erişir. Hizalama için bu kuralları izleyin:

- Yarı-word boyutlu (16-bit) (32-bit) tamsayı word boyutlu yükler ve depoları hizalı gerekmez. Donanım bunları etkili ve şeffaf bir şekilde işler.

- Kayan nokta yükler ve depoları hizalanmalıdır. Çekirdek hizalanmamış yükü işler ve şeffaf bir şekilde, ancak önemli ölçüde depolar.

- Yükleme veya double (LDRD/STRD) depolamak ve birden çok (LDM/STM) işlem hizalanmalıdır. Çekirdek çoğu şeffaf bir şekilde, ancak önemli ölçüde işler.

- Hatta tamsayı erişim için tüm önbelleğe alınmamış bellek erişimlerinin hizalanmalıdır. Hizalanmamış erişimler bir hizalama hatasına neden olur.

## <a name="instruction-set"></a>Yönerge kümesi

ARM üzerinde Windows için yönerge Thumb-2'ye kesinlikle sınırlıdır. Bu platform üzerinde çalıştırılan tüm koda başlatın ve her zaman Thumb modunda kalması beklenir. Eski ARM yönerge kümesine geçiş girişimi başarısız olabilir, ancak varsa, tüm özel durumlar veya ortaya çıkan kesintileri kullanıcı modunda bir uygulama hatası veya çekirdek modunda hata denetimi neden olabilir.

Bu gereksinim, yan etkisi, tüm kod işaretçileri düşük bit kümesi sahip olmasıdır. Bu, böylelikle yüklendi ve BLX veya BX aracılığıyla dallandırılmış işlemci Thumb modunda kalır ve hedef kodu 32 bit ARM yönergeleri yürütmek denememelidir.

### <a name="it-instructions"></a>BT yönergeleri

Thumb-2 kodda BT yönergelerinin kullanımını etkinleştir, bu özel durumlar dışında izin verilmez:

- BT yönergesi yalnızca tek bir hedef yönerge değiştirmek için kullanılabilir.

- Hedef yönerge 16-bit yönerge olmalıdır.

- Hedef yönerge bunlardan biri olmalıdır:

   |16-bit işlem kodları|örneği|Kısıtlamalar|
    |---------------------|-----------|------------------|
    |MOV, MVN|Taşıma|RM! bilgisayarı, Rd =! = PC|
    |LDR LDR [S] B, LDR [S] H|Bellekten yükleme|Ancak LDR değişmez değer formlar|
    |STR, STRB, STRH|Bellek Store||
    |ADC, RSB, SBC, ALT EKLEYİN|Eklemek veya çıkartmak|Ancak değil Ekle/SUB SP, SP, imm7 formlar<br /><br /> RM! = PC, Rdn! = PC, Rdm! = PC|
    |CMP, CMN|{1&gt;Karşılaştır&lt;1}|RM! = PC, Rn! = PC|
    |MUL|Çarp||
    |ASR, LSL, LSR, ROR|Bit kaydırma||
    |AYRICA, BIC, EOR, ORR TST|Bit düzeyinde aritmetik||
    |BX|Dal kaydetmek için|RM! = PC|

Geçerli ARMv7 CPU kullanımı izin verilmeyen bir yönerge formları raporlayamaz olsa da, gelecek nesil beklenir. Bu formlar algılanmazsa, bunları kullanan herhangi bir programı tanımlanmamış yönerge özel durumla sona erdirilecek.

### <a name="sdivudiv-instructions"></a>SDIV/UDIV yönergeleri

Tamsayı kullanımını SDIV ve UDIV tam olarak desteklenir, hatta bunları işlemek için yerel donanım olmadan platformlarda yönergeleri bölün. Cortex-A9 işlemci SDIV veya UDIV sıfırla bölme başına yükü girişleri bağlı olarak 20-250 çevrimi genel bölme zaman ek olarak yaklaşık 80 döngüleri var.

## <a name="integer-registers"></a>Tamsayı kaydeder

ARM işlemci 16 tamsayı kayıtları destekler:

|Yazmaç|Geçici?|Rol|
|--------------|---------------|----------|
|r0|Volatile|Parametresi, sonuç, karalama kayıt 1|
|R1|Volatile|Parametresi, sonuç, karalama kaydı 2|
|R2|Volatile|Parametresi, karalama kayıt 3|
|R3|Volatile|Parametresi, karalama kayıt 4|
|R4|Geçici olmayan||
|R5|Geçici olmayan||
|r6|Geçici olmayan||
|R7|Geçici olmayan||
|R8|Geçici olmayan||
|R9|Geçici olmayan||
|R10|Geçici olmayan||
|R11|Geçici olmayan|Çerçeve işaretçisi|
|R12|Volatile|İçi yordam çağrısı karalama Kaydet|
|R13 (SP)|Geçici olmayan|Yığın işaretçisi|
|R14 (LR)|Geçici olmayan|Bağlantı Kaydet|
|R15 kayıtları (PC)|Geçici olmayan|Program sayacının|

Parametresini kullanın ve değerini kayıtları döndürmek için bu makalede bir parametre geçirerek bölümüne bakın hakkında daha fazla ayrıntı için.

Windows hızlı-yürüyen için yığın çerçevesinin r11 kullanır. Daha fazla bilgi için yığın Walking bölümüne bakın. Bu gereksinimden dolayı her zaman zincirindeki en üstteki bağlantısına r11 göstermelidir. R11 genel amaçlar için kullanmayın; kod analizi sırasında doğru yığın Yürüyüşü oluşturmaz.

## <a name="vfp-registers"></a>VFP kaydeder

Windows Destek VFPv3 D32 eşişlemcisi olan ARM çeşitleri yalnızca destekler. Bunun anlamı, kayan nokta kayıtlarını her zaman mevcut olduğundan ve parametre geçirme için yararlandı ve tam 32 kayıtları ayarlamak için kullanılabilir. VFP kaydeder ve bu tablodaki kullanımları özetlenir:

|Tekler|Double değerleri|Quads|Geçici?|Rol|
|-------------|-------------|-----------|---------------|----------|
|S0-s3|D0 d1|q0|Volatile|Kayıt parametreleri, sonuç karalama|
|s7 S4|d3 D2|S1|Volatile|Parametreler, karalama kaydetme|
|S8 s11|D4 d5|S2|Volatile|Parametreler, karalama kaydetme|
|s12 s15|D6 D7 hücresini|q3|Volatile|Parametreler, karalama kaydetme|
|S16 s19|D8 d9|S4|Geçici olmayan||
|S20 s23|D10 d11|S5|Geçici olmayan||
|s24 s27|d12 d13|S6|Geçici olmayan||
|s28 s31|d15 D14|S7|Geçici olmayan||
||d16 d31|S8 S15|Volatile||

Sonraki tabloda kayan nokta durumunu gösterir ve denetim (FPSCR) bit alanları kaydedin:

|Bits|Açıklama|Geçici?|Rol|
|----------|-------------|---------------|----------|
|31-28|NZCV|Volatile|Durumu bayrakları|
|27|QC|Volatile|Toplu doygunluğu|
|26|AHP|Geçici olmayan|Alternatif yarı duyarlık denetimi|
|25|DN|Geçici olmayan|Varsayılan NaN modu denetimi|
|24|FZ|Geçici olmayan|Sıfır için temizleme modunu denetimi|
|23-22|RMode|Geçici olmayan|Yuvarlama modu denetimi|
|21-20|STRIDE|Geçici olmayan|STRIDE vektör, her zaman 0 olmalıdır|
|18-16|Len|Geçici olmayan|Vektör uzunluğu, her zaman 0 olmalıdır|
|15, 12-8|IDE, IXE, vb.|Geçici olmayan|Özel durum etkinleştir BITS tuzak, her zaman 0 olmalıdır|
|7, 4-0|IDC, IXC, vb.|Volatile|Toplam özel durum bayrakları|

## <a name="floating-point-exceptions"></a>Kayan nokta özel durumları

Çoğu ARM donanım IEEE kayan nokta özel durumlarını desteklemiyor. Windows çekirdek donanım kayan nokta özel durumları olan işlemci çeşitleri sessizce özel durumlarını yakalayan ve örtük olarak bunları FPSCR yazmacına devre dışı bırakır. Bu, işlemci çeşitler arasında normalleştirilmiş davranış sağlar. Aksi takdirde, özel durum desteği olmayan bir platform üzerinde geliştirilen kod özel durum desteği olan bir platform üzerinde çalışırken beklenmeyen bir özel durum alabilir.

## <a name="parameter-passing"></a>Parametre geçirme

Variadic olmayan işlevler için ARM ABI üzerinde Windows ARM parametre geçirme için kurallara — bu VFP ve Gelişmiş SIMD uzantıları içerir. Bu kuralları izleyin [ARM mimarisi için yordam çağrısı standart](http://infocenter.arm.com/help/topic/com.arm.doc.ihi0042c/IHI0042C_aapcs.pdf)VFP uzantısı olan birleştirilmiş. Göre varsayılan, ilk dört tamsayı bağımsız değişken ve sekiz kayan nokta veya vektör bağımsız değişkenleri yazmaçlara geçirilir ve ek bağımsız değişkenler yığına geçirilir. Bağımsız değişkenler kayıtları veya yığın için bu yordamı kullanarak atanır:

### <a name="stage-a-initialization"></a>Y: başlatma aşaması

Bağımsız değişken işleme başlamadan önce başlatılması tam bir kez gerçekleştirilir:

1. Sonraki çekirdek kayıt numarası (NCRN) r0 için ayarlanır.

2. VFP kayıtları işaretlenmiş şekilde ayrılmamış.

3. Sonraki yığın bağımsız değişken adresini (NSAA) Geçerli SP. ayarlanır

4. Bellekte bir sonuç döndüren bir işlev çağrılırsa r0 sonucu adresini yerleştirilir ve NCRN r1 için ayarlanır.

### <a name="stage-b-pre-padding-and-extension-of-arguments"></a>Aşama B: öncesi doldurma ve bağımsız değişkenlerin uzantısı

Listedeki her bağımsız değişken için aşağıdaki listeden eşleşen ilk kural uygulanır:

1. Bağımsız değişken boyutu, statik olarak çağıran ve çağrılan tarafından belirlenemiyor bileşik bir tür ise, bağımsız değişken belleğe kopyalanır ve kopya işaretçisi tarafından değiştirildi.

2. Bağımsız değişken bir bayt veya yarı 16 bit sözcük ise sıfır genişletilmiş veya işaret genişletilmiş 32 bit tam sözcük ve bir 4 baytlık bağımsız değişken olarak kabul edilir.

3. Bağımsız değişken türünün ise, boyutu 4'ün en yakın katına yuvarlanır.

### <a name="stage-c-assignment-of-arguments-to-registers-and-stack"></a>Aşama C: atama kaydeder ve yığın bağımsız değişken

Bağımsız değişken ayrılan kadar listedeki her bağımsız değişken için aşağıdaki kurallar sırayla uygulanır:

1. Bağımsız değişken bir VFP türüdür ve ardışık yeterli ayrılmamış VFP yazmaç uygun türde varsa, bağımsız değişkeni böyle yazmaçların en düşük numaralı sıralı tahsis edilir.

2. Bağımsız değişken VFP türü ise, tüm kalan ayrılmamış kasalar kullanılamaz olarak işaretlenir. NSAA yukarı doğru bağımsız değişken türü hizalanır ve bağımsız değişken için ayarlanan NSAA yığınına kopyalanır kadar ayarlanır. NSAA ardından bağımsız değişken boyutuna göre artırılır.

3. Bağımsız değişken 8 baytlık hizalama gerektirir, NCRN sonraki bile kaydı sayıya yuvarlanır.

4. 32-bit sözcüklerin bağımsız değişkenin boyutu r4 NCRN eksi fazlasını değilse, bağımsız değişken NCRN düşük numaralı kayıtları kaplayan en az önemli bitlerin ile başlangıç çekirdek kaydeder kopyalanır. NCRN kullanılan kayıtları sayısına göre artırılır.

5. NCRN r4 küçüktür ve NSAA SP için eşit ise, bağımsız değişken temel kayıtlara ve yığını arasında bölünür. Bağımsız değişkenin ilk bölümü NCRN en fazla başlangıç ve r3 dahil olmak üzere temel kaydeder kopyalanır. Kalan bağımsız değişkenin NSAA başlayan yığına kopyalanır. NCRN r4 için ayarlanır ve NSAA eksi tutarı kayıtlara geçirilen bağımsız değişken boyutuna göre artırılır.

6. Bağımsız değişken 8 baytlık hizalama gerektirir, sonraki 8 bayt hizalı adresi NSAA yuvarlanır.

7. Bağımsız değişken NSAA sırasında belleğe kopyalanır. Bağımsız değişken boyutuna NSAA artırılır.

VFP kasalar, değişen sayıda bağımsız değişken işlevleri için kullanılmaz ve 1. ve 2 aşama C kurallarını göz ardı edilir. Bu, bir bağımsız değişken içeren işlev kayıt bağımsız değişkenleri çağıran tarafından geçirilen ek bağımsız değişkenler için önüne eklediğinizden isteğe bağlı bir itme {r0-r3} ile başlayan ve ardından tüm bağımsız değişken listesi doğrudan yığından erişim anlamına gelir.

İsteğe bağlı olarak, 64-bit dönüş değerleri için r1 için genişletilmiş r0, tamsayı türü değerleri döndürülür. S0, d0 veya q0, uygun şekilde VFP/NEON kayan nokta veya SIMD türü değerleri döndürülür.

## <a name="stack"></a>Yığın

Yığın her zaman hizalı 4 baytlık kalmalı ve 8 baytlık herhangi bir işlev sınırında hizalı olmalıdır. Bu, 64-bit yığın değişkenleri birbirine kenetlenmiş işlemler sık kullanımını desteklemek için gereklidir. ARM EABI yığının ortak bir arabirim 8 baytlık hizalandığını belirtir. Tutarlılık sağlamak için ARM ABI üzerinde Windows ortak arabiriminin olması için hiçbir işlev sınırı göz önünde bulundurur.

Çerçeve işaretçisini kullanmak zorunda işlevleri — Örneğin, bu çağrı işlevleri `alloca` veya dinamik olarak ve yığın işaretçisi değiştirmek — r11 işlevi prolog ve epilog kadar değiştirmeden bırakın, çerçeve işaretçisini ayarlamanız gerekir. Çerçeve işaretçisini gerektirmeyen işlevleri, prolog tüm yığın güncelleştirmeleri gerçekleştirmek ve yığın işaretçisi kadar kapanış değiştirmeden bırakın.

4 KB veya daha fazla yığınındaki ayırma işlevleri her sayfanın son sayfa önce sırayla dokunulan emin olmanız gerekir. Bu kod yok "üzerinden yığın genişletmek için Windows kullanan koruyucu sayfa leap," sağlar. Genelde bu yapılır `__chkstk` Yardımcısı, hangi geçirilen toplam yığın ayırma 4'te r4 tarafından ayrılmış olan bayt ve geri r4 bayt son yığın ayırma miktarını döndürür.

### <a name="red-zone"></a>Kırmızı bölge

Geçerli yığın işaretçisi hemen altındaki 8 baytlık alan, analiz ve dinamik olarak düzeltme eki uygulama için ayrılmıştır. Bu 2 kasalarda depolayan eklenecek, dikkatli bir şekilde oluşturulan kod verir [sp, # 8] ve geçici olarak bunları rastgele amaçlar için kullanır. Windows çekirdek hem kullanıcı modu hem de çekirdek modu bir özel durum veya kesinti oluşursa,'ın bu 8 bayt yazılmaz garanti eder.

### <a name="kernel-stack"></a>Çekirdek yığını

Windows varsayılan çekirdek modu yığında üç sayfası (12 KB) olur. Büyük yığın arabelleği çekirdek modunda olan işlevler oluşturma konusunda dikkatli olun. Kesme, çok az yığın payı oturum gelir ve bir yığın Panik hata denetimi neden.

## <a name="cc-specifics"></a>C/C++ özellikleri

Listedeki en az bir değer 64-bit çift sözcük depolama gerektirmedikçe numaralandırmalar 32-bit tamsayı türleridir. Bu durumda, sabit bir 64-bit tamsayı türüne yükseltilir.

`wchar_t` eşdeğer olarak tanımlanır `unsigned short`, diğer platformlar ile uyumluluğu korumak için.

## <a name="stack-walking"></a>Yığın

Windows kod etkin çerçeve işaretçilerini ile derlenmiş ([/Oy (Çerçeve işaretçisini atlama)](../build/reference/oy-frame-pointer-omission.md)) hızlı yığın walking etkinleştirmek için. Genellikle, r11 kaydetme sonraki bağlantı noktalarını zincirini bir {r11, lr} önceki çerçeve işaretçisi yığını ve dönüş adresi belirtir çifti. Kodunuzu çerçeve işaretçilerini profil oluşturma ve izleme geliştirilmiş ayrıca etkinleştirmenizi öneririz.

## <a name="exception-unwinding"></a>Özel durumu geriye doğru izleme

Sırasında özel durum işleme geriye doğru izleme yığın geriye doğru izleme kodları kullandığı etkinleştirilir. Geriye doğru izleme kodları şunlardır: yürütülebilir resmin sanal işlem bulunur bölümde depolanan bayt dizisi. Arayanın yığın çerçevesi için geriye doğru izleme hazırlanırken bir işlevin prolog etkilerini alınabilir, soyut bir şekilde işlev prolog ve Epilog kodu işlemi açıklanmaktadır.

ARM EABI kullanan bir özel durumu geriye doğru izleme modeli geriye doğru izleme kodları belirtir. Ancak, bu belirtimi, işlemci işlevinin epilog ve prolog ortasında olduğu durumlarda işlemelidir Windows, geriye doğru izleme için yeterli değil. ARM özel durum verileri ve geriye doğru izleme Windows hakkında daha fazla bilgi için bkz [ARM özel durum işleme](../build/arm-exception-handling.md).

Dinamik olarak üretilen kod yapılan çağrıda belirtilen dinamik işlevi tablolar'ı kullanarak açıklanan öneririz `RtlAddFunctionTable` ve İşlevler, oluşturulan kod içinde özel durum işleme katılabilmesi ilişkili.

## <a name="cycle-counter"></a>Döngü sayacı

ARM işlemcileri Windows çalıştıran bir döngü sayacı desteklemek için gerekli olan, ancak sayaç doğrudan kullanılması sorunlara neden olabilir. Bu sorunlardan kaçınmak için bir normalleştirilmiş 64-bit döngü sayacı değerine istemek için tanımlanmamış bir işlem kodu Windows ARM üzerinde kullanır. C veya C++, kullanın `__rdpmccntr64` iç için uygun opcode gösterin; bütünleştirilmiş koddan kullanın `__rdpmccntr64` yönergesi. Döngü sayacı okuma yaklaşık 60 cycles Cortex-A9 alır.

Bir saat gibi doğru döngü sayacı sayacıdır; Bu nedenle, sayım sıklığı işlemci Frequency değeri ile değiştirir. Geçen saatin ölçmek istediğiniz kullanırsanız `QueryPerformanceCounter`.

## <a name="see-also"></a>Ayrıca bkz.

[Genel Visual C++ ARM Geçiş Sorunları](../build/common-visual-cpp-arm-migration-issues.md)  
[ARM Özel Durum İşleme](../build/arm-exception-handling.md)  
