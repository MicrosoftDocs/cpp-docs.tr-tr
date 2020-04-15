---
title: ARM ABI Sözleşmelerine Genel Bakış
ms.date: 07/11/2018
ms.assetid: 23f4ae8c-3148-4657-8c47-e933a9f387de
ms.openlocfilehash: 8737f7b1cbe0651b43eb3b9990a4035b60bd01b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320726"
---
# <a name="overview-of-arm32-abi-conventions"></a>ARM32 ABI Sözleşmelerine Genel Bakış

ARM işlemcilerde Windows için derlenen kod için uygulama ikili arabirimi (ABI) standart ARM EABI'ye dayanır. Bu makalede, ARM ve standart Windows arasındaki önemli farklar vurgulamaktadır. Bu belge ARM32 ABI'yi kapsamaktadır. ARM64 ABI hakkında bilgi için [ARM64 ABI sözleşmelerine genel bakış](arm64-windows-abi-conventions.md)bölümüne bakın. Standart ARM EABI hakkında daha fazla bilgi için [ARM Mimarisi (harici bağlantı) için Uygulama İkili Arabirimi (ABI) bölümüne](http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.subset.swdev.abi/index.html) bakın.

## <a name="base-requirements"></a>Temel Gereksinimler

ARM'daki Windows, her zaman bir ARMv7 mimarisi üzerinde çalıştığını varsayılır. VFPv3-D32 veya daha sonra şeklinde kayan nokta desteği donanımda bulunmalıdır. VFP donanımda hem tek hassasiyetli hem de çift duyarlıklı kayan noktayı desteklemelidir. Windows çalışma süresi, VFP olmayan donanımda çalıştırmayı etkinleştirmek için kayan nokta öykünmesini desteklemez.

Gelişmiş SIMD Uzantıları (NEON) desteği- bu hem tamsayı hem de kayan nokta işlemlerini içerir— donanımda da bulunmalıdır. Öykünme için çalışma süresi desteği sağlanmaz.

Burada bulunan bölme desteği (UDIV/SDIV) şiddetle önerilir, ancak gerekli değildir. Tamsayı bölme desteğinden yoksun platformlar performans cezasına tabi olabilir, çünkü bu işlemlerin tuzağa düşürülmesi ve muhtemelen yamalı olması gerekir.

## <a name="endianness"></a>Endianness

ARM'deki Windows, küçük endian modunda yürütülür. Hem MSVC derleyicisi hem de Windows çalışma süresi her zaman az endian veri bekler. ARM yönerge kümesi mimarisindeki (ISA) SETEND talimatı, kullanıcı modu kodunun bile geçerli son durumu değiştirmesine izin veriyor olsa da, bir uygulama için tehlikeli olduğu için bunu yapmak önerilmez. Büyük sonlu modda bir özel durum oluşturulursa, davranış öngörülemez dir ve kullanıcı modunda bir uygulama hatasına veya çekirdek modunda bir hata denetimine neden olabilir.

## <a name="alignment"></a>Hizalama

Windows, ARM donanımına yanlış hizalanmış tamsayı erişimlerini saydam bir şekilde işleme olanağı sağlasa da, bazı durumlarda hizalama hataları yine de oluşturulabilir. Hizalama için aşağıdaki kurallara uyun:

- Yarım kelime boyutunda (16-bit) ve kelime boyutunda (32-bit) tümsedo yükleri ve depoların hizalanması gerekmez. Donanım bunları verimli ve şeffaf bir şekilde işler.

- Kayan nokta yükleri ve depoları hizalanmalıdır. Çekirdek hizalanmamış yükleri işler ve saydam olarak depolar, ancak önemli yükü ile.

- Yük veya depo çift (LDRD /STRD) ve birden fazla (LDM/STM) işlemi hizalanmalıdır. Çekirdek bunların çoğunu saydam bir şekilde işler, ancak önemli miktarda genel ilerler.

- Tüm cached bellek erişimleri, tüm insa erişimi için bile hizalanmış olmalıdır. Hizalanmamış erişimler hizalama hatasına neden olur.

## <a name="instruction-set"></a>Talimat Seti

ARM'da Windows için ayarlanan yönerge kesinlikle Thumb-2 ile sınırlıdır. Bu platformda çalıştırılan tüm kodların başlatılması ve her zaman Başparmak modunda kalması beklenir. Eski ARM yönerge kümesine geçiş denemesi başarılı olabilir, ancak geçerse, oluşan özel durumlar veya kesintiler kullanıcı modunda bir uygulama hatasına veya çekirdek modunda hata denetimine neden olabilir.

Bu gereksinimin bir yan etkisi, tüm kod işaretçileri düşük bit kümesi olması gerekir. Bu, yükleme ve BLX veya BX üzerinden dallı, işlemci Başparmak modunda kalır ve 32-bit ARM talimatları olarak hedef kodu yürütmek için denemek değil, böylece.

### <a name="it-instructions"></a>BT Talimatları

Bu özel durumlar dışında, Thumb-2 kodunda BT yönergelerinin kullanılmasına izin verilmez:

- BT yönergesi yalnızca bir hedef yönergesini değiştirmek için kullanılabilir.

- Hedef yönerge 16 bitlik bir yönerge olmalıdır.

- Hedef yönerge aşağıdakilerden biri olmalıdır:

   |16-Bit Opcodes|Sınıf|Kısıtlamalar|
   |---------------------|-----------|------------------|
   |MOV, MVN|Taşı|Rm != PC, Rd != PC|
   |LDR, LDR[S]B, LDR[S]H|Bellekten yük|Ama LDR edebi formları değil|
   |STR, STRB, STRH|Belleğe depola||
   |ADD, ADC, RSB, SBC, SUB|Ekleme veya çıkarma|Ama ADD / SUB SP, SP, imm7 formları değil<br /><br /> Rm != PC, Rdn != PC, Rdm != PC|
   |CMP, CMN|Karşılaştır|Rm != PC, Rn != PC|
   |Mul|Çarp||
   |ASR, LSL, LSR, ROR|Bit kayması||
   |VE, BIC, EOR, ORR, TST|Bitwise aritmetik||
   |Bx|Kayıt olunacak şube|Rm != PC|

Mevcut ARMv7 CPU'lar izin verilmeyen öğretim formlarının kullanımını rapor edemese de, gelecek nesillerin bildirmesi beklenmektedir. Bu formlar algılanırsa, bunları kullanan herhangi bir program tanımlanmamış bir yönerge özel durumuyla sonlandırılabilir.

### <a name="sdivudiv-instructions"></a>SDIV/UDIV yönergeleri

Tamsayı bölme yönergeleriSDIV ve UDIV kullanımı, bunları işlemek için yerel donanım olmadan platformlarda bile, tam olarak desteklenir. Bir Cortex-A9 işlemcide SDIV veya UDIV bölme başına ek yükü, girdilere bağlı olarak, 20-250 döngülerin toplam bölme süresine ek olarak yaklaşık 80 döngüdür.

## <a name="integer-registers"></a>Sonsayı kayıtları

ARM işlemcisi 16 tümseci kaydını destekler:

|Kaydettir|Uçucu?|Rol|
|--------------|---------------|----------|
|r0|Uçucu|Parametre, sonuç, çizik kaydı 1|
|r1|Uçucu|Parametre, sonuç, çizik kayıt 2|
|R2|Uçucu|Parametre, çizik kayıt 3|
|r3|Uçucu|Parametre, çizik kayıt 4|
|R4|Uçucu olmayan||
|r5|Uçucu olmayan||
|r6|Uçucu olmayan||
|r7|Uçucu olmayan||
|R8|Uçucu olmayan||
|r9|Uçucu olmayan||
|r10|Uçucu olmayan||
|r11|Uçucu olmayan|Çerçeve işaretçisi|
|r12|Uçucu|Prosedür içi çağrı sıfırı kaydı|
|r13 (SP)|Uçucu olmayan|Yığın işaretçisi|
|r14 (LR)|Uçucu olmayan|Bağlantı kaydı|
|r15 (PC)|Uçucu olmayan|Program sayacı|

Parametre ve iade değeri kayıtlarının nasıl kullanılacağı hakkında ayrıntılı bilgi için bu makaledeki Parametre Geçiş bölümüne bakın.

Windows, yığın çerçevesinin hızlı yürümesi için r11 kullanır. Daha fazla bilgi için Stack Walking bölümüne bakın. Bu gereksinim nedeniyle, r11 her zaman zincirin en üst teki halkasını işaret etmelidir. R11'i genel amaçlar için kullanmayın—kodunuz çözümleme sırasında doğru yığın yürüyüşleri oluşturmaz.

## <a name="vfp-registers"></a>VFP kayıtları

Windows yalnızca VFPv3-D32 yardımcı işlemci desteğine sahip ARM türevlerini destekler. Bu, kayan nokta kayıtlarının her zaman mevcut olduğu ve parametre geçişi için güvenilebildiği ve 32 kayıt kümesinin tamamının kullanıma hazır olduğu anlamına gelir. VFP kayıtları ve bunların kullanımı bu tabloda özetlenmiştir:

|Single|Double değerleri|Dörtlü|Uçucu?|Rol|
|-------------|-------------|-----------|---------------|----------|
|s0-s3|d0-d1|q0|Uçucu|Parametreler, sonuç, çizik kaydı|
|s4-s7|d2-d3|Q1|Uçucu|Parametreler, çizik kaydı|
|s8-s11|d4-d5|q2|Uçucu|Parametreler, çizik kaydı|
|s12-s15|d6-d7|q3|Uçucu|Parametreler, çizik kaydı|
|s16-s19|d8-d9|q4|Uçucu olmayan||
|s20-s23|d10-d11|q5|Uçucu olmayan||
|s24-s27|d12-d13|q6|Uçucu olmayan||
|s28-s31|d14-d15|q7|Uçucu olmayan||
||d16-d31|q8-q15|Uçucu||

Sonraki tabloda kayan nokta durumu ve denetim kaydı (FPSCR) bit alanları gösteriş:

|Bits|Anlamı|Uçucu?|Rol|
|----------|-------------|---------------|----------|
|31-28|NZCV|Uçucu|Durum bayrakları|
|27|QC|Uçucu|Kümülatif doygunluk|
|26|Ahp|Uçucu olmayan|Alternatif yarı hassas kontrol|
|25|Dn|Uçucu olmayan|Varsayılan NaN modu denetimi|
|24|Fz|Uçucu olmayan|Flush'dan sıfıra mod kontrolü|
|23-22|RMode|Uçucu olmayan|Yuvarlama modu kontrolü|
|21-20|Adım|Uçucu olmayan|Vektör Adım, her zaman 0 olmalıdır|
|18-16|Len|Uçucu olmayan|Vektör Uzunluğu, her zaman 0 olmalıdır|
|15, 12-8|IDE, IXE, vb.|Uçucu olmayan|Özel durum bindirme sökse, her zaman 0 olmalıdır|
|7, 4-0|IDC, IXC, vb.|Uçucu|Kümülatif özel durum bayrakları|

## <a name="floating-point-exceptions"></a>Kayan nokta özel durumları

Çoğu ARM donanımı IEEE kayan nokta özel durumlarını desteklemez. Donanım kayan nokta özel durumları olan işlemci türevlerinde, Windows çekirdeği özel durumları sessizce yakalar ve fpscr kaydında bunları dolaylı olarak devre dışı kılabilir. Bu, işlemci türevleri arasında normalleştirilmiş davranış sağlar. Aksi takdirde, özel durum desteği olmayan bir platformda geliştirilen kod, özel durum desteği olan bir platformda çalışırken beklenmeyen özel durumlar alabilir.

## <a name="parameter-passing"></a>Parametre geçişi

Variadik olmayan işlevler için ARM ABI'deki Windows, parametre geçişi için ARM kurallarına uyar— bu VFP ve Gelişmiş SIMD uzantılarını içerir. Bu kurallar, VFP uzantılarıyla birleştirilmiş [ARM Mimarisi için Yordam Çağrı Standardı'nı](http://infocenter.arm.com/help/topic/com.arm.doc.ihi0042c/IHI0042C_aapcs.pdf)izler. Varsayılan olarak, ilk dört arayıcı bağımsız değişkeni ve en fazla sekiz kayan nokta veya vektör bağımsız değişkeni kayıtlara geçirilir ve ek bağımsız değişkenler yığına geçirilir. Bağımsız değişkenler bu yordamı kullanarak kayıtlara veya yığına atanır:

### <a name="stage-a-initialization"></a>Aşama A: Başlatma

Başlatma, bağımsız değişken işleme başlamadan önce tam olarak bir kez gerçekleştirilir:

1. Sonraki Çekirdek Kayıt Numarası (NCRN) r0 olarak ayarlanır.

1. VFP kayıtları ayrılmamış olarak işaretlenir.

1. Sonraki Yığılmış Bağımsız Değişken Adresi (NSAA) geçerli SP olarak ayarlanır.

1. Bellekte sonuç döndüren bir işlev çağrılırsa, sonucun adresi r0'a yerleştirilir ve NCRN r1 olarak ayarlanır.

### <a name="stage-b-pre-padding-and-extension-of-arguments"></a>Aşama B: Ön doldurma ve bağımsız değişkenlerin uzantısı

Listedeki her bağımsız değişken için, aşağıdaki listeden ilk eşleşen kural uygulanır:

1. Bağımsız değişken, boyutu hem arayan hem de çağrıcı tarafından statik olarak belirlenemeyen bileşik bir türse, bağımsız değişken belleğe kopyalanır ve kopyaiçin bir işaretçi yle değiştirilir.

1. Bağımsız değişken bir bayt veya 16 bit yarım sözcükse, 32 bitlik tam sözcük için sıfır uzatılmış veya işaret genişletilmişve 4 bayt bağımsız değişken olarak kabul edilir.

1. Bağımsız değişken bileşik bir türse, boyutu 4'ün en yakın katlarına yuvarlanır.

### <a name="stage-c-assignment-of-arguments-to-registers-and-stack"></a>Aşama C: Bağımsız değişkenlerin kayda ve yığına atanması

Listedeki her bağımsız değişken için, bağımsız değişken ayrılana kadar sırayla aşağıdaki kurallar uygulanır:

1. Bağımsız değişken bir VFP türüyse ve uygun türde yeterince ardışık ayrılmamış VFP kaydı varsa, bağımsız değişken bu tür kayıtların en düşük numaralı sırasına ayrılır.

1. Bağımsız değişken bir VFP türüyse, kalan tüm ayrılmamış kayıtlar kullanılamaz olarak işaretlenir. NSAA, bağımsız değişken türü için doğru şekilde hizalanana ve bağımsız değişken ayarlanan NSAA'daki yığına kopyalanana kadar yukarı doğru ayarlanır. NSAA daha sonra bağımsız değişkenin boyutuna göre artımlı.

1. Bağımsız değişken 8 bayt hizalama gerektiriyorsa, NCRN bir sonraki çift kayıt numarasına yuvarlanır.

1. 32 bit sözcüklerdeki bağımsız değişkenin boyutu r4 eksi NCRN'den fazla değilse, bağımsız değişken NCRN'den başlayarak alt numaralı kayıtları kaplayan en az önemli bitle birlikte çekirdek kayıtlara kopyalanır. NCRN kullanılan kayıt sayısına göre artımlanır.

1. NCRN r4'ten küçükse ve NSAA SP'ye eşitse, bağımsız değişken çekirdek kayıtları ve yığın arasında bölünür. Bağımsız değişkenin ilk bölümü, NCRN'den başlayarak r3'e kadar ve dahil olmak üzere çekirdek kayıtlara kopyalanır. Bağımsız değişkenin geri kalanı NSAA'dan başlayarak yığına kopyalanır. NCRN r4 olarak ayarlanır ve NSAA bağımsız değişkenin boyutu eksi kayıtlarda geçirilen miktar adedine göre artımlanır.

1. Bağımsız değişken 8 bayt hizalama gerektiriyorsa, NSAA sonraki 8 bayt hizalanmış adrese yuvarlanır.

1. Bağımsız değişken NSAA'da belleğe kopyalanır. NSAA bağımsız değişkenin boyutuna göre artarak.

VFP kayıtları variadik işlevler için kullanılmaz ve Aşama C kuralları 1 ve 2 yoksayılır. Bu, bir variadic işlevin, kayıt bağımsız değişkenlerini arayan tarafından geçirilen ek bağımsız değişkenlere hazırlamak ve ardından doğrudan yığından tüm bağımsız değişken listesine erişmek için isteğe bağlı bir itme {r0-r3} ile başlayabileceğini gösterir.

İnteger türü değerleri r0 olarak döndürülür ve isteğe bağlı olarak 64 bit dönüş değerleri için r1'e uzatılır. VFP/NEON kayan nokta veya SIMD türü değerleri uygun şekilde s0, d0 veya q0 olarak döndürülür.

## <a name="stack"></a>Yığın

Yığın her zaman 4 bayt hizalı olarak kalmalı ve herhangi bir işlev sınırında 8 bayt hizalanmış olmalıdır. Bu, 64 bit lik yığın değişkenlerinde birbirine kenetlenmiş işlemlerin sık kullanımını desteklemek için gereklidir. ARM EABI, yığının herhangi bir ortak arabirimde 8 bayt hizalanmış olduğunu belirtir. Tutarlılık için ARM ABI'deki Windows, herhangi bir işlev sınırını ortak arabirim olarak kabul eder.

Çerçeve işaretçisi kullanmak zorunda olan işlevler(örneğin, arayan `alloca` veya yığın işaretçisini dinamik olarak değiştiren işlevler- işlev önözünde r11'deki çerçeve işaretçisini ayarlamalı ve sonsöze kadar değişmeden bırakmalıdır. Çerçeve işaretçisi gerektirmeyen işlevler, önsözdeki tüm yığın güncelleştirmelerini gerçekleştirmeli ve yığın işaretçisini sonsöze kadar değişmeden bırakmalıdır.

Yığına 4 KB veya daha fazla ayıran işlevler, son sayfadan önce her sayfaya sırayla dokunulduğundan emin olmalıdır. Bu, hiçbir kodun Windows'un yığını genişletmek için kullandığı koruma sayfalarını "atlayamamasını" sağlar. Genellikle, `__chkstk` bu, r4'te 4'e bölünen baytlarda toplam yığın ayırması geçirilen ve son yığın ayırma miktarını r4'te baytlarda döndüren yardımcı tarafından yapılır.

### <a name="red-zone"></a>Kırmızı bölge

Geçerli yığın işaretçisinin hemen altındaki 8 baytlık alan çözümleme ve dinamik yama için ayrılmıştır. Bu, [sp, #-8] depolar ve geçici olarak rasgele amaçlar için bunları kullanır, dikkatle oluşturulan kod eklenmesine izin verir. Windows çekirdeği, hem kullanıcı modunda hem de çekirdek modunda bir özel durum veya kesme oluşursa, bu 8 baytın üzerine yazılmayacağını garanti eder.

### <a name="kernel-stack"></a>Çekirdek yığını

Windows'daki varsayılan çekirdek modu yığını üç sayfadır (12 KB). Çekirdek modunda büyük yığın arabellekleri olan işlevler oluşturmamaya dikkat edin. Bir kesme çok az yığın headroom ile gelebilir ve bir yığın panik bugcheck neden olabilir.

## <a name="cc-specifics"></a>C/C++ özellikleri

Numaralandırma, numaralandırmada en az bir değer 64 bit çift kelimedepolama gerektirmediği sürece 32 bit tamsayı türleridir. Bu durumda, numaralandırma 64 bit tamsayı türüne yükseltilir.

`wchar_t`diğer platformlarile uyumluluğu korumak için eşdeğer `unsigned short`olarak tanımlanır.

## <a name="stack-walking"></a>Yığın yürüyüş

Windows kodu, hızlı yığın yürümesi sağlamak için etkin çerçeve işaretçileri[(/Oy (Frame-Pointer Ekspre)](reference/oy-frame-pointer-omission.md)ile derlenir. Genel olarak, r11 kaydı zincirdeki bir sonraki bağlantıya işaret eder, bu da yığındaki önceki çerçeveye işaretçiyi ve geri dönüş adresini belirten bir {r11, lr} çiftidir. Kodunuzun gelişmiş profil oluşturma ve izleme için çerçeve işaretçilerine de olanak sağlamasını öneririz.

## <a name="exception-unwinding"></a>Özel durum gevşeme

İstisna işleme sırasında yığın boşaltma, gevşeme kodlarının kullanımıyla etkinleştirilir. Gevşeme kodları, çalıştırılabilir görüntünün .xdata bölümünde depolanan bayt dizisidir. İşlev prologve epilog kodunun işleyişini soyut bir şekilde açıklarlar, böylece bir işlevin önsözünün etkileri arayanın yığın çerçevesine gevşemeye hazırlık olarak geri alınabilir.

ARM EABI, gevşeme kodları kullanan bir özel durum gevşetme modeli belirtir. Ancak, bu belirtim, işlemcinin bir işlevin önsözünün veya sonsözünün ortasında olduğu durumlarda ele alması gereken Windows'da gevşemek için yeterli değildir. ARM özel durum verileri ve gevşeme hakkında daha fazla bilgi için [ARM Özel Durum İşleme'ye](arm-exception-handling.md)bakın.

Oluşturulan kodun özel durum işlemeye katılabilmesi için `RtlAddFunctionTable` çağrılarda ve ilişkili işlevlerde belirtilen dinamik işlev tabloları kullanılarak dinamik olarak oluşturulan kodun tanımlanmasını öneririz.

## <a name="cycle-counter"></a>Döngü sayacı

Windows'u çalıştıran ARM işlemcilerinin bir döngü sayacını desteklemesi gerekir, ancak sayacı doğrudan kullanmak sorunlara neden olabilir. Bu sorunları önlemek için ARM'deki Windows, normalleştirilmiş 64 bit çevrim sayacı değeri istemek için tanımlanmamış bir opcode kullanır. C veya C++'dan, uygun opkodu yalamak için `__rdpmccntr64` içsel kullanın; montajdan, `__rdpmccntr64` talimatı kullanın. Çevrim sayacını okumak Cortex-A9'da yaklaşık 60 döngü alır.

Sayaç gerçek bir döngü sayacı, bir saat değil; bu nedenle, sayma sıklığı işlemci frekansına göre değişir. Geçen saat süresini ölçmek istiyorsanız, kullanın. `QueryPerformanceCounter`

## <a name="see-also"></a>Ayrıca bkz.

[Genel Visual C++ ARM Geçiş Sorunları](common-visual-cpp-arm-migration-issues.md)<br/>
[ARM Özel Durum Taşıma](arm-exception-handling.md)
