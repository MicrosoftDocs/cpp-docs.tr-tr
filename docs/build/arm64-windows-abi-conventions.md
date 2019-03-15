---
title: ARM64 ABI kurallarına genel bakış
ms.date: 07/11/2018
ms.openlocfilehash: 537f8cf5bb8db61854bea7f4624e3dd3176c6a59
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816548"
---
# <a name="overview-of-arm64-abi-conventions"></a>ARM64 ABI kurallarına genel bakış

Temel ABI için derlendiğinde Windows ve çoğunlukla için 64 bit modunda (ARMv8 veya üzeri mimarileri) ARM işlemci çalıştırılmasında ARM'ın standart AArch64 EABI izler. Bu makalede bazı önemli varsayımlar ve EABI içinde belgelenmiştir gelen değişiklikleri vurgular. 32-bit ABI hakkında daha fazla bilgi için bkz. [genel bakış, ARM ABI kurallarına](overview-of-arm-abi-conventions.md). Standart ARM EABI hakkında daha fazla bilgi için bkz: [uygulama ikili arabirimi (ABI) ARM mimarisi için](http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.subset.swdev.abi/index.html) (dış bağlantı).

## <a name="definitions"></a>Tanımlar

64-bit desteği sunulmasıyla birlikte, çeşitli koşulları ARM tanımlanır:

- **AArch32** – Thumb modu yürütme dahil olmak üzere ARM tarafından tanımlanan mimari (ISA) eski 32-bit yönerge ayarlayın.
- **AArch64** – yeni bir 64-bit yönerge ARM tarafından tanımlanan mimari (ISA) ayarlayın.
- **ARMv7** – belirtimi "7 oluşturma" ARM donanım, yalnızca AArch32 için destek içerir. Windows ARM için ilk sürümü desteklenen ARM donanım sürümüdür.
- **ARMv8** – nesil"8" belirtimi ARM donanım, AArch32 hem AArch64 için destek içerir.

Bu tanımları yanı sıra Windows bu terimleri kullanırız:

- **ARM** – 32 bit ARM mimarisi (AArch32) ifade eder. Bu bazen WoA (Windows üzerinde ARM) olarak adlandırılır.
- **ARM32** – ARM, aynı yukarıdaki; anlaşılması için bu belgede kullanılan.
- **ARM64** – 64-bit ARM mimarisi (AArch64) ifade eder. WoA64 de yoktur.

Son olarak, veri türleri için söz konusu olduğunda aşağıdaki tanımları ARM başvurulur:

- **Kısa vektör** – Bu, doğrudan SIMD içinde gösterilebilen bir veri türü; yani, her öğe, 1, 2, 4 veya 8 bayt burada olabilir, boyutu (bayt), 8 veya 16 hizalanmış öğeler, 8 veya 16 bayt tutarında oluşan bir vektörü
- **(Homojen Floating-point toplama) HFA** – 2-4 aynı kayan nokta üyeler (float veya double) olan bir veri türü budur.
- **HVA (homojen kısa vektör toplama)** – 2-4 özdeş kısa vektör üyesi olan bir veri türü budur.

## <a name="base-requirements"></a>Temel gereksinimleri

Bir ARMv8 üzerinde çalışıyor veya üzeri mimarisi her zaman Windows ARM64 sürümünü varsayar. Kayan nokta hem ve NEON desteği donanım bulunması varsayılmıştır.

İçin tam destek AArch32 uygulamaların ARMv8 belirtilmesine izin verir ancak da şu anda Windows (yani, herhangi bir plan için WOW64) ARM64 sürümünü varolan ARM32 uygulamaların çalıştırılmasını desteklemek üzere herhangi bir plan vardır. Gelecekte yeniden değerlendirme tabi budur ancak onu geçerli çalışma varsayılır.

ARMv8 belirtimi AArch32 ve AArch64 için isteğe bağlı yeni şifreleme ve CRC yardımcı işlem kodlarını açıklar. Bu destek, şu anda isteğe bağlı ancak önerilen değerdir. Bu işlem kodlarını yararlanmak isteyen kod çalışma zamanı denetimleri kendi varlığını gerçekleştirmeniz gerekir.

## <a name="endianness"></a>Endianness

Olarak ARM32 ile ARM64 Windows üzerinde Windows sürümünü endian modunda yürütülür. Endianness geçiş zorlamak daha kolay olacak şekilde AArch64, çekirdek modu desteği olmadan elde etmek zor olabilir.

## <a name="alignment"></a>Hizalama

ARM64'te çalışan Windows yanlış hizalanmış erişimleri şeffaf bir şekilde işlemek CPU donanım sağlar. AArch32 gelen bir gelişme Bu destek şimdi de (birden çok sözcük erişim dahil) tüm tamsayı erişir ve kayan nokta erişimler için çalışır.

Ancak, önbelleğe alınmamış (cihaz) bellek erişimlerinin yine de her zaman hizalanması gerekir. Üzerinde okuma/yanlış hizalanmış verileri önbelleğe alınmamış bellekten gerekir play yazma çağrılabilir kodu varsa buna şeyleri güvenli ve verilere sağlanan tüm erişimlerde uygun olduğundan emin olun.

## <a name="integer-registers"></a>Tamsayı kaydeder

Aşağıda özetlenen 32 tamsayı kayıtları AArch64 mimarisi destekler:

|Yazmaç|Geçici?|Rol|
|-|-|-|
x0|Volatile|Parametre/baştan 1, sonuç kaydı kaydetme
x1-x7|Volatile|Parametre/baştan kayıt 2-8
x8-x15|Volatile|Karalama kayıtları
x16 x17|Volatile|İçi yordam çağrısı karalama kayıtları
x18|Geçici olmayan|Platform kaydı: çekirdek modunda KPCR için geçerli bir işlemci için; gösterir. kullanıcı modunda TEB için işaret eder.
x19-x28|Geçici olmayan|Karalama kayıtları
x29/fp|Geçici olmayan|Çerçeve işaretçisi
x30/lr|Geçici olmayan|Bağlantı kaydeder

Her kayıt, tam 64-bit bir değer (aracılığıyla x0 x30) veya (aracılığıyla w0-w30) 32-bit bir değer olarak erişilebilir. 32-bit işlemler sıfır-sonuçları en fazla 64 bit genişletin.

Parametre parametresi yazmaçların kullanımı hakkında ayrıntılar için bölümüne geçirme bakın.

AArch32, farklı bilgisayar SP dizinli kayıtları değildir ve nasıl bunlar erişilebilir bu nedenle sınırlı olduğunu unutmayın. Ayrıca hiçbir x31 olduğuna dikkat edin kaydedin (Bu, kodlama, özel amaçlar için kullanılır).

Çerçeve işaretçisini (x29) kullanımını hızlı yığın ETW ve diğer hizmetleri tarafından kullanılan uyum için gereklidir. Önceki {x29, 30 x} göstermelidir yığında çifti.

## <a name="floating-pointsimd-registers"></a>Kayan noktaya/SIMD kaydeder

AArch64 mimarisi de aşağıda özetlenmiştir 32 kayan noktaya/SIMD kayıtları destekler:

Yazmaç|Geçici?|Rol
|-|-|-|
v0|Volatile|Parametre/baştan 1, sonuç kaydı kaydetme
v1-v7|Volatile|2-8 parametre/baştan kaydeder
v8-v15|Geçici olmayan|Karalama kayıtları (yalnızca düşük 64 bit geçici olmayan unutmayın)
v16-v31|Volatile|Karalama kayıtları

Her kasa 16-bit bir değer (aracılığıyla h0 h31), veya 8-bit bir değer (aracılığıyla b0 b31) olarak (aracılığıyla s0-s31), 32-bit bir değer olarak (aracılığıyla d0-d31), 64-bit bir değer olarak tam 128-bit değeri (v0-v31 veya q0 q31) üzerinden erişilebilir. Erişimlerinin 128 bit daha küçük, yalnızca tam 128-bit kayıt daha düşük bit erişmek ve kalan bitleri aksi belirtilmediği sürece dokunmayın. (Burada daha küçük olan kayıtları üzerinde daha büyük olan kayıtları paketlenmiş AArch32, önemli ölçüde farklı olduğunu unutmayın.)

Ek olarak veri kayıtları, kayan nokta denetim kaydı (FPCR) içindeki çeşitli bit alanları üzerinde belirli gereksinimleri vardır:

Bits|Açıklama|Geçici?|Rol
|-|-|-|-|
26|AHP|Geçici olmayan|Alternatif yarı duyarlık denetimi
25|DN|Geçici olmayan|Varsayılan NaN modu denetimi
24|FZ|Geçici olmayan|Sıfır için temizleme modunu denetimi
23-22|RMode|Geçici olmayan|Yuvarlama modu denetimi
15,12-8|IDE/IXE/vb.|Geçici olmayan|Özel durum etkinleştir BITS tuzak, her zaman 0 olmalıdır

## <a name="system-registers"></a>Sistem kayıtları

AArch32 gibi gibi kullanılan/ayrılmış olan üç sistem tarafından denetlenen "İş parçacığı kimliği" kayıtlarını AArch64 belirtimi sağlar:

Yazmaç|Rol
|-|-|
TPIDR_EL0|Ayrılmış
TPIDRRO_EL0|Geçerli işlemci için CPU sayısını içerir
TPIDR_EL1|Geçerli İşlemci KPCR yapısına noktaları

## <a name="floating-point-exceptions"></a>Kayan nokta özel durumları

IEEE kayan nokta özel durumları için destek AArch64 sistemlerinde isteğe bağlıdır. Windows çekirdek, donanım kayan nokta özel durumları olan işlemci çeşitleri için sessizce özel durumlarını yakalayan ve örtük olarak bunları FPCR kayıt defterinde devre dışı bırakır. İşlemci çeşitler arasında normalleştirilmiş davranış budur (Aksi halde, kod geliştirilen bir platforma özel durum desteği kendisini desteği olan bir platform üzerinde çalışırken beklenmeyen bir özel durumları alma bulabilirsiniz olmadan).

## <a name="parameter-passing"></a>Parametre geçirme

Variadic olmayan işlevler için Windows ABI parametre geçirme için ARM tarafından belirtilen kuralları izler. Bu kurallar doğrudan yordamı çağırma standart moddan AArch64 mimarisi adlı çalışmasından:

### <a name="stage-a--initialization"></a>Aşama – A başlatma

Bu aşama, bağımsız değişkenleri işlenmesi işlemi başlamadan önce tam bir kez gerçekleştirilir.

1. Sonraki genel amaçlı kayıt numarası (NGRN) sıfır olarak ayarlanır.

1. Floating-point kayıt numarası (NSRN) ve sonraki SIMD sıfır olarak ayarlayın.

1. Sonraki yığın bağımsız değişken adresini (NSAA), geçerli yığın işaretçisi değerine (SP) ayarlanır.

### <a name="stage-b--pre-padding-and-extension-of-arguments"></a>Aşama – B öncesi doldurma ve bağımsız değişkenlerin uzantısı

Listedeki her bağımsız değişken için aşağıdaki listeden eşleşen ilk kural uygulanır. Değiştirilmemiş bağımsız değişkeni kullanılmıştır kural eşleşme.

1. Bağımsız değişken türü boyutu, statik olarak çağıran ve çağrılan tarafından belirlenemiyor bileşik bir tür ise, bağımsız değişken belleğe kopyalanır ve bağımsız değişken kopya işaretçisi tarafından değiştirilir. (C/C++'da böyle bir türü vardır ancak diğer dillerde veya dil uzantıları var).

1. Bir HFA veya bir HVA bağımsız değişken türü olan sonra bağımsız değişkeni kullanılır değiştirilmemiş.

1. Bağımsız değişken türü, 16 bayttan büyük bir bileşik türü ise, bağımsız değişkeni çağırıcı tarafından ayrılan belleğe kopyalanır ve bağımsız değişken bir işaretçi kopyasına değiştirilir.

1. Bağımsız değişken türü bir bileşik türü ise bağımsız değişkenin boyutu yukarı 8 baytlık en yakın katına yuvarlanır.

### <a name="stage-c--assignment-of-arguments-to-registers-and-stack"></a>Aşama – C kaydeder ve yığın bağımsız değişken ataması

Listedeki her bağımsız değişken için aşağıdaki kuralları bağımsız değişken ayrılan kadar sırayla uygulanır. Bağımsız değişken bir kasaya atandığında kayıttaki kullanılmayan tüm BITS değeri belirtilmeyen. Bağımsız değişken bir yığın yuvasına atandığında kullanılmayan tüm baytları değeri belirtilmeyen.

1. Bağımsız değişken yarı-tek, çift - veya dört duyarlıklı kayan nokta veya kısa vektör türü ve NSRN ise, 8'den küçük, bağımsız değişken için kayıt v [NSRN] ' en az önemli bitlerin ayrılan sonra. NSRN bir artırılır. Bağımsız değişken artık ayrıldı.

1. Bir HFA veya bir HVA bağımsız değişken olan ve yeterli ayrılmamış SIMD ve kayan nokta kayıtlarını (NSRN + 8 üyeleri ≤ sayısı) varsa, bağımsız değişken SIMD ve Floating-point kaydeder (bir kasa HFA veya HVA üyesi başına ile) ayrılır. NSRN kullanılan kayıtları sayısına göre artırılır. Bağımsız değişken artık ayrıldı.

1. Bağımsız değişken bir HFA veya bir HVA ise NSRN 8'e ayarlanır ve bağımsız değişkenin boyutu 8 bayt için en yakın katına yuvarlanır.

1. Bir HFA bir HVA bağımsız değişken ise dört duyarlıklı kayan nokta veya kısa vektör türü NSAA yuvarlatılmış sonra en fazla 8 ya da doğal hizalama bağımsız değişkenin türü daha büyük.

1. Yarı veya tek duyarlıklı kayan nokta türü bağımsız değişken ise bağımsız değişkenin boyutu 8 bayt için'e ayarlanır. Bağımsız değişken varmış gibi etkisi en az önemli bitlerin bir 64-bit kayıt ve belirtilmeyen değerlerle doldurulmuş kalan bitleri kopyalanmış.

1. Bağımsız değişken bir HFA ise ayarlanmış NSAA bellek için bir HVA, yarı-, tek, çift - veya dört duyarlıklı kayan nokta veya kısa vektör türü ve ardından bağımsız değişken kopyalanır. Bağımsız değişken boyutuna NSAA artırılır. Bağımsız değişken artık ayrıldı.

1. Bağımsız değişken bir Integral veya işaretçi türü ise bağımsız değişkenin boyutudur veya 8 bayt ve NGRN eşittir 8'den küçük, bağımsız değişkeni [NGRN] x en az önemli bitlerin kopyalanır. NGRN bir artırılır. Bağımsız değişken artık ayrıldı.

1. Bağımsız değişken bir hizalama 16 varsa NGRN yukarı doğru sonraki bile sayıya yuvarlanır.

1. Bağımsız değişken bağımsız değişken bir tam sayı türü, bağımsız değişkenin boyutu 16 eşittir ve NGRN 7'den az ise x kopyalanır [NGRN] ve [NGRN + 1] x. x [NGRN] alt adresli çift sözcük bağımsız değişkeni bellek temsilinin içeren. NGRN ikiye artırılır. Bağımsız değişken artık ayrıldı.

1. Bağımsız değişken bileşik bir türdür ve çift sözcükler bağımsız değişkenin boyutu NGRN eksi 8'den fazla değil durumunda art arda genel amaçlı kayıtlarına, bağımsız kopyalanan başlayan [NGRN] x. Bu kasalar bellekten ardışık kayıtları yüklenirken LDR yönergeleri (yazmaçların kullanılmayan tüm bölümlerinin içeriğini belirtilmeyen uygun bir diziyle bir çift sözcük hizalanmış adresinden içine yüklenmiş gibi sorgulamanıza bağımsız değişken geçirilir Bu standardına göre). NGRN kullanılan kayıtları sayısına göre artırılır. Bağımsız değişken artık ayrıldı.

1. NGRN 8'e ayarlanır.

1. NSAA tarafına yuvarlanır büyük 8 ya da doğal hizalama bağımsız değişkenin türü...

1. Bağımsız değişken türünün ise bağımsız değişken için ayarlanan NSAA bellek kopyalanır. Bağımsız değişken boyutuna NSAA artırılır. Bağımsız değişken artık ayrıldı.

1. Bağımsız değişkenin boyutu 8 bayttan daha az ise bağımsız değişkenin boyutu 8 bayt için'e ayarlanır. En az önemli bitlerin bir 64-bit kayıt ve belirtilmeyen değerlerle doldurulmuş kalan bitleri bağımsız kopyalanan gibi etkisidir.

1. Bağımsız değişken ayarlanmış NSAA bellek kopyalanır. Bağımsız değişken boyutuna NSAA artırılır. Bağımsız değişken artık ayrıldı.

### <a name="addendum-variadic-functions"></a>Eki: Değişen sayıda bağımsız değişken işlevleri

Değişken sayıda bağımsız değişkenler almayan işlevleri farklı daha yukarıda şu şekilde işlenir:

1. Tüm bileşik de işletmelere kabul edilir; HFAs veya HVAs özel işleme yok.

1. SIMD ve Floating-point kaydeder kullanılmaz.

Etkili bir şekilde bu aşağıdaki kurallar sanal yığın burada ilk 64 bayt yığın x0 x7 yüklenir ve kalan tüm yığın bağımsız değişkenleri normalde yerleştirilir bağımsız değişkenleri ayrılacak C.12–C.15 karşılık gelir.

## <a name="return-values"></a>Döndürülen değerler

Tamsayı değerleri x0 döndürülür. Kayan nokta değerleri d0/s0/v0 uygun olarak döndürülür.

Return kayıtları geçirilen değere göre için çağırana bir blok boyutu ve hizalama sonucu tutmak için yeterli bellek ayırmak. Bellek bloğu adresini ek bağımsız değişken olarak x8 POD türü veya x0 (veya $bu içinde x0 iletilmezse x1) işlevi POD olmayan türü için geçirilmesi. Çağrılan sonucu bellek bloğu herhangi bir noktada (değer x8 içinde depolanan değeri saklamak çağrılan, ancak POD harici, bu arabelleğin adresi gereksinimi de x0 Aranan tarafından iade edilmesi gerekir) alt yordam yürütülmesi sırasında değiştirebilir.

## <a name="stack"></a>Yığın

İleri tarafından ARM put ABI 16 bayt yığın her zaman hizalı kalmalıdır. AArch64 SP göreli yük ya da depolama gerçekleştirilir ve 16 baytlık SP hataları hizalı yığın hizalamasını oluşturan bir donanım özelliği içerir. Bu özellik her zaman Windows çalışır.

4 k ya da daha fazla değer yığın ayırma işlevleri son sayfa önce her bir sayfasında, sırayla dokunulan, böylece kod sağlama "üzerinden yığın genişletmek için Windows kullanan koruyucu sayfa leap" emin olmalısınız. Genelde bu yapılır `__chkstk` x8 16 bölü toplam yığın ayırma geçirir özel bir çağırma kuralı olan Yardımcısı.

## <a name="red-zone"></a>Kırmızı bölge

Geçerli yığın işaretçisi hemen altındaki 16 bayt alan, analiz tarafından kullanım için ayrılmış ve dinamik senaryoları düzeltme eki uygulama. Bu 2 kasalarda depolayan eklenecek dikkatli bir şekilde oluşturulan kod verir [sp, # 16] ve geçici olarak bunları rastgele amaçlar için kullanır. Windows çekirdek garanti eder, bir özel durum veya kesinti hem kullanıcı hem de çekirdek modunda yapılmazsa,'ın bu 16 bayt yazılmaz.

## <a name="kernel-stack"></a>Çekirdek yığını

Windows varsayılan çekirdek modu yığınında altı sayfaları (24 k) olur. Ek işlevlere büyük yığın arabelleği ile çekirdek modunda dikkat edin. İll-timed kesme, çok az boş alan oturum gelir ve yığın Panik hata denetimi oluşturun.

## <a name="stack-walking"></a>Yığın

Etkin çerçeve işaretçilerini ile derlenmiş kod içinde Windows ([/Oy-](reference/oy-frame-pointer-omission.md)) hızlı yığın walking etkinleştirmek için. Bu upshot x29 (dp) genel bir {fp, lr} olan zincirdeki sonraki bağlantısını işaret emin olan yığın ve dönüş adresi önceki çerçeve işaretçisi belirten çifti. Üçüncü taraf kodu çerçeve işaretçilerini yanı iyileştirilmiş profil oluşturma ve izleme için izin vermek için etkinleştirmeniz önerilir.

## <a name="exception-unwinding"></a>Özel durumu geriye doğru izleme

Geriye doğru izleme kodları kullanılarak Yardımlı sırasında özel durum işleme geriye doğru izleme. Geriye doğru izleme kodları şunlardır: azure'a yedekleme hazırlanırken bir işlevin prolog etkilerini geri gibi soyut bir şekilde prolog ve epilog işlemini açıklar yürütülebilir dosyanın sanal işlem bulunur bölümde depolanan bayt dizisi Arayanın yığın çerçevesinin. Geriye doğru izleme kodları hakkında daha fazla bilgi için bkz. [ARM64 özel durum işleme](arm64-exception-handling.md).

ARM EABI yararlanır geriye doğru izleme kodları, bir özel durumu geriye doğru izleme modeli de belirtir. Ancak, sunulan belirtimi, bilgisayar bir işlevin epilog ve prolog ortasında olduğu durumlarda işlemelidir Windows, geriye doğru izleme için yeterli değil.

Dinamik olarak oluşturulan kodu açıklanan dinamik işlevi tablolarla `RtlAddFunctionTable` ve İşlevler, oluşturulan kod içinde özel durum işleme katılabilmesi ilişkili.

## <a name="cycle-counter"></a>Döngü sayacı

Bir döngüyü desteklemek için gereken tüm ARMv8 CPU sayaç kaydolun. Herhangi bir özel durum düzeyinde (dahil olmak üzere kullanıcı modu) okunabilir olması için Windows için yapılandıran bir 64-bit kayıt budur. Özel PMCCNTR_EL0 erişilebilen kaydetme, derleme kodunda MSR opcode kullanarak veya `_ReadStatusReg` C/C++ kodundaki iç.

Döngü sayacı burada gerçek bir döngü sayacı, duvar saati ve böylece sayım sıklığı işlemci sıklığı değişir olduğuna dikkat edin. Döngü sayacı sıklığı bilmelisiniz düşünüyorsanız, döngü sayacı kullanmıyor. Bunun yerine, kendisi için kullanmanız gerektiğini duvar saati süresi ölçmek istediğiniz `QueryPerformanceCounter`.

## <a name="see-also"></a>Ayrıca bkz.

[Genel Visual C++ ARM Geçiş Sorunları](common-visual-cpp-arm-migration-issues.md)<br/>
[ARM64 özel durum işleme](arm64-exception-handling.md)
