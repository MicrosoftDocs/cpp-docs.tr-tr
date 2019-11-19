---
title: ARM64 ABI kurallarına genel bakış
ms.date: 03/27/2019
ms.openlocfilehash: 3a3df475b8f814fcecaf2e67a0a62c7267a0de30
ms.sourcegitcommit: e805200eaef4fe7a65a00051bbd305273af94fe7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2019
ms.locfileid: "74163226"
---
# <a name="overview-of-arm64-abi-conventions"></a>ARM64 ABI kurallarına genel bakış

64 bit modundaki (ARMv8 veya sonraki mimarilerin) ARM işlemcilerde derleme ve çalıştırma sırasında Windows için temel uygulama ikili arabirimi (ABı), en çok bölüm için ARM 'nin standart AArch64 EABı ' ı izler. Bu makalede, EABI 'de belgelenen bazı önemli varsayımlar ve değişiklikler vurgulanmaktadır. 32-bit ABı hakkında daha fazla bilgi için bkz. [ARM ABI kurallarına genel bakış](overview-of-arm-abi-conventions.md). Standart ARM EABI hakkında daha fazla bilgi için bkz. ARM mimarisi (dış bağlantı) [Için uygulama Ikili arabirimi (ABI)](http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.subset.swdev.abi/index.html) .

## <a name="definitions"></a>Tanımlar

64 bitlik destek tanıtımı sayesinde ARM birkaç terim tanımladı:

- **AArch32** – Thumb modu yürütme dahil olmak üzere ARM tarafından tanımlanan eski 32 bit yönerge kümesi mımarısı (ISA).
- **AArch64** – ARM tarafından tanımlanan yeni 64-bit yönerge kümesi mımarısı (ISA).
- **ARMv7** : yalnızca AArch32 desteğini içeren "7th oluşturma" ARM donanımının belirtimi. ARM donanımının bu sürümü, ARM 'nin desteklenme için ilk sürüm Windows sürümüdür.
- **ARMv8** : hem AArch32 hem de AArch64 desteğini içeren "8th oluşturma" ARM donanımının belirtimi.

Windows aşağıdaki terimleri de kullanır:

- **ARM** : bazen WOA (ARM üzerinde Windows) olarak adlandırılan 32 bitlik ARM mimarisine (AArch32) başvurur.
- **ARM32** – yukarıdaki ARM ile aynı; Bu belgede açıklık için kullanılır.
- **ARM64** – 64-bit ARM mimarisine (AArch64) başvurur. WoA64 gibi bir şey yoktur.

Son olarak, veri türlerine başvururken, ARM 'deki aşağıdaki tanımlara başvurulur:

- **Kısa vektör** : bir veri türü doğrudan Simd 'de, 8 baytlık bir vektör veya 16 bayt/öğe olarak gösterilebilir. Her bir öğenin 1, 2, 4 veya 8 bayt olabilecek boyutu 8 bayt veya 16 bayt olarak hizalanır.
- **HFA (homojen nokta toplama)** – 2 ile 4 özdeş kayan nokta üyelerine sahip bir veri türü, float veya Double.
- **HVA (homojen kısa vektör toplama)** – 2 ile 4 özdeş kısa vektör üyesine sahip bir veri türüdür.

## <a name="base-requirements"></a>Temel gereksinimler

Windows 'un ARM64 sürümü, her zaman bir ARMv8 veya sonraki bir mimaride çalıştığını doğurur. Kayan nokta ve NEON desteğinin her ikisi de donanımda mevcut olacak şekilde adlandırılır.

ARMv8 belirtimi, hem AArch32 hem de AArch64 için yeni isteğe bağlı şifreleme ve CRC Yardımcısı işlem kodları tanımlar. Bu destek şu anda isteğe bağlıdır, ancak önerilir. Bu OpCodes avantajlarından yararlanmak için, uygulamaların ilk olarak kendi mevcut çalışma zamanı denetimleri yapması gerekir.

## <a name="endianness"></a>Endian

Windows 'un ARM32 sürümünde olduğu gibi ARM64 Windows, küçük endian modunda yürütülür. AArch64 içinde çekirdek modu desteği olmadan elde etmek zordur; bu nedenle zorlamak daha kolay olur.

## <a name="alignment"></a>Hizalama

ARM64 üzerinde çalışan Windows, CPU donanımının hatalı hizalanmış erişimleri saydam şekilde işlemesini sağlar. AArch32 ' den itibaren, bu destek artık tüm tamsayı erişimleri (çok sözcüklü erişimler dahil) ve kayan nokta erişimleri için de geçerlidir.

Ancak, önbelleğe alınmamış (cihaz) belleğe erişim yine de her zaman hizalı olmalıdır. Kod büyük olasılıkla önbelleğe alınmamış bellekten hatalı hizalanmış veriler okuyabilir veya yazamaz, tüm erişimleri hizaladığınızdan emin olmalıdır.

Yereller için varsayılan düzen hizalaması:

| Bayt cinsinden boyut | Bayt cinsinden hizalama |
| - | - |
| 1\. | 1\. |
| 2 | 2 |
| 3, 4 | 4 |
| > 4 | 8 |

Genel ve statikler için varsayılan düzen hizalaması:

| Bayt cinsinden boyut | Bayt cinsinden hizalama |
| - | - |
| 1\. | 1\. |
| 2 - 7 | 4 |
| 8 - 63 | 8 |
| > = 64 | 16 |

## <a name="integer-registers"></a>Tamsayı Yazmaçları

AArch64 mimarisi 32 tamsayı yazmaçlarını destekler:

| Yazmaç | Katılımcıdan? | Rol |
| - | - | - |
| x0 | Katılımcıdan | Parametre/karalama kayıt 1, sonuç kaydı |
| x1-x7 | Katılımcıdan | Parametre/karalama kaydı 2-8 |
| x8-X15 | Katılımcıdan | Karalama Yazmaçları |
| X16-x17 | Katılımcıdan | Yordam içi çağrı kayıt Yazmaçları |
| x18 | Geçici olmayan | Platform kaydı: çekirdek modunda, geçerli işlemci için KPCR 'ye işaret eder; Kullanıcı modunda, TEB 'ye işaret eder |
| x19-x28 | Geçici olmayan | Karalama Yazmaçları |
| x29/FP | Geçici olmayan | Çerçeve işaretçisi |
| x30/LR | Geçici olmayan | Bağlantı Yazmaçları |

Her kayda tam 64 bitlik bir değer (x0-x30 aracılığıyla) veya 32 bitlik bir değer (W0-W30 aracılığıyla) olarak erişilebilir. 32 bitlik işlemler sıfır-sonuçları en fazla 64 bit olacak şekilde genişletin.

Parametre yazmaçlarının kullanımıyla ilgili ayrıntılar için parametre geçirme bölümüne bakın.

AArch32 aksine, program sayacı (PC) ve yığın işaretçisi (SP), dizinli Yazmaçları değildir. Bunlara nasıl erişilebileceği kısıtlıdır. Ayrıca, x31 kaydı olmadığını unutmayın. Bu kodlama özel amaçlar için kullanılır.

Çerçeve işaretçisi (x29), ETW ve diğer hizmetler tarafından kullanılan hızlı yığın yürüyüle uyumluluk için gereklidir. Yığındaki önceki {x29, x30} çiftiyle işaret etmelidir.

## <a name="floating-pointsimd-registers"></a>Kayan nokta/SıMD Yazmaçları

AArch64 mimarisi, aşağıda özetlenen 32 kayan nokta/SıMD kayıtlarını da destekler:

| Yazmaç | Katılımcıdan? | Rol |
| - | - | - |
| v0 | Katılımcıdan | Parametre/karalama kayıt 1, sonuç kaydı |
| V1-v7 | Katılımcıdan | Parametre/karalama Yazmaçları 2-8 |
| V8-v15 | Geçici olmayan | Karalama Yazmaçları (yalnızca düşük 64 bitleri geçici olmayan) |
| v16-v31 | Katılımcıdan | Karalama Yazmaçları |

Her kayda tam 128 bitlik bir değer (v0-V31 veya Q0-Q31 aracılığıyla) olarak erişilebilir. 64 bitlik bir değer (D0-d31 aracılığıyla), 32 bitlik bir değer (S0-S31 aracılığıyla) olarak, 16 bitlik bir değer (H0-H31 aracılığıyla) veya 8 bitlik bir değer (B0-B31 aracılığıyla) olarak erişilebilir. 128 bitten küçük erişimler yalnızca tam 128 bit kayıt 'nin düşük Bitlerine erişir. Aksi belirtilmediği takdirde, kalan bitleri dokunmaz. (AArch64, küçük yazmaçların daha büyük yazmaçların üzerine paketlendikleri AArch32 'dan farklıdır.)

Kayan nokta denetim kaydı (fpcr), içindeki çeşitli bit alanları üzerinde belirli gereksinimlere sahiptir:

| Bits | Açıklama | Katılımcıdan? | Rol |
| - | - | - | - |
| 26 | AHP | Geçici olmayan | Alternatif yarı duyarlık denetimi. |
| 25 | DEĞERI | Geçici olmayan | Varsayılan NaN modu denetimi. |
| 24 | FZ | Geçici olmayan | Sıfır moddan sıfıra denetim. |
| 23-22 | RMode | Geçici olmayan | Yuvarlama modu denetimi. |
| 15, 12-8 | IDE/ıXE/etc | Geçici olmayan | Özel durum yakalama bitlerini etkinleştir, her zaman 0 olmalıdır. |

## <a name="system-registers"></a>Sistem kayıtları

AArch32 gibi, AArch64 belirtimi, sistem tarafından denetlenen üç "iş parçacığı KIMLIĞI" kaydı sağlar:

| Yazmaç | Rol |
| - | - |
| TPIDR_EL0 | Ayrılamadı. |
| TPIDRRO_EL0 | Geçerli işlemcinin CPU numarasını içerir. |
| TPIDR_EL1 | Geçerli işlemci için KPCR yapısına işaret eder. |

## <a name="floating-point-exceptions"></a>Kayan nokta özel durumları

IEEE kayan nokta özel durumları için destek, AArch64 sistemlerinde isteğe bağlıdır. Donanım kayan nokta özel durumları olan işlemci çeşitleri için, Windows çekirdeği özel durumları sessizce yakalar ve FPCR kaydındaki bunları örtülü olarak devre dışı bırakır. Bu tuzak, işlemci çeşitleri arasında normalleştirilmiş davranışı sağlar. Aksi takdirde, özel durum desteği olmayan bir platformda geliştirilen kod, destek içeren bir platformda çalışırken beklenmedik özel durumlar bulmayabilir.

## <a name="parameter-passing"></a>Parametre geçirme

Bağımsız değişken olmayan bağımsız işlevlerde, Windows ABı, parametre geçirme için ARM tarafından belirtilen kurallara uyar. Bu kurallar, AArch64 mimarisi için doğrudan yordam çağrısı Standbundan alınmıştır:

### <a name="stage-a--initialization"></a>Aşama A – başlatma

Bu aşama, bağımsız değişkenlerin işlenmesi başlamadan önce tam olarak bir kez gerçekleştirilir.

1. Sonraki genel amaçlı kayıt numarası (NGRN) sıfır olarak ayarlanır.

1. Sonraki SıMD ve kayan nokta kayıt numarası (NSRN) sıfır olarak ayarlanır.

1. Sonraki yığılmış bağımsız değişken adresi (NSAA) geçerli yığın işaretçisi değeri (SP) olarak ayarlanır.

### <a name="stage-b--pre-padding-and-extension-of-arguments"></a>Aşama B – bağımsız değişkenlerin ön doldurma ve uzantısı

Listedeki her bağımsız değişken için, aşağıdaki listeden ilk eşleştirme kuralı uygulanır. Hiçbir kural eşleşmez, bağımsız değişken değiştirilmemiş olarak kullanılır.

1. Bağımsız değişken türü, boyutu hem çağıran hem de aranan tarafından statik olarak belirlenemediği bir bileşik tür ise, bağımsız değişken belleğe kopyalanır ve bağımsız değişken kopyaya bir işaretçi ile değiştirilmiştir. (C/C++ içinde böyle bir tür yoktur, ancak bunlar diğer dillerde veya dil uzantılarında bulunur).

1. Bağımsız değişken türü bir HFA veya bir HVA ise, bağımsız değişken değiştirilmemiş olarak kullanılır.

1. Bağımsız değişken türü 16 bayttan daha büyük bir bileşik tür ise, bağımsız değişken çağıran tarafından ayrılan belleğe kopyalanır ve bağımsız değişken, kopyaya bir işaretçi ile değiştirilmiştir.

1. Bağımsız değişken türü bir bileşik tür ise, bağımsız değişkenin boyutu 8 baytın en yakın katına yuvarlanır.

### <a name="stage-c--assignment-of-arguments-to-registers-and-stack"></a>Aşama C – bağımsız değişkenlerin yazmaçlara ve yığına atanması

Listedeki her bağımsız değişken için, bağımsız değişken ayrılana kadar aşağıdaki kurallar sırayla uygulanır. Bir kaydına bir bağımsız değişken atandığında, kayıttaki kullanılmayan bitlerin değeri belirtilmemiş olur. Bir bağımsız değişken bir yığın yuvasına atanırsa, kullanılmamış doldurma baytlarının değeri belirtilmemiş olur.

1. Bağımsız değişken bir yarı, tek, çift veya dört duyarlıklı kayan nokta veya kısa vektör türüdür ve NSRN 8 ' den küçükse, bağımsız değişken, YAZMAÇ v\[NSRN] en az önemli bitlerini tahsis edilir. NSRN, bir artırılır. Bağımsız değişken artık ayrıldı.

1. Bağımsız değişken bir HFA veya bir HVA ise ve yeterli ayrılmamış SıMD ve kayan nokta Yazmaçları varsa (NSRN + üye sayısı ≤ 8), bağımsız değişken, HFA veya HVA üyesi başına tek bir kayıt olmak üzere SıMD ve kayan nokta Yazmaçları için ayrılır. NSRN, kullanılan kayıt sayısı kadar artırılır. Bağımsız değişken artık ayrıldı.

1. Bağımsız değişken bir HFA veya bir HVA ise, NSRN 8 olarak ayarlanır ve bağımsız değişkenin boyutu 8 baytın en yakın katına yuvarlanır.

1. Bağımsız değişken bir HFA, bir HVA, dört duyarlıklı kayan nokta veya kısa vektör türü ise, NSAA, 8 ' in üzerine veya bağımsız değişkenin türünün doğal hizalamasına yuvarlanır.

1. Bağımsız değişken bir yarı veya tek duyarlıklı kayan nokta türünde ise, bağımsız değişkenin boyutu 8 bayt olarak ayarlanır. Bu, bağımsız değişken 64 bitlik bir kaydın en az önemli bitine kopyalanmış ve kalan bitlerin belirtilmemiş değerlerle doldurulmuş olduğu gibidir.

1. Bağımsız değişken bir HFA, bir HVA, bir yarı, tek, çift veya dört duyarlıklı kayan noktalı veya kısa vektör türünde ise, bağımsız değişken ayarlanmış NSAA 'da belleğe kopyalanır. NSAA, bağımsız değişkenin boyutuyla artırılır. Bağımsız değişken artık ayrıldı.

1. Bağımsız değişken bir Integral veya Işaretçi türü ise, bağımsız değişkenin boyutu 8 bayttan küçük veya buna eşit ve NGRN 8 ' den küçükse, bağımsız değişken x\[NGRN] içindeki en az önemli olan bit sayısına kopyalanır. NGRN, bir artırılır. Bağımsız değişken artık ayrıldı.

1. Bağımsız değişkenin 16 hizalaması varsa, NGRN bir sonraki çift sayıya yuvarlanır.

1. Bağımsız değişken bir Integral türüdür, bağımsız değişkenin boyutu 16 ' dır ve NGRN 7 ' den küçükse, bağımsız değişken x\[NGRN] ve x\[NGRN + 1] ' e kopyalanır. x\[NGRN], bağımsız değişkenin bellek gösteriminin daha düşük olan bir çift kelimesine sahip olacaktır. NGRN iki ile artırılır. Bağımsız değişken artık ayrıldı.

1. Bağımsız değişken bir bileşik türdür ve bağımsız değişkenin çift sözcüklerdeki boyutu 8 eksi NGRN 'den fazla değilse, bağımsız değişken x\[NGRN] ile başlayarak ardışık genel amaçlı kayıtlara kopyalanır. Bağımsız değişken, bellekten ardışık kayıtları yükleyen uygun bir LDR yönergeleri dizisiyle birlikte çift sözcüklü hizalanmış bir adresten kayıtlara yüklenmiş gibi geçirilir. Yazmaçların kullanılmayan bölümlerinin içerikleri bu standart tarafından belirlenmeyen bir tür. NGRN, kullanılan kayıt sayısına göre artırılır. Bağımsız değişken artık ayrıldı.

1. NGRN, 8 olarak ayarlanır.

1. NSAA, 8 ' den büyük veya bağımsız değişkenin türünün doğal hizalamasına yuvarlanır.

1. Bağımsız değişken bir bileşik tür ise, bağımsız değişken ayarlanmış NSAA 'da belleğe kopyalanır. NSAA, bağımsız değişkenin boyutuyla artırılır. Bağımsız değişken artık ayrıldı.

1. Bağımsız değişkenin boyutu 8 bayttan küçükse, bağımsız değişkenin boyutu 8 bayt olarak ayarlanır. Bu efekt, bağımsız değişkenin 64 bitlik bir yazmacın en az önemli bitlerini kopyalanmış olması ve kalan bitlerin belirtilmemiş değerlerle doldurulmasıdır.

1. Bağımsız değişken, ayarlanan NSAA 'da belleğe kopyalanır. NSAA, bağımsız değişkenin boyutuyla artırılır. Bağımsız değişken artık ayrıldı.

### <a name="addendum-variadic-functions"></a>Eki: değişken bağımsız değişken işlevleri

Değişken sayıda bağımsız değişken alan işlevler, aşağıdaki şekilde yukarıdan farklı şekilde işlenir:

1. Tüm Birleşik siteler benzer şekilde işlenir; HFAs veya HVAs için özel bir işleme yoktur.

1. SıMD ve kayan nokta Yazmaçları kullanılmıyor.

Etkin olarak, bir sanal yığına bağımsız değişkenler ayırmak için C. 12 – C. 15 kurallarla aynı olur. Bu, yığının ilk 64 baytlarının x0-x7 ' ye yüklendiği ve kalan yığın bağımsız değişkenlerinin normal şekilde yerleştirildiği yerdir.

## <a name="return-values"></a>Döndürülen değerler

Integral değerleri x0 içinde döndürülür.

Kayan nokta değerleri, uygun şekilde S0, D0 veya V0 ' de döndürülür.

HFA ve HVA değerleri, uygun şekilde S0-S3, D0-D3 veya v0-v3 ' de döndürülür.

Değere göre döndürülen türler, belirli özelliklere sahip olup olmadığına bağlı olarak farklı şekilde işlenir. Bu özelliklere sahip olan türler,

- Bunlar, C++ 14 standart tanımına göre *toplamakta* , diğer bir deyişle, hiç Kullanıcı tarafından sağlanmayan bir Oluşturucu yoktur, özel veya korumalı olmayan veri üyeleri yoktur, temel sınıf içermez ve sanal işlevler yoktur ve
- Bunlar, önemsiz bir kopya atama işlecine sahiptir ve
- Bu, basit bir yıkıcıya sahiptir,

aşağıdaki dönüş stilini kullanın:

- X0 içinde 8 bayttan küçük veya buna eşit türler döndürülür.
- 16 bayttan küçük veya buna eşit türler, x0 ve x1 içinde, alt sıra 8 bayt içeren x0 ile döndürülür.
- 16 bayttan daha büyük türler için, çağıran, sonucu tutmak için yeterli boyutta ve hizalamadaki bir bellek bloğu ayıracaktır. Bellek bloğunun adresi, x8 içindeki işleve ek bir bağımsız değişken olarak geçirilir. Çağrılan, alt yordamın yürütülmesi sırasında herhangi bir noktada sonuç bellek bloğunu değiştirebilir. Aranan, x8 ' de depolanan değeri korumak için gerekli değildir.

Diğer tüm türler bu kuralı kullanır:

- Çağıran, sonucu tutmak için yeterli boyutta ve hizalamadaki bir bellek bloğu ayıracaktır. Bellek bloğunun adresi, x0 içindeki işleve ek bir bağımsız değişken olarak geçirilir veya x0 içinde $this geçirilirse x1. Çağrılan, alt yordamın yürütülmesi sırasında herhangi bir noktada sonuç bellek bloğunu değiştirebilir. Çağrılan, x0 içindeki bellek bloğunun adresini döndürür.

## <a name="stack"></a>Yığın

ARM tarafından ABı 'in sonunda, yığın her zaman 16 baytlık hizalı olmalıdır. AArch64, SP 16 bayt hizalı olduğunda ve SP göreli yük veya mağaza yapıldığında yığın hizalama hataları üreten bir donanım özelliği içerir. Windows, bu özellik her zaman etkin olarak çalışır.

En fazla 4k veya daha fazla yığın ayıran işlevler, son sayfadan önceki her sayfanın sırayla dokunulmamasını sağlamalıdır. Bu eylem, hiçbir kodun Windows 'un yığını genişletmek için kullandığı koruma sayfalarını "artık üzerinde" olmamasını sağlar. Genellikle, X15 içinde 16 ile bölünen toplam yığın ayırmayı geçiren özel bir çağrı kuralına sahip `__chkstk` Yardımcısı tarafından yapılır.

## <a name="red-zone"></a>Kırmızı bölge

Geçerli yığın işaretçisinin hemen altındaki 16 baytlık alan, analiz ve dinamik düzeltme eki uygulama senaryolarında kullanılmak üzere ayrılmıştır. Bu alan, [SP, #-16] konumunda iki kaydı depolayan ve bunları geçici olarak rastgele amaçlarla kullanan, dikkatle üretilen kodun eklenmesine izin verir. Windows çekirdeği, hem Kullanıcı hem de çekirdek modunda bir özel durum veya kesme alınması durumunda bu 16 baytın üzerine yazılmadığını garanti eder.

## <a name="kernel-stack"></a>Çekirdek yığını

Windows 'daki varsayılan çekirdek modu yığını altı sayfalardır (24 k). Çekirdek modunda büyük yığın arabelleklerine sahip işlevlere fazladan dikkat ödeyin. Hatalı süreli bir kesme, küçük bir yer ile gelebilir ve yığın panik hata denetimi oluşturabilir.

## <a name="stack-walking"></a>Yığın yürüme

Windows içindeki kod, hızlı yığın yürümesini etkinleştirmek için çerçeve işaretçileri ([/oy-](reference/oy-frame-pointer-omission.md)) ile derlenir. Genellikle, x29 (FP) zincirde bir sonraki bağlantıyı işaret eder; bu bir {FP, LR} çiftidir ve bu, yığındaki önceki çerçeveye yönelik işaretçiyi ve dönüş adresini gösterir. Üçüncü taraf kodu, geliştirilmiş profil oluşturma ve izlemeye izin vermek için çerçeve işaretçilerini de etkinleştirecek şekilde teşvik edilir.

## <a name="exception-unwinding"></a>Özel durum geri sarma

Özel durum işleme sırasında geri sarma, geriye doğru izleme kodları kullanımı aracılığıyla yapılır. Geriye doğru izleme kodları, yürütülebilir dosyanın. xdata bölümünde depolanan baytların bir dizisidir. Bu işlemler, bir işlevin prolog 'nin etkilerinin, çağıranın yığın çerçevesine yedekleme hazırlığı sırasında geri alınamayacağı şekilde, bir Özet ve EPIO 'un bir soyut şekilde, bir dizi işlemini anlatmaktadır. Bırakma kodları hakkında daha fazla bilgi için bkz. [ARM64 Exception Handling](arm64-exception-handling.md).

ARM EABI, geriye doğru izleme kodları kullanan bir özel durum izleme modeli de belirtir. Ancak, sunulan belirtim Windows 'da geri sarma için yetersiz, bu da BILGISAYARıN bir işlev prolog veya epıg 'nin ortasında olduğu durumları ele almalıdır.

Dinamik olarak oluşturulan kod, `RtlAddFunctionTable` ve ilişkili işlevler aracılığıyla dinamik işlev tabloları ile açıklanmalıdır, böylece oluşturulan kodun özel durum işleme katılmasını sağlayabilirsiniz.

## <a name="cycle-counter"></a>Bisiklet sayacı

Tüm ARMv8 CPU 'Ları, Windows 'un Kullanıcı modu da dahil olmak üzere herhangi bir özel durum düzeyinde okunabilir olması için Windows 'un yapılandırdığı 64 bitlik bir kayıt olan bir bisiklet sayacı kaydını desteklemesi için gereklidir. Derleme kodundaki MSR Opcode veya C/C++ code içinde `_ReadStatusReg` iç kullanılarak özel PMCCNTR_EL0 kaydı aracılığıyla erişilebilir.

Buradaki Cycle sayacı, bir duvar saati değil, doğru bir geçiş sayacıdır. Sayım sıklığı işlemci sıklığıyla farklılık gösterecektir. Zaman aralığı sayacının sıklığını bilmeniz gerektiğini düşünüyorsanız, zaman aralığı sayacını kullanmamanız gerekir. Bunun yerine, `QueryPerformanceCounter`kullanmanız gereken duvar saati zamanını ölçmek istiyorsunuz.

## <a name="see-also"></a>Ayrıca bkz.

[Genel Visual C++ ARM Geçiş Sorunları](common-visual-cpp-arm-migration-issues.md)<br/>
[ARM64 özel durum işleme](arm64-exception-handling.md)
