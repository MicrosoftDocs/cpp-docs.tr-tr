---
title: ARM ABI kuralları genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: f78e5731e6c8d4125fb8afc184cd6e4f2a74cb7a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379100"
---
# <a name="overview-of-arm-abi-conventions"></a>ARM ABI kuralları genel bakış
Windows için ARM işlemci derlenmiş kod için uygulama ikili arabirimi (ABI) üzerinde standart ARM EABI temel alır. Bu makale, ARM Windows standart arasındaki temel farklılıklar vurgular. Standart ARM EABI hakkında daha fazla bilgi için bkz: [uygulama ikili arabirimi (ABI) ARM mimarisi için](http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.subset.swdev.abi/index.html).  
  
## <a name="base-requirements"></a>Temel gereksinimleri  
 Windows ARM üzerinde her zaman bir ARMv7 mimarisine çalıştığını varsayar. Kayan nokta desteği VFPv3 D32 veya sonraki biçiminde donanımda mevcut olması gerekir. VFP tek duyarlıklı ve çift duyarlıklı kayan nokta donanımda desteklemesi gerekir. Windows çalışma zamanı VFP olmayan donanım üzerinde çalışmasını sağlamak için kayan nokta öykünmesini desteklemez.  
  
 Gelişmiş SIMD Uzantıları (NEON) desteği — bu tamsayı ve kayan nokta işlemlerini içerir — donanımında bulunmalıdır. Öykünme çalıştırma desteği sağlanır.  
  
 Tamsayı bölme desteği (UDIV/SDIV) şiddetle önerilir, ancak gerekli değildir. Yakalanan ve büyük olasılıkla düzeltme eki bu işlemler olduğundan tamsayı bölme destek eksikliği platformları performans cezasına sebep.  
  
## <a name="endianness"></a>Endianness  
 Windows ARM üzerinde little endian modunda yürütür. Visual C++ derleyicisi ve Windows çalışma zamanı little endian verileri her zaman bekler. ARM yönergesindeki SETEND yönerge kümesi de geçerli endianness değiştirmek için bile kullanıcı modu kodu mimari (ISA) sayesinde, bir uygulama için tehlikeli olduğundan bunun nedenle önerilmez. Bir özel durum ise big endian modunda oluşturulan davranışı tahmin edilemez ve kullanıcı modunda bir uygulama hatası ya da hata denetimi çekirdek modunda neden olabilir.  
  
## <a name="alignment"></a>Hizalama  
 Şeffaf bir şekilde, Windows yanlış hizalanmış tamsayı işlemek ARM donanım sağlar, ancak hizalama hataları hala bazı durumlarda oluşturulan erişir. Bu kurallar hizalama izleyin:  
  
-   Yarı-word boyutlu (16-bit) ve word ölçekli (32 bit) tamsayı yükler ve depoları hizalanacak gerekmez. Donanım bunları etkili ve şeffaf bir şekilde işler.  
  
-   Kayan nokta yükler ve depoları hizalanmalıdır. Çekirdek hizalanmamış yükleri işleme ve şeffaf bir şekilde ancak önemli yüküyle depolar.  
  
-   Yükleme veya çift (LDRD/STRD) depolamak ve birden çok (LDM/STM) işlemleri hizalanmalıdır. Çekirdek saydam ancak önemli ek yükü ile bunların çoğu işler.  
  
-   Hatta tamsayı erişimler için tüm önbelleğe alınmamış bellek erişimler hizalanmalıdır. Hizalanmamış erişimleri bir hizalama hatasına neden.  
  
## <a name="instruction-set"></a>Yönerge kümesi  
 Windows ARM için ayarlanmış yönerge Flash-2'ye kesinlikle sınırlıdır. Bu platformda çalıştırılan tüm kod başlatın ve her zaman Flash modunda kalır beklenir. Eski ARM yönerge kümesine geçiş girişimi başarısız olabilir, ancak varsa, tüm özel durumları veya ortaya çıkan kesintileri kullanıcı modunda bir uygulama hatası ya da hata denetimi çekirdek modunda neden olabilir.  
  
 Bu gereksinim, bir yan etkisi, tüm kod işaretçileri ayarlamak düşük bit olmalıdır ' dir. Bu, böylelikle yüklenir ve BLX veya BX aracılığıyla dallandırılmış, işlemci Flash modunda kalır ve 32-bit ARM yönergeleri hedef kod çalıştırmasına deneyin değil.  
  
### <a name="it-instructions"></a>BT yönergeleri  
 Flash 2 kodu BT yönergeleri kullanın, bu özel durumlar dışında izin verilmez:  
  
-   BT yönerge yalnızca tek bir hedef yönerge değiştirmek için kullanılabilir.  
  
-   Hedef yönerge bir 16 bit yönergesi olması gerekir.  
  
-   Hedef yönerge bunlardan biri olmalıdır:  
  
    |16 bit işlem kodları|örneği|Kısıtlamalar|  
    |---------------------|-----------|------------------|  
    |MOV, MVN|Taşıma|RM! bilgisayarı, Rd =! PC =|  
    |LDR, LDR [S] B, LDR [S] H|Bellekten yükleme|Ancak LDR değişmez değer formlar|  
    |STR, STRB, STRH|Bellek için depolama||  
    |EKLEME, ADC, RSB, SBC, ALT|Ekleme veya çıkarma|Ancak değil Ekle/alt SP, SP, imm7 formlar<br /><br /> RM! PC, Rdn =! PC, Rdm =! PC =|  
    |CMP, CMN|{1&gt;Karşılaştır&lt;1}|RM! PC, kaydırmayı =! PC =|  
    |MUL|Çarp||  
    |ASR, LSL, LSR, ROR|Bit kaydırma||  
    |VE, BIC, EOR, ORR TST|Bit düzeyinde aritmetik||  
    |BX|Kaydetmek için şube|RM! PC =|  
  
 Geçerli ARMv7 CPU izin verilmeyen yönerge formları kullanımını raporlayamaz rağmen gelecek nesil beklenir. Bu formlar algılanırsa, bunları kullanan herhangi bir programı tanımsız yönerge özel durumla sona erdirilecek.  
  
### <a name="sdivudiv-instructions"></a>SDIV/UDIV yönergeleri  
 Tamsayı kullanımını SDIV ve UDIV tam olarak desteklenir, hatta bunları işlemek için yerel donanım olmadan platformlarda yönergeleri bölün. Cortex A9 işlemci SDIV veya UDIV sıfırla bölme başına yükü girişleri bağlı olarak, 20-250 döngüleri genel bölme süre yanı sıra yaklaşık 80 döngüleri var.  
  
## <a name="integer-registers"></a>Tamsayı kaydeder  
 ARM işlemci 16 tamsayı yazmaçları destekler:  
  
|Yazmaç|Volatile?|Rol|  
|--------------|---------------|----------|  
|r0|Volatile|Parametresi, sonuç, karalama kaydetme 1|  
|R1|Volatile|Parametresi, sonuç, karalama kaydı 2|  
|R2|Volatile|Parametresi, sıfırdan kayıt 3|  
|R3|Volatile|Parametresi, sıfırdan kayıt 4|  
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
|R15 kayıtları (PC)|Geçici olmayan|Program sayacı|  
  
 Nasıl kullanılacağı hakkında ayrıntılar için parametre ve dönüş değeri yazmaçlar parametre geçirme bölümüne bakın bu makalede.  
  
 Windows hızlı-taramasını için yığın çerçeve r11 kullanır. Daha fazla bilgi için yığın taramasını bölümüne bakın. Bu gereksinimden dolayı r11 zincirindeki en üstteki bağlamak için her zaman göstermesi gerekir. R11 genel amaçlar için kullanmayın — kodunuzun doğru yığın yetenekte Çözümleme sırasında oluşturmaz.  
  
## <a name="vfp-registers"></a>VFP kaydeder  
 Windows Destek VFPv3 D32 eşişlemcisi sahip ARM çeşitleri yalnızca destekler. Bunun anlamı kayan nokta kayıtları her zaman varsa ve üzerinde için parametre geçirme dayanıyordu ve tam 32 yazmaçlar ayarlamak için kullanılabilir. VFP kaydeder ve bu tabloda kullanımları özetlenir:  
  
|Gösteren|Double değerleri|Quads|Volatile?|Rol|  
|-------------|-------------|-----------|---------------|----------|  
|S0 s3|D0 d1|q0|Volatile|Kayıt parametreleri, sonuç boş|  
|S4 s7|d3 D2|S1|Volatile|Parametreler, karalama kaydetme|  
|S8 s11|D4 d5|S2|Volatile|Parametreler, karalama kaydetme|  
|s12 s15|D6 D7 hücresini|S3|Volatile|Parametreler, karalama kaydetme|  
|S16 s19|D8 d9|S4|Geçici olmayan||  
|S20'in s23|D10 d11|S5|Geçici olmayan||  
|s24 s27|d12 d13|S6|Geçici olmayan||  
|s28 s31|D14 d15|S7|Geçici olmayan||  
||d16 d31|S8 S15|Volatile||  
  
 Kayan nokta durum sonraki tablo gösterir ve denetim (FPSCR) bit alanları kaydedin:  
  
|Bits|Açıklama|Volatile?|Rol|  
|----------|-------------|---------------|----------|  
|31-28|NZCV|Volatile|Durum Bayrakları|  
|27|QC|Volatile|Toplu Doygunluk|  
|26|AHP|Geçici olmayan|Alternatif yarı duyarlıklı denetimi|  
|25|DN|Geçici olmayan|Varsayılan NaN modu denetimi|  
|24|FZ|Geçici olmayan|Flush sıfır modu denetimi|  
|23-22|RMode|Geçici olmayan|Yuvarlama modu denetimi|  
|21-20|STRIDE|Geçici olmayan|STRIDE vektör, her zaman 0 olmalıdır|  
|18-16|Len|Geçici olmayan|Uzunluk vektör, her zaman 0 olmalıdır|  
|15, 12-8|IDE, IXE, vb.|Geçici olmayan|Özel durum etkinleştir BITS tuzak, her zaman 0 olmalıdır|  
|7, 4-0|IDC, IXC, vb.|Volatile|Toplu özel durumu bayrakları|  
  
## <a name="floating-point-exceptions"></a>Kayan nokta özel durumlar  
 Çoğu ARM donanım IEEE kayan nokta özel durumlar desteklemez. Donanım kayan nokta özel durumlara sahip işlemci çeşitleri, Windows Çekirdeği sessizce özel durumları yakalar ve örtük olarak bunları FPSCR kayıt defterinde devre dışı bırakır. Bu, işlemci çeşitler arasında normalleştirilmiş davranış sağlar. Aksi takdirde, özel durum desteği olan bir platformda çalışırken özel durum desteği olmayan bir platformda geliştirilmiş kod beklenmeyen özel durum alabilir.  
  
## <a name="parameter-passing"></a>Parametre Geçirme  
 Variadic olmayan işlevleri için ARM ABI Windows ARM parametre geçirme için kurallara — bu VFP ve Gelişmiş SIMD uzantıları içerir. Bu kurallar izleyin [ARM mimarisi için yordam çağrısı standart](http://infocenter.arm.com/help/topic/com.arm.doc.ihi0042c/IHI0042C_aapcs.pdf), birleştirilmiş VFP uzantılara sahip. Göre varsayılan, ilk dört tamsayı bağımsız değişkeni ve kayan nokta sekiz yukarı veya vektör bağımsız değişkenleri Yazmaçları geçirilir ve ek bağımsız değişkenler, yığında geçirilir. Bağımsız değişkenler kaydeder veya yığını için bu yordamı kullanarak atanır:  
  
### <a name="stage-ainitialization"></a>Aşama A — başlatma  
 Bağımsız değişken işleme başlamadan önce başlatılması tam olarak bir kez gerçekleştirilir:  
  
1.  Sonraki çekirdek kayıt numarası (NCRN) r0 için ayarlanır.  
  
2.  VFP yazmaçlar işaretlenmiş olarak ayrılmamış.  
  
3.  Sonraki Yığılmış bağımsız değişkeni adresi (NSAA) Geçerli SP. ayarlanır  
  
4.  Bellekte bir sonuç döndüren bir işlev çağrılırsa, sonuç adresini r0 yerleştirilir ve NCRN r1 için ayarlanır.  
  
### <a name="stage-bpre-padding-and-extension-of-arguments"></a>Aşama B — öncesi doldurma ve bağımsız değişkenleri uzantısı  
 Listedeki her bağımsız değişken için aşağıdaki listedeki ilk eşleşen kural uygulanır:  
  
1.  Bağımsız değişken büyüklüğü statik olarak çağıran ve çağrılan tarafından belirlenemiyor bileşik bir tür ise, bağımsız değişkeni için bellek kopyalanır ve kopyalamak için bir işaretçi olarak değiştirilir.  
  
2.  Bağımsız değişken bir bayt veya 16 bit yarı-word ise, sıfır genişletilmiş ya da bir 32 bit tam sözcük oturum genişletilmiş ve 4-bayt bağımsız değişken olarak kabul edilir.  
  
3.  Bağımsız değişken bileşik bir tür ise boyutuna en yakın 4 katına yuvarlanır.  
  
### <a name="stage-cassignment-of-arguments-to-registers-and-stack"></a>Aşama C — kaydeder ve yığın bağımsız değişkenleri atama  
 Bağımsız değişken ayrılan kadar listedeki her bağımsız değişken için aşağıdaki kurallar sırayla uygulanır:  
  
1.  Bağımsız değişkeni bir VFP türüdür ve uygun türde ardışık yeterli ayrılmamış VFP yazmaçlar varsa bağımsız değişkeni tür yazmaçlar en düşük numaralı dizisi tahsis edilir.  
  
2.  Bağımsız değişkeni bir VFP türü ise, tüm kalan ayrılmamış kasalar kullanılamaz olarak işaretlenmiş. NSAA yukarı doğru bağımsız değişken türü hizalanır ve bağımsız değişkeni ayarlanmış NSAA yığında kopyalanır kadar ayarlanır. NSAA sonra bağımsız değişkeni boyutuyla artırılır.  
  
3.  Bağımsız değişken 8-bayt hizalama gerektiriyorsa, NCRN sonraki bile kayıt sayıya yuvarlanır.  
  
4.  32-bit sözcükler değişkeninde boyutunu NCRN eksi r4'den fazla değilse, bağımsız değişkeni NCRN düşük numaralı yazmaçlar kaplayan en az önemli BITS ile başlayarak, çekirdek yazmaçlar kopyalanır. NCRN kullanılan yazmaçlar sayısına göre artırılır.  
  
5.  NCRN r4 küçüktür ve NSAA SP eşit ise, bağımsız değişkeni çekirdek kaydeder ve yığın arasında bölünür. Bağımsız değişken ilk bölümü NCRN kadar başlatma ve r3 dahil olmak üzere çekirdek kaydeder kopyalanır. Bağımsız değişken kalanı NSAA başlangıç yığına kopyalanır. NCRN r4 için ayarlanır ve NSAA bağımsız değişkeni eksi Yazmaçları geçirilen tutarı boyutuna artırılır.  
  
6.  Bağımsız değişken 8-bayt hizalama gerektiriyorsa, sonraki 8 bayt hizalı adresi NSAA yuvarlanır.  
  
7.  Bağımsız değişken NSAA bellek kopyalanır. NSAA bağımsız değişkeni boyutuyla artırılır.  
  
 VFP yazmaçlar variadic işlevleri için kullanılmaz ve aşama C kurallarını 1 ve 2 göz ardı edilir. Bu variadic işlevi kayıt bağımsız değişkenleri çağıran tarafından geçirilen diğer ek bağımsız değişkenler için önüne eklediğinizden isteğe bağlı bir itme {r0-r3}'ile başlayan ve ardından tüm bağımsız değişken listesi doğrudan yığınından erişim anlamına gelir.  
  
 Tamsayı türü değerleri için 64-bit dönüş değerleri r1 için isteğe bağlı olarak genişletilmiş r0 döndürülür. VFP/NEON kayan nokta veya SIMD türü değerleri s0, d0 ya da uygun şekilde q0 döndürülür.  
  
## <a name="stack"></a>Yığın  
 Yığın her zaman hizalı 4-bayt kalması ve tüm işlevi sınırında hizalı 8-bayt olmalıdır. Bu, 64-bit yığını değişkenleri birbirine kenetlenmiş işlemler sık kullanımını desteklemek için gereklidir. ARM EABI yığının ortak bir arabirim hizalı 8-bayt olduğunu belirtir. Tutarlılık için ortak bir arabirim olarak herhangi bir işlev kenarının ARM ABI Windows'ta göz önünde bulundurur.  
  
 Çerçeve işaretçisi kullanmak zorunda işlevleri — Örneğin, bu arama işlevleri `alloca` veya dinamik olarak yığın işaretçisi değiştirme — çerçeve işaretçisi r11 kadar epilog değiştirmeden bırakın ve işlev giriş olarak ayarlamanız gerekir. Çerçeve işaretçisi gerektirmeyen işlevleri başlangıç tüm yığın güncelleştirmeleri gerçekleştirmek ve epilog kadar değişmeden yığın işaretçisi bırakın.  
  
 4 KB veya daha fazla yığınındaki ayırma işlevleri son sayfasında önce her bir sayfa sırayla işlemdeki emin olmanız gerekir. Bu kod yok "üzerinden Windows yığın genişletmek için kullandığı koruma sayfaları leap," sağlar. Genellikle, bu yapılır `__chkstk` Yardımcısı, geçirilen toplam yığın ayırma 4'te r4 bölü bayt ve bayt r4 edilene son yığın ayırma miktarını döndürür.  
  
### <a name="red-zone"></a>Kırmızı bölge  
 Geçerli yığın işaretçisi hemen altındaki 8-bayt alanı çözümleme ve dinamik düzeltme için ayrılmış. Bu, 2 kasalarda depoladığı eklenmesi için dikkatle oluşturulan kod verir [sp, # 8] ve bunları rasgele amaçları için geçici olarak kullanır. Windows Çekirdeği bir özel durum ya da kesme hem kullanıcı modu hem de çekirdek modu oluşursa'nın bu 8 bayt yazılmaz güvence altına alır.  
  
### <a name="kernel-stack"></a>Çekirdek yığını  
 Windows varsayılan çekirdek modu yığınında üç sayfa (12 KB) olur. Büyük yığın arabellekleri çekirdek modunda olan işlevler oluşturma konusunda dikkatli olun. Kesme, çok az yığın boş alan oturum gelir ve bir yığın Panik hata denetimi neden olabilir.  
  
## <a name="cc-specifics"></a>C/C++ özellikleri  
 Listedeki en az bir değer 64-bit çift sözcük depolama gerektirmedikçe numaralandırmalar 32 bit tam sayı türleridir. Bu durumda, sabit bir 64-bit tamsayı türü yükseltilir.  
  
 `wchar_t` eşdeğer olarak tanımlanan `unsigned short`, diğer platformlar ile uyumluluğu korumak için.  
  
## <a name="stack-walking"></a>Taramasını yığını  
 Etkin çerçeve işaretçisi ile derlenmiş Windows kod ([/Oy (Çerçeve işaretçisini atlama)](../build/reference/oy-frame-pointer-omission.md)) hızlı yığın taramasını etkinleştirmek için. Genellikle, r11 kaydetmek sonraki bağlantı noktalarına bir {r11, lr} olan zincirinde önceki çerçeve işaretçisi yığını ve dönüş adresi belirtir çifti. Kodunuzu Ayrıca çerçeve işaretçisi profil oluşturma ve izleme için etkinleştirmenizi öneririz.  
  
## <a name="exception-unwinding"></a>Özel durum geriye doğru izleme  
 Özel durum işleme sırasında geriye doğru izleme yığın bırakma kodlarının kullanımı tarafından etkinleştirilir. Yürütülebilir görüntü sanal işlem bulunur bölümünde depolanan bayt dizisi bırakma kodlarıdır. Böylece bir işlevin giriş etkilerini arayanın yığın çerçevesi için geriye doğru izleme için hazırlık alınabilecek soyut bir şekilde işlev giriş ve Epilog kodu işlemi açıklanmaktadır.  
  
 ARM EABI kullanan bir özel durum unwinding modeli kodlarının bırakma belirtir. Ancak, bu özellikteki işlemci giriş veya bir işlevin epilog ortasında olduğu durumlarda işlemelidir Windows geriye doğru izleme için yeterli değil. ARM özel durum verileri ve geriye doğru izleme pencereleri hakkında daha fazla bilgi için bkz: [ARM özel durum işleme](../build/arm-exception-handling.md).  
  
 Dinamik olarak üretilen kod çağrılarında belirtilen dinamik işlevi tablolar kullanarak açıklanan öneririz `RtlAddFunctionTable` ve oluşturulan kod özel durum işleme katılabilmesi İşlevler, ilişkili.  
  
## <a name="cycle-counter"></a>Sayaç döngüsü  
 Windows çalıştıran ARM işlemcileri döngüsü sayaç desteklemek için gerekli olan, ancak sayaç kullanarak doğrudan sorunlara neden olabilir. Bu sorunları önlemek için normalleştirilmiş bir 64-bit döngüsü sayaç değeri istemek için tanımsız opcode ARM Windows kullanır. C veya C++, kullanın `__rdpmccntr64` iç için uygun opcode yayma; derleme kullanın `__rdpmccntr64` yönergesi. Döngü sayacı okuma yaklaşık 60 oynatılmayacağını Cortex A9 alır.  
  
 Bir saat doğru döngüsü sayaç sayacıdır; Bu nedenle, sayım sıklığı işlemci sıklığı değişir. Geçen saatin ölçmek istediğiniz kullanırsanız `QueryPerformanceCounter`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Visual C++ ARM geçiş sorunları](../build/common-visual-cpp-arm-migration-issues.md)   
 [ARM Özel Durum İşleme](../build/arm-exception-handling.md)