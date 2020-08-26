---
title: Varsayılan olarak kapalı olan derleyici uyarıları
ms.date: 08/29/2019
helpviewer_keywords:
- warnings, compiler
- cl.exe compiler, setting options
ms.assetid: 69809cfb-a38a-4035-b154-283a61938df8
ms.openlocfilehash: 3727777c6abd3ae5ba19f147e2b6fbe559251813
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836615"
---
# <a name="compiler-warnings-that-are-off-by-default"></a>Varsayılan olarak kapalı olan derleyici uyarıları

Çoğu geliştirici onları yararlı bulmadığından, derleyici varsayılan olarak kapatılmış uyarıları destekler. Bazı durumlarda, bir stil seçimi veya eski koddaki yaygın deyimler hakkında uyarır. Diğer uyarılar, Microsoft uzantısının dile kullanımı ile ilgilidir. Bazı uyarılar, programcıların genellikle yanlış varsayımlar yaparken, beklenmeyen veya tanımsız davranışlara neden olabilecek bir alanı gösterir. Bu uyarıların tümü etkinleştirilirse, bazı bunlar kitaplık başlıklarında birçok kez görünebilir. C çalışma zamanı kitaplıkları ve C++ standart kitaplıkları yalnızca uyarı düzeyi [/W4](../build/reference/compiler-option-warning-level.md)' te hiçbir uyarı yaymak üzere tasarlanmıştır.

## <a name="enable-warnings-that-are-off-by-default"></a>Varsayılan olarak kapalı olan uyarıları etkinleştir

Aşağıdaki seçeneklerden birini kullanarak, normal olarak varsayılan olarak kapalı olan uyarıları etkinleştirebilirsiniz:

- **#pragma Uyarısı (varsayılan:** *warning_number* **)**

   Belirtilen uyarı (*warning_number*) varsayılan düzeyinde etkindir. Uyarılara yönelik belgeler varsayılan uyarı düzeyini içerir.

- **#pragma Uyarısı (** *warning_level* **:** *warning_number* **)**

   Belirtilen (*warning_number*) uyarısı belirtilen düzeyde (*warning_level*) etkin.

- [/Wall](../build/reference/compiler-option-warning-level.md)

   `/Wall` Varsayılan olarak kapalı olan tüm uyarıları etkinleştirilir. Bu seçeneği kullanırsanız, [/WD](../build/reference/compiler-option-warning-level.md) seçeneğini kullanarak uyarıları tek tek kapatabilirsiniz.

- [/w*Lnnnn*](../build/reference/compiler-option-warning-level.md)

   Bu seçenek, düzey *L*'de Uyarı *nnnn* 'yi sunar.

## <a name="warnings-that-are-off-by-default"></a>Varsayılan olarak kapalı olan uyarılar

Aşağıdaki uyarılar, Visual Studio 2015 ve sonraki sürümlerinde varsayılan olarak kapalıdır:

|Uyarı|İleti|
|-|-|
|[C4061](../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md) (düzey 4)|'*Enumeration*' enum anahtarındaki bir anahtardaki '*Identifier*' numaralandırıcısı bir Case etiketi tarafından açıkça işlenmiyor|
|[C4062](../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md) (düzey 4)|'*Enumeration*' numaralandırması anahtarındaki '*Identifier*' numaralandırıcısı işlenmedi|
| [C4165](../error-messages/compiler-warnings/compiler-warning-level-1-c4165.md) (düzey 1) | ' HRESULT ' ' bool ' olarak dönüştürülüyor; Bunun istediğiniz durum olduğundan emin misiniz? |
| [C4191](../error-messages/compiler-warnings/compiler-warning-level-3-c4191.md) (düzey 3)|'*operator*': '*type_of_expression*' ile '*type_required*' arasında güvenli olmayan dönüştürme|
|[C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) (düzey 4)|'*tanımlayıcı*': '*Type1*' değerinden '*type2*' öğesine dönüştürme, olası veri kaybı|
|[C4254](../error-messages/compiler-warnings/compiler-warning-level-4-c4254.md) (düzey 4)|'*operator*': '*Type1*' değerinden '*type2*' öğesine dönüştürme, olası veri kaybı|
|[C4255](../error-messages/compiler-warnings/compiler-warning-level-4-c4255.md) (düzey 4)|'*Function*': hiçbir işlev prototipi verilmedi: ' () ', ' (void) ' olarak dönüştürülüyor|
|[C4263](../error-messages/compiler-warnings/compiler-warning-level-4-c4263.md) (düzey 4)|'*Function*': üye işlev hiçbir taban sınıf sanal üye işlevini geçersiz kılmıyor|
|[C4264](../error-messages/compiler-warnings/compiler-warning-level-1-c4264.md) (düzey 1)|'*virtual_function*': ' class ' taban '*sınıfından*sanal üye işlevi için geçersiz kılma yok; işlev gizli|
|[C4265](../error-messages/compiler-warnings/compiler-warning-level-3-c4265.md) (düzey 3)|'*Class*': sınıf sanal işlevlere sahip, ancak yıkıcı sanal değil|
|[C4266](../error-messages/compiler-warnings/compiler-warning-level-4-c4266.md) (düzey 4)|'*Function*': temel '*Type*' öğesinden sanal üye işlevi için geçersiz kılma yok; işlev gizli|
|[C4287](../error-messages/compiler-warnings/compiler-warning-level-3-c4287.md) (düzey 3)|'*operator*': işaretsiz/negatif sabit uyuşmazlığı|
|[C4289](../error-messages/compiler-warnings/compiler-warning-level-4-c4289.md) (düzey 4)|Standart olmayan uzantı kullanıldı: '*var*': for döngüsünde belirtilen döngü denetim değişkeni for döngüsü kapsamının dışında kullanılıyor|
|[C4296](../error-messages/compiler-warnings/compiler-warning-level-4-c4296.md) (düzey 4)|'*operator*': ifade her zaman false şeklindedir|
|[C4339](../error-messages/compiler-warnings/compiler-warning-level-4-c4339.md) (düzey 4)|'*Type*': clr meta verilerinde tanımsız tür kullanımı algılandı-Bu türün kullanılması çalışma zamanı özel durumuna neden olabilir|
|[C4342](../error-messages/compiler-warnings/compiler-warning-level-1-c4342.md) (düzey 1)|davranış değişikliği: '*Function*' çağrıldı, ancak önceki sürümlerde bir üye işleci çağrıldı|
|[C4350](../error-messages/compiler-warnings/compiler-warning-level-1-c4350.md) (düzey 1)|davranış değişikliği: '*member1*', '*member2*' yerine çağrıldı|
|[C4355](../error-messages/compiler-warnings/compiler-warning-c4355.md)|'this' : taban üye başlatıcı listesinde kullanıldı|
|[C4365](../error-messages/compiler-warnings/compiler-warning-level-4-c4365.md) (düzey 4)|'*Action*': '*type_1*' değerinden '*type_2*' öğesine dönüştürme, imzalanmış/imzasız uyuşmazlığı|
|C4370 (düzey 3)|daha iyi paketleme nedeniyle sınıfın düzeni önceki bir derleyici sürümünden farklı|
|[C4371](../error-messages/compiler-warnings/c4371.md) (düzey 3)|'*ClassName*': '*member*' üyesinin daha iyi paketlenmesi nedeniyle sınıfın düzeni önceki bir derleyici sürümünden değişmiş olabilir|
|C4388 (düzey 4)|İmzalı/imzasız uyuşmazlığı|
|[C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) (düzey 2)|'*Function*': işlev imzası '*Type*' türünü içeriyor; C++ nesnelerinin saf kod ile karma veya yerel arasında geçmesi güvenli değildir|
|C4426 (düzey 1)|üst bilgi eklendikten sonra iyileştirme bayrakları değişti #pragma optimize olabilir () <sup>14,1</sup>|
|[C4435](../error-messages/compiler-warnings/compiler-warning-level-4-c4435.md) (düzey 4)|'*Class1*':/VD2 altındaki nesne düzeni, '*Class2*' sanal tabanı nedeniyle değiştirilecek|
|[C4437](../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md) (düzey 4)|'*Class1*' sanal tabandan '*class2*' öğesine dynamic_cast bazı bağlamlarda başarısız olabilir|
|C4444 (düzey 3)|en üst düzey '__unaligned' bu bağlamda uygulanmadı|
|[C4464](../error-messages/compiler-warnings/c4464.md) (düzey 4)|göreli ekleme yolu '.. ' içeriyor|
|[C4471](../error-messages/compiler-warnings/compiler-warning-level-4-c4471.md) (düzey 4)|kapsamlı olmayan numaralandırmanın ileri bir bildirimi temel alınan bir türe (int <sup>varsayıldı) sahip</sup> olmalıdır|
|C4472 (düzey 1)|'*Identifier*' yerel bir sabit listesi: yönetilen bir Enum bildirmek için bir erişim belirticisi (Private/public) ekleme|
|[C4514](../error-messages/compiler-warnings/compiler-warning-level-4-c4514.md) (düzey 4)|'*Function*': başvurulmayan satır içi işlev kaldırıldı|
|[C4536](../error-messages/compiler-warnings/compiler-warning-level-4-c4536.md) (düzey 4)|' tür adı ': tür adı '*limit*' karakter olan meta veri sınırını aşıyor|
|[C4545](../error-messages/compiler-warnings/compiler-warning-level-1-c4545.md) (düzey 1)|virgülden önceki ifade bir bağımsız değişken listesi olmayan bir işlev olarak değerleniyor|
|[C4546](../error-messages/compiler-warnings/compiler-warning-level-1-c4546.md) (düzey 1)|virgülden önceki işlev çağrısında bağımsız değişken listesi eksik|
|[C4547](../error-messages/compiler-warnings/compiler-warning-level-1-c4547.md) (düzey 1)|'*operator*': virgülden önceki işlecin etkisi yok; yan etkisi olan işleç bekleniyordu|
|[C4548](../error-messages/compiler-warnings/compiler-warning-level-1-c4548.md) (düzey 1)|virgülden önceki ifadenin etkisi yok; yan etkisi olan ifade bekleniyordu|
|[C4549](../error-messages/compiler-warnings/compiler-warning-level-1-c4549.md) (düzey 1)|'*operator1*': virgülden önceki işlecin etkisi yok; '*operator2*' mı istiyordunuz?|
|[C4555](../error-messages/compiler-warnings/compiler-warning-level-1-c4555.md) (düzey 1)|ifadenin etkisi yok; yan etkisi olan ifade bekleniyordu|
|[C4557](../error-messages/compiler-warnings/compiler-warning-level-3-c4557.md) (düzey 3)|' __assume ' efekt '*etkisi*' içeriyor|
|[C4571](../error-messages/compiler-warnings/compiler-warning-level-4-c4571.md) (düzey 4)|bilgi: catch (...) semantiği Visual C++ 7,1 ' den sonra değişti; yapılandırılmış özel durumlar (SEH) artık yakalanmıyor|
|C4574 (düzey 4)|'*tanımlayıcı*' ' 0 ' olarak tanımlandı: ' #if *Identifier*' kullanmak mı istediniz?|
|C4577 (düzey 1)|' noexcept ', özel durum işleme modu belirtilmediği için kullanıldı; özel durum üzerinde sonlandırma garanti edilmez. /EHsc belirtin|
|C4582 (düzey 4)|'*Type*': Oluşturucu örtük olarak çağrılmadı|
|C4583 (düzey 4)|'*Type*': yıkıcı örtük olarak çağrılmadı|
|C4587 (düzey 1)|'*anonymous_structure*': davranış değişikliği: Oluşturucu artık örtük olarak çağrılmayacak|
|C4588 (düzey 1)|'*anonymous_structure*': davranış değişikliği: yıkıcı artık örtük olarak çağrılmayacak|
|[C4596](../error-messages/compiler-warnings/c4596.md) (düzey 4)|'*tanımlayıcı*': üye bildiriminde geçersiz nitelenmiş ad <sup>14,3</sup> <sup>izin</sup>|
|C4598 (düzey 1 ve düzey 3)|' #include "*üst bilgisi*" ': üst bilgi numarası *üstbilgisi-* ön derlenmiş üstbilgideki sayı bu konumdaki geçerli derleme ile eşleşmiyor <sup>14,3</sup>|
|C4599 (düzey 3)|'*seçenek* *yolu*': komut satırı bağımsız değişkeni numara *numarası* önceden derlenmiş üst bilgi <sup>14,3</sup> ile eşleşmiyor|
|C4605 (düzey 1)|Geçerli komut satırında '/d*makro*' belirtildi, ancak önceden derlenmiş üstbilgi oluşturulduğunda belirtilmemiş|
|[C4608](../error-messages/compiler-warnings/compiler-warning-level-3-c4608.md) (düzey 3)|'*union_member*', Başlatıcı listesindeki başka bir birleşim üyesi tarafından zaten başlatıldı, '*union_member*' <sup>izin</sup>|
|[C4619](../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md) (düzey 3)|#pragma uyarı: '*Number*' uyarı numarası yok|
|[C4623](../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md) (düzey 4)|'derived class': bir taban sınıf varsayılan oluşturucusuna erişilemediğinden varsayılan oluşturucu üretilemedi|
|[C4625](../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md) (düzey 4)|'derived class': bir taban sınıf kopya oluşturucusuna erişilemediğinden kopya oluşturucu üretilemedi|
|[C4626](../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md) (düzey 4)|'derived class': bir taban sınıf atama işlecine erişilemediğinden atama işleci üretilemedi|
|[C4628](../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md) (düzey 1)|-Ze ile digraf kullanılması desteklenmez. '*Digraf*' karakter dizisi '*char*' için alternatif bir belirteç olarak yorumlanmadı|
|[C4640](../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md) (düzey 3)|'*örnek*': yerel statik nesnenin yapımı iş parçacığı güvenli değil|
| C4643 (düzey 4) | Standart ad alanı içindeki '*Identifier*' Iletme bildiriminde C++ standardı tarafından izin verilmiyor. <sup>15,8</sup> |
|C4647 (düzey 3)|davranış değişikliği: __is_pod (*tür*) önceki sürümlerde farklı değere sahip|
|C4654 (düzey 4)|Ön derlenmiş üstbilgi satırı dahil etmeden önce yerleştirilmiş kod yoksayılacak. Kodu önceden derlenmiş üstbilgiye ekleyin. <sup>14,1</sup>|
|[C4668](../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md) (düzey 4)|'*symbol*' bir önişlemci makrosu olarak tanımlanmamış, '*yönergeler*' için ' 0 ' ile değiştiriliyor|
|[C4682](../error-messages/compiler-warnings/compiler-warning-level-4-c4682.md) (düzey 4)|'*symbol*': açıklamalı parametre özniteliği belirtilmedi, [in] varsayılan olarak ayarlanıyor|
|[C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md) (düzey 3)|'*Kullanıcı tanımlı tür*': davranıştaki olası DEĞIŞIKLIK, udt dönüş çağırma kuralına göre değişiklik|
|[C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) (düzey 1)|'*Function*': özel olmayan üyenin imzası '*native_type*' derleme özel yerel türünü içeriyor|
|[C4710](../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md) (düzey 4)|'*Function*': işlev satır içine alınmadı|
|[C4738](../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md) (düzey 3)|32 bit kayan sonuç bellekte depolanıyor, olası performans kaybı|
|[C4746](../error-messages/compiler-warnings/compiler-warning-c4746.md)|'*Expression*' geçici erişimi/volatile: Setting öğesine tabidir \<iso&#124;ms> ; __İso_volatile_load/Store iç işlevlerini kullanmayı düşünün|
|C4749 (düzey 4)|koşullu olarak desteklenir: standart olmayan ' tür ' düzeninde olmayan '*Type*' türü için OffsetOf uygulandı|
|C4767 (düzey 4)|'*symbol*' bölüm adı 8 karakterden uzun ve bağlayıcı tarafından kesilecek|
|C4768 (düzey 3)|bağlantı belirtiminin önüne __declspec öznitelikleri yok sayılıyor|
|C4774 (düzey 4)|'*String*': bağımsız değişken *numarasında* beklenen biçim dizesi bir dize sabit değeri değil|
|C4777 (düzey 4)|'*Function*': biçim dizesi '*String*', '*Type1*' türünde bir bağımsız değişken gerektiriyor, ancak değişen sayıda bağımsız değişken *numarası* '*type2*' türüne sahip|
|C4786 (düzey 3)|'*symbol*': nesne adı hata ayıklama bilgilerinde '*Number*' karakter olarak kesildi|
| [C4800](../error-messages/compiler-warnings/compiler-warning-level-3-c4800.md) (düzey 4) | '*Type*' türünden bool 'a örtük dönüştürme. Olası bilgi kaybı <sup>16,0</sup> |
|[C4820](../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md) (düzey 4)|'*MEMBER_NAME*' yapısı sonrasında '*bayt*' bayt doldurma eklendi|
| [C4822](../error-messages/compiler-warnings/compiler-warning-level-1-c4822.md) (düzey 1) | '*üye*': Yerel sınıf üyesi işlevin gövdesi yok |
|C4826 (düzey 2)|'*Type1*' değerinden '*type2*' öğesine dönüştürme, işaret genişletilmiş. Bu, beklenmeyen çalışma zamanı davranışına neden olabilir.|
|C4837 (düzey 4)|trigraf algılandı: '?? '*karakter '* tarafından değiştirilmiş *karakter*|
|C4841 (düzey 4)|Standart olmayan uzantı kullanıldı: OffsetOf içinde kullanılan bileşik üye göstergesi|
|C4842 (düzey 4)|birden fazla devralma kullanılarak bir türe uygulanan ' OffsetOf ' sonucunun, derleyici yayınları arasında tutarlı olması garanti edilmez|
|[C4868](../error-messages/compiler-warnings/compiler-warning-c4868.md) (düzey 4)|'_File_(*Line_Number*) ' derleyicisi, örgü başlatma listesinde soldan sağa değerlendirme sırasını zorlamaz|
|[C4905](../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md) (düzey 1)|geniş düz dize 'LPSTR' değerine atandı|
|[C4906](../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md) (düzey 1)|düz dize 'LPWSTR' değerine atandı|
|[C4917](../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md) (düzey 1)|'*bildirimci*': bir GUID yalnızca bir sınıf, arabirim veya ad alanıyla ilişkilendirilebilir|
|[C4928](../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md) (düzey 1)|hatalı kopya başlatma; birden çok kullanıcı tanımlı dönüştürme örtük olarak uygulandı|
|[C4931](../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md) (düzey 4)|tür kitaplığının sayı bit işaretçiler için oluşturulduğunu varsayıyoruz|
|[C4946](../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md) (düzey 1)|reinterpret_cast ilgili sınıflar arasında kullanıldı: '*Class1*' ve '*Class2*'|
|C4962|'*Function*': iyileştirmeler profil verilerinin tutarsız olmasına yol açtığı için profil temelli iyileştirmeler devre dışı bırakıldı|
|[C4986](../error-messages/compiler-warnings/compiler-warning-c4986.md) (düzey 4)|'*symbol*': özel durum belirtimi önceki bildirimle eşleşmiyor|
|C4987 (düzey 4)|standart olmayan uzantı kullanıldı: 'throw (...)'|
|C4988 (düzey 4)|'*symbol*': değişken sınıf/işlev kapsamının dışında bildiriliyor|
|C5022|'*Type*': birden fazla taşıma Oluşturucusu belirtildi|
|C5023|'*Type*': birden fazla taşıma atama işleci belirtildi|
|C5024 (düzey 4)|'*Type*': taşıma Oluşturucusu örtük bir şekilde silindi olarak tanımlandı|
|C5025 (düzey 4)|'*Type*': taşıma atama işleci örtük bir şekilde silindi olarak tanımlandı|
|C5026 (düzey 1 ve düzey 4)|'*Type*': taşıma Oluşturucusu örtük bir şekilde silindi olarak tanımlandı|
|C5027 (düzey 1 ve düzey 4)|'*Type*': taşıma atama işleci örtük bir şekilde silindi olarak tanımlandı|
|C5029 (düzey 4)|Standart olmayan uzantı kullanıldı: C++ hizalama öznitelikleri yalnızca değişkenlere, veri üyelerine ve etiket türlerine uygulanır|
|C5031 (düzey 4)|#pragma warning (pop): olası uyuşmazlık, farklı dosya <sup>14,1</sup> ' de oluşan uyarı durumu gönderildi|
|C5032 (düzey 4)|karşılık gelen #pragma warning (pop <sup>14,1</sup> ) #pragma uyarı (push) algılandı|
|C5034|iç '*iç*' kullanımı işlev *işlev adının* Konuk kod <sup>15,3</sup> olarak derlenmesine neden oluyor|
|C5035|'*Feature*' özelliğinin kullanılması işlev *işlevi adının* Konuk kod <sup>15,3</sup> olarak derlenmesine neden oluyor|
|C5036 (düzey 1)|/Hibrit: x86arm64 türünden '*Type1*' ile '*type2*' <sup>15,3</sup> arasında derleme yaparken varargs işlev işaretçisi dönüştürme|
|[C5038](../error-messages/compiler-warnings/c5038.md) (düzey 4)|veri üyesi '*member1*', '*member2*' <sup>15,3</sup> ' dan sonra başlatılacak|
|C5039 (düzey 4)|'*Function*':-EHC altındaki extern c işlevine geçilen, büyük olasılıkla atma işlevine yönelik işaretçi veya başvuru. Bu işlev bir özel durum oluşturursa tanımsız davranış ortaya çıkabilir. <sup>15,5</sup>|
|C5042 (düzey 3)|'*Function*': blok kapsamındaki işlev bildirimleri, standart C++ içinde ' inline ' olarak belirtilemez; ' inline ' belirticisini Kaldır <sup>15,5</sup>|
|[C5045](../error-messages/compiler-warnings/c5045.md)|/Qspectre anahtarı belirtilmişse, derleyici bellek yüklemesi için Spectre risk azaltma ekler <sup>15,7</sup>|

<sup>14,1</sup> bu uyarı, Visual Studio 2015 güncelleştirme 1 ' den başlayarak kullanılabilir. \
<sup>14,3</sup> bu uyarı, Visual Studio 2015 güncelleştirme 3 ' den başlayarak kullanılabilir. \
<sup>15,3</sup> bu uyarı, Visual Studio 2017 sürüm 15,3 ' den başlayarak kullanılabilir. \
<sup>15,5</sup> bu uyarı, Visual Studio 2017 sürüm 15,5 ' den başlayarak kullanılabilir. \
<sup>15,7</sup> bu uyarı, Visual Studio 2017 sürüm 15,7 ' den başlayarak kullanılabilir. \
<sup>15,8</sup> bu uyarı, Visual Studio 2017 sürüm 15,8 ' den başlayarak kullanılabilir. \
<sup>16,0</sup> bu uyarı, Visual STUDIO 2019 RTM 'den başlayarak kullanılabilir. \
<sup>İzin</sup> [/Permissive-](../build/reference/permissive-standards-conformance.md) derleyici seçeneği ayarlanmadığı takdirde bu uyarı kapalıdır.

## <a name="warnings-off-by-default-in-earlier-versions"></a>Önceki sürümlerde varsayılan olarak kapatma uyarıları

Bu uyarılar, Visual Studio 2015 ' den önceki derleyicinin sürümlerinde varsayılan olarak kapalıdır:

|Uyarı|İleti|
|-|-|
|[C4302](../error-messages/compiler-warnings/compiler-warning-level-2-c4302.md) (düzey 2)|'*dönüştürme*': '*Type1*' öğesinden '*type2*' öğesine kesildi|
|[C4311](../error-messages/compiler-warnings/compiler-warning-level-1-c4311.md) (düzey 1)|'*değişken*': '*Type*' ile '*Type*' işaretçisi kesildi|
|[C4312](../error-messages/compiler-warnings/compiler-warning-level-1-c4312.md) (düzey 1)|'*Operation*': '*Type1*' öğesinden daha büyük boyutlu '*type2*' öğesine dönüştürme|
|[C4319](../error-messages/compiler-warnings/compiler-warning-level-1-c4319.md) (düzey 1)|'*operator*': '*Type1*' değerini daha büyük boyuttaki '*type2*' öğesine genişletme|

Bu uyarı, Visual Studio 2012 ' den önceki derleyicinin sürümlerinde varsayılan olarak kapalıdır:

|Uyarı|İleti|
|-|-|
|[C4431](../error-messages/compiler-warnings/compiler-warning-level-4-c4431.md) (düzey 4)|tür belirticisi eksik - int varsayıldı. Not: C artık varsayılan int desteği içermiyor|

## <a name="see-also"></a>Ayrıca bkz.

[Warning](../preprocessor/warning.md)
