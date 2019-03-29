---
title: ARM64 ABI kurallarına genel bakış
ms.date: 03/27/2019
ms.openlocfilehash: 4c0f89f97529d4cd70e1449c90b131d25d30f9ee
ms.sourcegitcommit: ac5c04b347e817eeece6e2c98e60236fc0e307a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58639452"
---
# <a name="overview-of-arm64-abi-conventions"></a>ARM64 ABI kurallarına genel bakış

ARM işlemcileri için çoğunlukla 64 bit modunda (ARMv8 veya üzeri mimarileri) üzerinde çalıştırma ve temel uygulama ikili arabiriminde (ABI) derlendiğinde Windows için ARM'ın standart AArch64 EABI izler. Bu makalede bazı önemli varsayımlar ve EABI içinde belgelenmiştir gelen değişiklikleri vurgular. 32-bit ABI hakkında daha fazla bilgi için bkz. [genel bakış, ARM ABI kurallarına](overview-of-arm-abi-conventions.md). Standart ARM EABI hakkında daha fazla bilgi için bkz: [uygulama ikili arabirimi (ABI) ARM mimarisi için](http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.subset.swdev.abi/index.html) (dış bağlantı).

## <a name="definitions"></a>Tanımlar

64-bit desteği sunulmasıyla birlikte, çeşitli koşulları ARM tanımlanır:

- **AArch32** – Thumb modu yürütme dahil olmak üzere ARM tarafından tanımlanan mimari (ISA) eski 32-bit yönerge ayarlayın.
- **AArch64** – yeni bir 64-bit yönerge ARM tarafından tanımlanan mimari (ISA) ayarlayın.
- **ARMv7** – belirtimi "7 oluşturma" ARM donanım, yalnızca AArch32 için destek içerir. Bu sürümü ARM donanım, Windows için ARM desteklenen ilk sürümdür.
- **ARMv8** – nesil"8" belirtimi ARM donanım, AArch32 hem AArch64 için destek içerir.

Windows, ayrıca bu terimler kullanılmaktadır:

- **ARM** – bazen WoA (Windows üzerinde ARM) olarak adlandırılır 32 bit ARM mimarisi (AArch32) ifade eder.
- **ARM32** – ARM, aynı yukarıdaki; anlaşılması için bu belgede kullanılan.
- **ARM64** – 64-bit ARM mimarisi (AArch64) ifade eder. WoA64 de yoktur.

Son olarak, veri türleri için söz konusu olduğunda aşağıdaki tanımları ARM başvurulur:

- **Kısa vektör** – SIMD, 8 veya 16 bayt gereken öğelerin oluşan bir vektörü doğrudan gösterilebilen bir veri türü. Bu, kendi boyutu 8 bayt ya da 16 bayt, burada her öğe 1, 2, 4 veya 8 bayt olabilir hizalanır.
- **(Homojen Floating-point toplama) HFA** – 2-4 kayan nokta üyeleri aynı, veri türüyle gezinen veya iki katına çıkar.
- **HVA (homojen kısa vektör toplama)** – 2 ila 4 özdeş kısa vektör üyesi olan bir veri türü.

## <a name="base-requirements"></a>Temel gereksinimleri

Bir ARMv8 üzerinde çalışıyor veya üzeri mimarisi her zaman Windows ARM64 sürümünü varsayar. Kayan nokta hem ve NEON desteği donanım bulunması varsayılmıştır.

ARMv8 belirtimi AArch32 uygulamaları için tam destek sağlar. Ancak, Windows ARM64 sürümünü mevcut ARM32 uygulamalar için destek planlı değil. (Diğer bir deyişle, planlanmamaktadır WOW64 için). Bu destek, gelecekte yeniden değerlendirmeye bağlı olmakla birlikte, geçerli çalışma varsayılır.

ARMv8 belirtimi AArch32 ve AArch64 için isteğe bağlı yeni şifreleme ve CRC yardımcı işlem kodlarını açıklar. Bunlar için destek, şu anda isteğe bağlı ancak önerilen değerdir. Bu işlem kodlarını yararlanmak için uygulamaları ilk önce çalışma zamanı denetimleri kendi bulunup bulunmadığını olmanız gerekir.

## <a name="endianness"></a>Endianness

Olarak ARM32 ile ARM64 Windows üzerinde Windows sürümünü endian modunda yürütülür. Endianness geçiş zorlamak daha kolay olacak şekilde AArch64, çekirdek modu desteği olmadan elde etmek zor olabilir.

## <a name="alignment"></a>Hizalama

ARM64'te çalışan Windows yanlış hizalanmış erişimleri şeffaf bir şekilde işlemek CPU donanım sağlar. AArch32 gelen bir gelişme Bu destek şimdi de (birden çok sözcük erişim dahil) tüm tamsayı erişir ve kayan nokta erişimler için çalışır.

Ancak, önbelleğe alınmamış (cihaz) bellek erişimlerinin yine de her zaman hizalanması gerekir. Kod büyük olasılıkla okuma veya önbelleğe alınmamış bellekten yanlış hizalanmış veri yazma, bu verilere sağlanan tüm erişimlerde hizalamak emin olmanız gerekir.

## <a name="integer-registers"></a>Tamsayı kaydeder

AArch64 mimarisi 32 tamsayı kayıtları destekler:

| Yazmaç | Geçici? | Rol |
| - | - | - |
| x0 | Volatile | Parametre/baştan 1, sonuç kaydı kaydetme |
| x1-x7 | Volatile | Parametre/baştan kayıt 2-8 |
| x8-x15 | Volatile | Karalama kayıtları |
| x16 x17 | Volatile | İçi yordam çağrısı karalama kayıtları |
| x18 | Geçici olmayan | Platform kaydı: çekirdek modunda KPCR için geçerli bir işlemci için; gösterir. kullanıcı modunda TEB için işaret eder. |
| x19-x28 | Geçici olmayan | Karalama kayıtları |
| x29/fp | Geçici olmayan | Çerçeve işaretçisi |
| x30/lr | Geçici olmayan | Bağlantı kaydeder |

Her kayıt, tam 64-bit bir değer (aracılığıyla x0 x30) veya (aracılığıyla w0-w30) 32-bit bir değer olarak erişilebilir. 32-bit işlemler sıfır-sonuçları en fazla 64 bit genişletin.

Parametre parametresi yazmaçların kullanımı hakkında ayrıntılar için bölümüne geçirme bakın.

AArch32, dizinli kayıtları program sayacının (PC) ve yığın işaretçisi (SP) değil. Nasıl bunlar erişilebilir içinde sınırlama getirilir. Ayrıca, hiçbir x31 olduğuna dikkat edin kaydedin. Kodlama, özel amaçlar için kullanılır.

Çerçeve işaretçisini (x29) hızlı yığın ETW ve diğer hizmetleri tarafından kullanılan walking ile uyumluluk için gereklidir. Önceki {x29, 30 x} göstermelidir yığında çifti.

## <a name="floating-pointsimd-registers"></a>Kayan noktaya/SIMD kaydeder

AArch64 mimarisi de aşağıda özetlenmiştir 32 kayan noktaya/SIMD kayıtları destekler:

| Yazmaç | Geçici? | Rol |
| - | - | - |
| v0 | Volatile | Parametre/baştan 1, sonuç kaydı kaydetme |
| v1-v7 | Volatile | 2-8 parametre/baştan kaydeder |
| v8-v15 | Geçici olmayan | Karalama (geçici olmayan düşük 64 bit yalnızca) kaydeder |
| v16-v31 | Volatile | Karalama kayıtları |

Her kasa (aracılığıyla v0-v31 veya q0 q31) tam 128-bit bir değer olarak erişilebilir. Bu (aracılığıyla d0-d31), 64-bit bir değer olarak (aracılığıyla s0-s31), 32-bit bir değer olarak 16-bit bir değer (aracılığıyla h0 h31) olarak veya 8-bit bir değer (b0 b31) aracılığıyla erişilebilir. 128 bit daha küçük erişimleri yalnızca tam 128-bit kayıt daha düşük bit erişin. Bunlar kalan bitleri aksi belirtilmediği sürece dokunmayın. (AArch64 AArch32, daha küçük olan kayıtları üzerinde daha büyük olan kayıtları burada paketlenmiş farklıdır.)

Kayan nokta denetim kaydı (FPCR) içindeki çeşitli bit alanları üzerinde belirli gereksinimleri vardır:

| Bits | Açıklama | Geçici? | Rol |
| - | - | - | - |
| 26 | AHP | Geçici olmayan | Alternatif yarı duyarlık denetimi. |
| 25 | DN | Geçici olmayan | Varsayılan NaN modu denetimi. |
| 24 | FZ | Geçici olmayan | Sıfır için temizleme modunu denetimi. |
| 23-22 | RMode | Geçici olmayan | Yuvarlama modu denetimi. |
| 15,12-8 | IDE/IXE/vb. | Geçici olmayan | Özel durum etkinleştir BITS tuzak, her zaman 0 olmalıdır. |

## <a name="system-registers"></a>Sistem kayıtları

AArch32 gibi üç sistem tarafından denetlenen "İş parçacığı kimliği" kayıtlarını AArch64 belirtimi sağlar:

| Yazmaç | Rol |
| - | - |
| TPIDR_EL0 | Ayrılmış. |
| TPIDRRO_EL0 | Geçerli işlemci için CPU sayısını içerir. |
| TPIDR_EL1 | Geçerli İşlemci KPCR yapısına işaret eder. |

## <a name="floating-point-exceptions"></a>Kayan nokta özel durumları

IEEE kayan nokta özel durumları için destek AArch64 sistemlerinde isteğe bağlıdır. Windows çekirdek, donanım kayan nokta özel durumları olan işlemci çeşitleri için sessizce özel durumlarını yakalayan ve örtük olarak bunları FPCR kayıt defterinde devre dışı bırakır. Bu yakalama işlemci çeşitler arasında normalleştirilmiş davranış sağlar. Aksi takdirde, özel durum desteği olmayan bir platform üzerinde geliştirilen kodu kendisini desteği olan bir platform üzerinde çalışırken beklenmeyen bir özel durumları alma bulabilirsiniz.

## <a name="parameter-passing"></a>Parametre geçirme

Variadic olmayan işlevler için Windows ABI parametre geçirme için ARM tarafından belirtilen kuralları izler. Bu kurallar doğrudan yordamı çağırma standart moddan AArch64 mimarisi adlı çalışmasından:

### <a name="stage-a--initialization"></a>Aşama – A başlatma

Bu aşama, bağımsız değişkenleri işlenmesi başlamadan önce tam bir kez gerçekleştirilir.

1. Sonraki genel amaçlı kayıt numarası (NGRN) sıfır olarak ayarlanır.

1. Floating-point kayıt numarası (NSRN) ve sonraki SIMD sıfır olarak ayarlayın.

1. Sonraki yığın bağımsız değişken adresini (NSAA), geçerli yığın işaretçisi değerine (SP) ayarlanır.

### <a name="stage-b--pre-padding-and-extension-of-arguments"></a>Aşama – B öncesi doldurma ve bağımsız değişkenlerin uzantısı

Listedeki her bağımsız değişken için aşağıdaki listeden eşleşen ilk kural uygulanır. Bağımsız değişken hiçbir kural eşleşme kullanıldığında değiştirilmemiş.

1. Bağımsız değişken türü boyutu, statik olarak çağıran ve çağrılan tarafından belirlenemiyor bileşik bir tür ise, bağımsız değişken belleğe kopyalanır ve bağımsız değişken kopya işaretçisi tarafından değiştirilir. (C/C++'da böyle bir türü vardır ancak diğer dillerde veya dil uzantıları var).

1. Bir HFA veya bir HVA bağımsız değişken türü olan sonra bağımsız değişkeni kullanılır değiştirilmemiş.

1. Bağımsız değişken türü, 16 bayttan büyük bir bileşik türü ise, ardından bağımsız değişkeni çağırıcı tarafından ayrılan belleğe kopyalanır ve bağımsız değişken kopya işaretçisi tarafından değiştirilir.

1. Bağımsız değişken türü bileşik bir tür ise, bağımsız değişkenin boyutu yukarı 8 baytlık en yakın katına yuvarlanır.

### <a name="stage-c--assignment-of-arguments-to-registers-and-stack"></a>Aşama – C kaydeder ve yığın bağımsız değişken ataması

Bağımsız değişken ayrılan kadar listedeki her bağımsız değişken için aşağıdaki kurallar sırayla uygulanır. Bağımsız değişken bir kasaya atandığında, kayıttaki kullanılmayan tüm BITS değeri belirtilmeyen. Bağımsız değişken bir yığın yuvasına atanırsa, kullanılmayan tüm baytları değeri belirtilmeyen.

1. Bağımsız değişken yarı - olan tek çift - veya dört duyarlıklı kayan nokta veya kısa vektör türü ve NSRN 8'den küçük olduğunu ve ardından bağımsız değişken kaydının v en az önemli bitlerin için ayrılan\[NSRN]. NSRN bir artırılır. Bağımsız değişken artık ayrıldı.

1. Bir HFA veya bir HVA bağımsız değişken olan ve yeterli ayrılmamış SIMD ve kayan nokta kayıtlarını (NSRN + 8 üyeleri ≤ sayısı), bağımsız değişken SIMD ve Floating-point kaydeder, HFA veya HVA üyesi başına bir kasa için ayrılır. NSRN kullanılan kayıtları sayısına göre artırılır. Bağımsız değişken artık ayrıldı.

1. Bir HFA veya bir HVA bağımsız değişken ise, ardından NSRN 8'e ayarlanır ve bağımsız değişkenin boyutu 8 bayt için en yakın katına yuvarlanır.

1. Bir HFA bir HVA, dört duyarlıklı kayan nokta veya kısa vektör türü bağımsız değişken olan sonra NSAA tarafına yuvarlanır bağımsız değişkenin türünün doğal hizalama 8 veya daha büyük.

1. Yarı veya tek duyarlıklı kayan nokta türü bağımsız değişken ise bağımsız değişkenin boyutu 8 bayt için'e ayarlanır. Bağımsız değişken varmış gibi etkili bir 64-bit kayıt için en az önemli bitlerini kopyalandığından ve kalan bitleri belirtilmeyen değerlerle doldurulur.

1. Bağımsız değişken bir HFA ise ayarlanmış NSAA bellek için bir HVA, yarı-, tek, çift- veya dört duyarlıklı kayan nokta veya kısa vektör türü ve ardından bağımsız değişken kopyalanır. Bağımsız değişken boyutuna NSAA artırılır. Bağımsız değişken artık ayrıldı.

1. Bir Integral veya işaretçi türü olmayan bağımsız değişken, bağımsız değişkenin boyutu 8 bayt veya daha az ve NGRN 8'den küçük, bağımsız değişken x en az önemli bitlerin kopyalanır\[NGRN]. NGRN bir artırılır. Bağımsız değişken artık ayrıldı.

1. Bağımsız değişken bir hizalama 16 varsa, ardından NGRN sonraki bile sayıya yuvarlanır.

1. Bağımsız değişken bağımsız değişken bir tamsayı türüdür, bağımsız değişkenin boyutu 16 eşittir ve NGRN 7'den az olduğundan, x kopyalanır\[NGRN] ve x\[NGRN + 1]. x\[NGRN] alt adresli çift sözcük bağımsız değişkeni bellek temsilinin içeren. NGRN ikiye artırılır. Bağımsız değişken artık ayrıldı.

1. Bileşik bir tür olmayan bağımsız değişken ve bağımsız değişkenin çift sözcükler boyutu en fazla 8 NGRN eksi olduğundan durumunda bağımsız değişken x başlayan ardışık genel amaçlı kayıtları kopyalanır\[NGRN]. Bu ardışık kayıtları bellekten yük LDR yönergeleri uygun bir diziyle çift sözcük hizalanmış bir adresi olan kayıtları içine yüklenmiş gibi sorgulamanıza bağımsız değişken geçirildi. Kullanılmayan tüm bölümler yazmaçların içeriğini bu standardı tarafından belirtilmemiş. NGRN kullanılan kayıtları sayısına göre artırılır. Bağımsız değişken artık ayrıldı.

1. NGRN 8'e ayarlanır.

1. NSAA tarafına yuvarlanır bağımsız değişkenin türünün doğal hizalama 8 veya daha büyük.

1. Bağımsız değişken türünün ise bağımsız değişkeni ayarlanmış NSAA bellek kopyalanır. Bağımsız değişken boyutuna NSAA artırılır. Bağımsız değişken artık ayrıldı.

1. Bağımsız değişkenin boyutu 8 bayttan daha az ise, bağımsız değişkenin boyutu 8 bayt için'e ayarlanır. Bir 64-bit kayıt için en az önemli bitlerini bağımsız kopyalanan ve kalan bitleri belirtilmeyen değerlerle doldurulmuş gibi etkisidir.

1. Bağımsız değişken ayarlanmış NSAA bellek kopyalanır. Bağımsız değişken boyutuna NSAA artırılır. Bağımsız değişken artık ayrıldı.

### <a name="addendum-variadic-functions"></a>Eki: Değişen sayıda bağımsız değişken işlevleri

Değişken sayıda bağımsız değişkenler almayan işlevleri farklı daha yukarıda şu şekilde işlenir:

1. Tüm bileşik de işletmelere kabul edilir; HFAs veya HVAs özel işleme yok.

1. SIMD ve Floating-point kaydeder kullanılmaz.

Etkili bir şekilde, aşağıdaki kurallar sanal yığın burada ilk 64 bayt yığın x0 x7 yüklenir ve kalan tüm yığın bağımsız değişkenleri normalde yerleştirilir bağımsız değişkenleri ayrılacak C.12–C.15 aynıdır.

## <a name="return-values"></a>Döndürülen değerler

Tamsayı değerleri x0 döndürülür.

Kayan nokta değerleri d0/s0/v0 uygun olarak döndürülür.

Değeri tarafından döndürülen türleri belirli özellikleri olup olmamasına bağlı olarak farklı şekilde ele alınır. Tüm bu özelliklerin türleri

- Bunlar *toplama* C ++ 14 standart tanımına göre diğer bir deyişle, hiçbir kullanıcı tarafından sağlanan bir oluşturucu, hiçbir özel veya korumalı statik olmayan veri üyesi, temel olmayan sınıflar ve sanal işlev yok, sahip oldukları ve
- bir basit kopya atama işleci, sahip oldukları ve
- Önemsiz bir yok edici sahip oldukları

Aşağıdaki dönüş stili kullanın:

- Türleri 8 bayt veya daha az x0 döndürülür.
- Türleri 16 bayt veya daha az x0 ve x1, x0 içeren alt sıra 8 bayt ile döndürülür.
- 16 bayttan büyük türleri için çağırana bir blok boyutu ve hizalama sonucu tutmak için yeterli bellek ayırmak. Bellek bloğu adresini, x8 işlevi için ek bağımsız değişken olarak geçirilen. Çağrılan alt yordam yürütme sırasında herhangi bir noktada sonucu bellek bloğu değiştirebilir. Aranan x8 içinde depolanan değeri korumak için gerekli değildir.

Diğer tüm türleri bu kuralı kullanın:

- Arayan, bir blok boyutu ve hizalama sonucu tutmak için yeterli bellek ayırmak. $Bu içinde x0 geçirilirse bellek bloğu adresini x0 ya da x1 işlevi için ek bağımsız değişken olarak geçirilen. Çağrılan alt yordam yürütme sırasında herhangi bir noktada sonucu bellek bloğu değiştirebilir. Çağrılan içinde x0 bellek bloğu adresini döndürür.

## <a name="stack"></a>Yığın

İleri tarafından ARM put ABI 16 bayt yığın her zaman hizalı kalmalıdır. AArch64 SP 16 bayt hizalı değil ve bir SP göreli yük veya depolama yapılır her yığın hizalama hatası oluşturur bir donanım özelliği içerir. Bu özellik her zaman Windows çalışır.

4 k ya da daha fazla değer yığın ayırma işlevleri her sayfanın son sayfa önce sırayla dokunulan emin olmanız gerekir. Bu eylem, kod yok "üzerinden yığın genişletmek için Windows kullanan koruyucu sayfa leap" sağlar. Genellikle temas yapabilirsiniz `__chkstk` x15 16 bölü toplam yığın ayırma geçirir özel bir çağırma kuralı olan Yardımcısı.

## <a name="red-zone"></a>Kırmızı bölge

Geçerli yığın işaretçisi hemen altındaki 16 baytlık alan analiz tarafından kullanım için ayrılmış ve dinamik senaryoları düzeltme eki uygulama. Bu alan izin veren iki kasalarda depolayan eklenecek dikkatli bir şekilde oluşturulan kod [sp, # 16] ve geçici olarak bunları rastgele amaçlar için kullanır. Windows çekirdek, bir özel durum veya kesinti hem kullanıcı hem de çekirdek modunda yapılmazsa, bu 16 baytın üzerine olmayan garanti eder.

## <a name="kernel-stack"></a>Çekirdek yığını

Windows varsayılan çekirdek modu yığınında altı sayfaları (24 k) olur. Ek işlevlere büyük yığın arabelleği ile çekirdek modunda dikkat edin. İll-timed kesme, az boş alan oturum gelir ve yığın Panik hata denetimi oluşturun.

## <a name="stack-walking"></a>Yığın

Etkin çerçeve işaretçilerini ile derlenmiş kod içinde Windows ([/Oy-](reference/oy-frame-pointer-omission.md)) hızlı yığın walking etkinleştirmek için. Genellikle, x29 (dp) işaret eden bir {fp, lr} olan zincirdeki sonraki bağlantısını için işaretçiyi yığına ve dönüş adresi önceki çerçeveye belirten çifti. Üçüncü taraf kodu iyileştirilmiş profil oluşturma ve izleme için izin vermek için de çerçeve işaretçilerini etkinleştirmek için önerilir.

## <a name="exception-unwinding"></a>Özel durumu geriye doğru izleme

Geriye doğru izleme kodları kullanılarak Yardımlı sırasında özel durum işleme geriye doğru izleme. Geriye doğru izleme kodları şunlardır: yürütülebilir dosyanın sanal işlem bulunur bölümde depolanan bayt dizisi. Arayanın yığın çerçevesinin yedeklemenin hazırlığında işlevin prolog etkilerini geri alınabilir, soyut bir şekilde prolog ve epilog işlemini açıklar. Geriye doğru izleme kodları hakkında daha fazla bilgi için bkz. [ARM64 özel durum işleme](arm64-exception-handling.md).

ARM EABI de kullanan bir özel durumu geriye doğru izleme modeli geriye doğru izleme kodları belirtir. Ancak, sunulan belirtimi form veya Windows PC işlevi prolog veya kapanış ortasında olduğu durumlarla gerekir, geriye doğru izleme için yeterli değil.

Dinamik olarak oluşturulan kodu açıklanan dinamik işlevi tablolarla `RtlAddFunctionTable` ve İşlevler, oluşturulan kod içinde özel durum işleme katılabilmesi ilişkili.

## <a name="cycle-counter"></a>Döngü sayacı

Tüm ARMv8 CPU'ların bir döngü sayacı desteklemek için gerekli olan kullanıcı modu da dahil olmak üzere, hiçbir özel durum düzeyinde okunabilir olması için Windows için yapılandıran bir 64-bit kayıt kaydedin. Özel PMCCNTR_EL0 erişilebilen kaydetme, derleme kodunda MSR opcode kullanarak veya `_ReadStatusReg` C/C++ kodundaki iç.

Döngü burada duvar saati bir doğru döngü sayacı sayacıdır. Sayım sıklığı işlemci sıklığı değişir. Döngü sayacı sıklığı bilmelisiniz düşünüyorsanız, döngü sayacını kullanarak olmamalıdır. Bunun yerine, kendisi için kullanmanız gerektiğini duvar saati süresi ölçmek istediğiniz `QueryPerformanceCounter`.

## <a name="see-also"></a>Ayrıca bkz.

[Genel Visual C++ ARM Geçiş Sorunları](common-visual-cpp-arm-migration-issues.md)<br/>
[ARM64 özel durum işleme](arm64-exception-handling.md)
