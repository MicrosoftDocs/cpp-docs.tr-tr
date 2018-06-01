---
title: Varsayılan olarak kapalı olan derleyici uyarıları | Microsoft Docs
ms.date: 05/30/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- warnings, compiler
- cl.exe compiler, setting options
ms.assetid: 69809cfb-a38a-4035-b154-283a61938df8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d311c730781aee70d4b77723ddec98a79407e42a
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705572"
---
# <a name="compiler-warnings-that-are-off-by-default"></a>Varsayılan olarak kapalı olan derleyici uyarıları

Çoğu geliştirici bunları görmek istemediğiniz çünkü derleyici varsayılan olarak kapalı uyarıları içerir. Bazı durumlarda, bunlar bir stil seçim temsil eden ortak deyimleri eski koduna sahip olan veya dil için bir Microsoft uzantısı yararlanmak. Diğer durumlarda, bunlar burada programcıları beklenmeyen veya tanımsız davranışa neden olabilir yanlış varsayımlar genellikle olun bir alanı gösterir. Bu uyarıların bir kısmı, kitaplık üstbilgileri çok gürültülü olabilir. C çalışma zamanı kitaplıkları ve C++ Standart Kitaplığı yalnızca uyarı düzeyinde uyarı yaymak üzere tasarlanmıştır [/W4](../build/reference/compiler-option-warning-level.md).

## <a name="enable-warnings-that-are-off-by-default"></a>Varsayılan olarak kapalı olan uyarılar etkinleştir

Normalde kapalı varsayılan olarak aşağıdaki seçeneklerden birini kullanarak olan uyarıları etkinleştirebilirsiniz:

- **#pragma Uyarısı (varsayılan:** *warning_number* **)**

   Belirtilen uyarı (*warning_number*), varsayılan düzeyinde etkinleştirilir. Uyarılara yönelik belgeler varsayılan uyarı düzeyini içerir.

- **#pragma Uyarısı (** *warning_level* **:** *warning_number* **)**

   Belirtilen uyarı (*warning_number*) belirtilen düzeyinde etkinleştirilir (*warning_level*).

- [/ Wall](../build/reference/compiler-option-warning-level.md)

   **/ Duvar** varsayılan olarak kapalı olan tüm uyarıları sağlar. Bu seçeneği kullanırsanız, kullanarak tek tek ayarları kapatabilirsiniz [/wd](../build/reference/compiler-option-warning-level.md) seçeneği.

- [/w*Lnnnn*](../build/reference/compiler-option-warning-level.md)

   Bu uyarı sağlar *nnnn* düzeyinde *L*.

## <a name="warnings-that-are-off-by-default"></a>Varsayılan olarak kapalı olan uyarılar

Aşağıdaki uyarılarla Visual Studio 2015 ve sonraki sürümlerinde varsayılan olarak kapalıdır:

|||
|-|-|
|[C4061](../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md) (düzey 4)|Numaralandırıcı '*tanımlayıcısı*'ın bir anahtar Enum'*numaralandırma*' açıkça bir servis talebi etiketle işlenmedi|
|[C4062](../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md) (düzey 4)|Numaralandırıcı '*tanımlayıcısı*'ın bir anahtar Enum'*numaralandırma*' değil işlenir|
|C4191 (düzey 3)|'*işleci*': Güvenli olmayan bir dönüştürme '*type_of_expression*'to'*type_required*'|
|[C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) (düzey 4)|'*tanımlayıcısı*': dönüştürme '*type1*'to'*type2*', olası veri kaybını|
|[C4254](../error-messages/compiler-warnings/compiler-warning-level-4-c4254.md) (düzey 4)|'*işleci*': dönüştürme '*type1*'to'*type2*', olası veri kaybını|
|[C4255](../error-messages/compiler-warnings/compiler-warning-level-4-c4255.md) (düzey 4)|'*işlevi*': verilen hiçbir işlev prototipi: dönüştürme '(void)' için ' (')|
|[C4263](../error-messages/compiler-warnings/compiler-warning-level-4-c4263.md) (düzey 4)|'*işlevi*': üye işlevini geçersiz bir temel sınıf sanal üye işlevi|
|[C4264](../error-messages/compiler-warnings/compiler-warning-level-1-c4264.md) (düzey 1)|'*virtual_function*': temel sanal üyesi işlevinden için kullanılabilir geçersiz kılma '*sınıfı*'; işlevi gizli|
|[C4265](../error-messages/compiler-warnings/compiler-warning-level-3-c4265.md) (Düzey 3)|'*sınıfı*': sınıfı sanal işlevlere sahiptir, ancak yıkıcı sanal değil|
|[C4266](../error-messages/compiler-warnings/compiler-warning-level-4-c4266.md) (düzey 4)|'*işlevi*': temel sanal üyesi işlevinden için kullanılabilir geçersiz kılma '*türü*'; işlevi gizli|
|[C4287](../error-messages/compiler-warnings/compiler-warning-level-3-c4287.md) (Düzey 3)|'*işleci*': İmzasız negatif sabit uyuşmazlığı|
|[C4289](../error-messages/compiler-warnings/compiler-warning-level-4-c4289.md) (düzey 4)|kullanılan standart olmayan uzantısı: '*var*': for döngüsü denetim değişkeni için-döngüde bildirilen for döngüsü kapsamı dışında kullanılır|
|[C4296](../error-messages/compiler-warnings/compiler-warning-level-4-c4296.md) (düzey 4)|'*işleci*': ifade değer her zaman false|
|[C4339](../error-messages/compiler-warnings/compiler-warning-level-4-c4339.md) (düzey 4)|'*türü*': Tanımsız Tür kullanımını algılandı CLR meta veri - bu türün kullanımı, bir çalışma zamanı özel durumuna neden olabilir|
|[C4342](../error-messages/compiler-warnings/compiler-warning-level-1-c4342.md) (düzey 1)|davranış değişikliği: '*işlevi*' çağrılır, ancak üye işleci önceki sürümlerde çağrıldı|
|[C4350](../error-messages/compiler-warnings/compiler-warning-level-1-c4350.md) (düzey 1)|davranış değişikliği: '*Üye1*'yerine adında'*üye2*'|
|[C4355](../error-messages/compiler-warnings/compiler-warning-c4355.md)|'this' : taban üye başlatıcı listesinde kullanıldı|
|[C4365](../error-messages/compiler-warnings/compiler-warning-level-4-c4365.md) (düzey 4)|'*eylem*': dönüştürme '*type_1*'to'*type_2*', imzalı ve imzasız uyuşmazlığı|
|C4370 (Düzey 3)|daha iyi paketleme nedeniyle sınıfın düzeni önceki bir derleyici sürümünden farklı|
|[C4371](../error-messages/compiler-warnings/c4371.md) (Düzey 3)|'*classname*': sınıf yerleşimini üyesinin daha iyi paketleme nedeniyle Derleyici önceki bir sürümünden değişmiş olabilir '*üye*'|
|C4388 (düzey 4)|İmzalı/imzasız uyuşmazlığı|
|[C4412'yi](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) (Düzey 2)|'*işlevi*': işlev imzası içeren türü '*türü*'; Saf kod arasında geçirmek için güvenli ve karma veya yerel C++ nesneleri|
|C4426 (düzey 1)|en iyi duruma getirme bayrakları üstbilgisi de dahil olmak sonra değiştirilen #pragma optimize() nedeniyle olabilir <sup>14.1</sup>|
|[C4435](../error-messages/compiler-warnings/compiler-warning-level-4-c4435.md) (düzey 4)|'*class1*': nesne düzeni /vd2 altında nedeniyle sanal taban değiştirir '*Ders2*'|
|[C4437](../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md) (düzey 4)|Sanal Taban gelen dynamic_cast '*class1*'to'*Ders2*' bazı bağlamlarda başarısız olabilir|
|C4444 (Düzey 3)|en üst düzey '__unaligned' bu bağlamda uygulanmadı|
|[C4464](../error-messages/compiler-warnings/c4464.md) (düzey 4)|göreli yol dahil içeren '..'|
|[C4471](../error-messages/compiler-warnings/compiler-warning-level-4-c4471.md) (düzey 4)|bir temel alınan türü (int olduğu varsayılır) dizininden kapsam dışı numaralandırma ileriye dönük bildirimi olmalıdır <sup>işle</sup>|
|C4472 (düzey 1)|'*tanımlayıcısı*' yerel Enum: yönetilen bir enum bildirmek için bir erişim belirteci (özel/ortak) Ekle|
|[C4514](../error-messages/compiler-warnings/compiler-warning-level-4-c4514.md) (düzey 4)|'*işlevi*': başvurulmayan satır içi işlev kaldırıldı|
|[C4536](../error-messages/compiler-warnings/compiler-warning-level-4-c4536.md) (düzey 4)|'tür adı': tür adı meta veri sınırını aşan '*sınırı*' karakter|
|[C4545](../error-messages/compiler-warnings/compiler-warning-level-1-c4545.md) (düzey 1)|virgülden önceki ifade bir bağımsız değişken listesi olmayan bir işlev olarak değerleniyor|
|[C4546](../error-messages/compiler-warnings/compiler-warning-level-1-c4546.md) (düzey 1)|virgülden önceki işlev çağrısında bağımsız değişken listesi eksik|
|[C4547](../error-messages/compiler-warnings/compiler-warning-level-1-c4547.md) (düzey 1)|'*işleci*': virgülle; etkisizdir önce işleci yan etkisi olan beklenen işleci|
|[C4548](../error-messages/compiler-warnings/compiler-warning-level-1-c4548.md) (düzey 1)|virgülden önceki ifadenin etkisi yok; yan etkisi olan ifade bekleniyordu|
|[C4549](../error-messages/compiler-warnings/compiler-warning-level-1-c4549.md) (düzey 1)|'*operator1*': işleci virgülle önce hiçbir etkisi; istiyordunuz '*operator2*'?|
|[C4555](../error-messages/compiler-warnings/compiler-warning-level-1-c4555.md) (düzey 1)|ifadenin etkisi yok; yan etkisi olan ifade bekleniyordu|
|[C4557](../error-messages/compiler-warnings/compiler-warning-level-3-c4557.md) (Düzey 3)|'__assume' içeren etkisi '*etkisi*'|
|[C4571](../error-messages/compiler-warnings/compiler-warning-level-4-c4571.md) (düzey 4)|Bilgi amaçlı: Visual C++ 7.1 beri değiştirilen catch(...) semantiği; yapılandırılmış özel durum (SEH) artık yakalandı|
|C4574 (düzey 4)|'*tanımlayıcısı*'0 ' olarak tanımlanan': kullanılacak mu demek istediniz ' #if *tanımlayıcısı*'?|
|C4577 (düzey 1)|hiçbir özel durum işleme belirtilen modu ile kullanılan noexcept'; özel durum sonlandırıldığında garanti edilmez. /EHsc belirtin|
|C4582 (düzey 4)|'*türü*': Oluşturucu örtük olarak çağrılmaz|
|C4583 (düzey 4)|'*türü*': yıkıcı örtük olarak çağrılmaz|
|C4587 (düzey 1)|'*anonymous_structure*': davranış değişikliği: Oluşturucusu artık dolaylı olarak çağrılır|
|C4588 (düzey 1)|'*anonymous_structure*': davranış değişikliği: yıkıcı artık dolaylı olarak çağrılır|
|C4596 (düzey 4)|'*tanımlayıcısı*': üye bildiriminde geçersiz tam ad <sup>14.3</sup> <sup>işle</sup>|
|C4598 (düzey 1 ve Düzey 3)|' #include "*üstbilgi*"': üstbilgi numarası *numarası* önceden derlenmiş üst bilgi bu konumda geçerli derleme eşleşmiyor <sup>14.3</sup>|
|C4599 (Düzey 3)|'*seçeneği* *yolu*': komut satırı bağımsız değişken numarası *numarası* önceden derlenmiş üstbilgi eşleşmiyor <sup>14.3</sup>|
|C4605 (düzey 1)|' /D*makrosu*' geçerli bir komut satırında belirtilen, ancak ne zaman önceden derlenmiş üst bilgi oluşturulmuş belirtilmedi|
|[C4608](../error-messages/compiler-warnings/compiler-warning-level-3-c4608.md) (Düzey 3)|'*union_member*'zaten başka bir bileşim üyesi başlatıcısı listesinde tarafından başlatıldı'*union_member*' <sup>işle</sup>|
|[C4619](../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md) (Düzey 3)|#pragma uyarısı: uyarı numarası yok '*numarası*'|
|[C4623](../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md) (düzey 4)|'derived class': bir taban sınıf varsayılan oluşturucusuna erişilemediğinden varsayılan oluşturucu üretilemedi|
|[C4625](../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md) (düzey 4)|'derived class': bir taban sınıf kopya oluşturucusuna erişilemediğinden kopya oluşturucu üretilemedi|
|[C4626](../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md) (düzey 4)|'derived class': bir taban sınıf atama işlecine erişilemediğinden atama işleci üretilemedi|
|[C4628](../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md) (düzey 1)|-Ze ile digraf kullanılması desteklenmez. Karakter dizisi '*digraph*'alternatif belirteci için yorumlanan değil'*char*'|
|[C4640](../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md) (Düzey 3)|'*örneği*': yerel statik nesne yapımı iş parçacığı açısından güvenli değil|
|C4647 (Düzey 3)|davranış değişikliği: __is_pod (*türü*) önceki sürümlerde farklı bir değere sahip|
|C4654 (düzey 4)|Kod önce yerleştirilmiş dahil önceden derlenmiş başlık satırı yok sayılacak. Kodu önceden derlenmiş üstbilgi ekleyin. <sup>14.1</sup>|
|[C4668](../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md) (düzey 4)|'*simgesi*'için '0' ile değiştirerek bir önişlemci makrosu olarak tanımlanmadığından'*yönergeleri*'|
|[C4682](../error-messages/compiler-warnings/compiler-warning-level-4-c4682.md) (düzey 4)|'*sembol*': [in] varsayarak belirtilen yönlü parametre özniteliği yok|
|[C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md) (Düzey 3)|'*kullanıcı tanımlı tür*': olası değişiklik davranış UDT değişikliği iade çağırma|
|[C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) (düzey 1)|'*işlevi*': İmza özel olmayan üye olarak içeren derleme özel yerel tür '*NATIVE_TYPE*'|
|[C4710](../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md) (düzey 4)|'*işlevi*': değil içermesinden işlevi|
|[C4738](../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md) (Düzey 3)|32 bit kayan sonuç bellekte depolanıyor, olası performans kaybı|
|[C4746](../error-messages/compiler-warnings/compiler-warning-c4746.md)|volatile erişimini '*ifade*' / volatile tabi olan:\<ISO&#124;ms > ayarlama; __iso_volatile_load/deposu iç işlevler kullanmayı düşünün|
|C4749 (düzey 4)|Koşullu desteklenen: non standard düzeni türüne uygulanacağını offsetof '*türü*'|
|C4767 (düzey 4)|Bölüm adı '*sembol*' 8 karakterden uzun ve bağlayıcı tarafından kesilecek|
|C4768 (level 3)|bağlantı belirtimi önce __declspec öznitelikleri göz ardı edilir|
|C4774 (düzey 4)|'*dize*': biçim dizesi bağımsız değişkeni beklenen *numarası* bir dize sabit değeri değil|
|C4777 (düzey 4)|'*işlevi*': biçim dizesi '*dize*'türünde bir bağımsız değişken gerektirir'*type1*', ancak variadic bağımsız değişkeni *numarası* türüne sahip '*type2*'|
|C4786 (Düzey 3)|'*simgesi*': nesne adı için kesildi '*numarası*' hata ayıklama bilgileri karakter|
|[C4820](../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md) (düzey 4)|'*bayt*'Doldurma bayt eklenen sonra yapı'*member_name*'|
|C4826 (Düzey 2)|Dönüştürme '*type1*'to'*type2*' oturum genişletilmiş olduğu. Bu, çalışma zamanı beklenmeyen davranışlara neden olabilir.|
|C4837 (düzey 4)|trigrafı algılandı: '?? *karakter*'yerine'*karakter*'|
|C4841 (düzey 4)|kullanılan standart uzantısı: offsetof içinde kullanılan bileşik üye göstergesi|
|C4842 (düzey 4)|'birden çok devralmayı kullanma türüne uygulanacağını offsetof' sonucunu derleyici sürümler arasında tutarlı olması garanti edilmez|
|[C4868](../error-messages/compiler-warnings/compiler-warning-c4868.md) (düzey 4)|'_dosya_(*line_number*)' derleyici zorla küme ayracı içine alınan başlatma listesinde soldan sağa değerlendirme sırası|
|[C4905](../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md) (düzey 1)|geniş düz dize 'LPSTR' değerine atandı|
|[C4906](../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md) (düzey 1)|düz dize 'LPWSTR' değerine atandı|
|[C4917](../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md) (düzey 1)|'*bildirimcisi*': GUID yalnızca bir sınıf, arabirimi veya ad alanı ile ilişkilendirilebilir|
|[C4928](../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md) (düzey 1)|hatalı kopya başlatma; birden çok kullanıcı tanımlı dönüştürme örtük olarak uygulandı|
|[C4931](../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md) (düzey 4)|tür kitaplığının sayı bit işaretçiler için oluşturulduğunu varsayıyoruz|
|[C4946](../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md) (düzey 1)|ilgili sınıflar arasında kullanılan reinterpret_cast: '*class1*'ve'*Ders2*'|
|C4962|'*işlevi*': Profil temelli iyileştirmeler iyileştirmeler profil verileri tutarsız hale gelmesine neden olduğundan devre dışı|
|[C4986](../error-messages/compiler-warnings/compiler-warning-c4986.md) (düzey 4)|'*sembol*': özel durum belirtimi önceki bildirimi eşleşmiyor|
|C4987 (düzey 4)|standart olmayan uzantı kullanıldı: 'throw (...)'|
|C4988 (düzey 4)|'*sembol*': değişken bildirilen dış sınıfı ya da işlevin kapsamı|
|C5022|'*türü*': belirtilen birden çok taşıma oluşturucuları|
|C5023|'*türü*': belirtilen birden çok taşıma atama işleçleri|
|C5024 (düzey 4)|'*türü*': Oluşturucusu silindi olarak örtük olarak tanımlanmıştı taşıma|
|C5025 (düzey 4)|'*türü*': atama işleci silindi olarak örtük olarak tanımlanmıştı taşıma|
|C5026 (düzey 1 ve düzey 4)|'*türü*': Oluşturucusu silindi olarak örtük olarak tanımlanmıştı taşıma|
|C5027 (düzey 1 ve düzey 4)|'*türü*': atama işleci silindi olarak örtük olarak tanımlanmıştı taşıma|
|C5029 (düzey 4)|kullanılan standart olmayan uzantısı: C++ hizalama öznitelikleri değişkenleri, veri üyeleri ve yalnızca etiket türleri için geçerlidir|
|C5031 (düzey 4)|#pragma warning(pop): büyük olasılıkla uyuşmazlığı, farklı bir dosya gönderilen uyarı durumuna pencerelerinin <sup>14.1</sup>|
|C5032 (düzey 4)|#pragma warning(push) karşılık gelen hiçbir #pragma warning(pop) ile algılanan <sup>14.1</sup>|
|C5034|biri iç kullanmak '*iç*' neden işlevi *işlevi* Konuk kodu olarak derlenecek <sup>15.3</sup>|
|C5035|özelliğini kullanın '*özelliği*' neden işlevi *işlevi* Konuk kodu olarak derlenecek <sup>15.3</sup>|
|C5036 (düzey 1)|VarArgs işlev işaretçisi dönüştürme /hybrid:x86arm64 ile derleme yapılırken '*type1*'to'*type2*' <sup>15.3</sup>|
|[C5038](../error-messages/compiler-warnings/c5038.md) (düzey 4)|veri üyesi '*Üye1*'veri üyesi sonra başlatılacak'*üye2*' <sup>15.3</sup>|
|C5039 (düzey 4)|'*işlevi*': - EHc altında extern C işlev işaretçisi veya potansiyel olarak işlevi atma başvuru geçirilen. Bu işlev bir özel durum oluşturursa tanımsız davranış ortaya çıkabilir. <sup>15,5</sup>|
|C5042 (Düzey 3)|'*işlevi*': blok kapsamında işlev bildirimleri standart C++'da belirtilen 'satır içi' olamaz; 'inline' tanımlayıcısı kaldırın <sup>15,5</sup>|

<sup>14.1</sup> bu uyarı Visual Studio 2015 güncelleştirme 1'den itibaren kullanılabilmektedir.<br>
<sup>14.3</sup> bu uyarı, Visual Studio 2015 güncelleştirme 3'te itibaren kullanılabilir.<br>
<sup>15.3</sup> bu uyarı, Visual Studio 2017 sürüm 15.3 itibaren kullanılabilir.<br>
<sup>15,5</sup> bu uyarı, Visual Studio 2017 sürüm 15,5 itibaren kullanılabilir.<br>
<sup>/P</sup> bu uyarıyı devre dışı olduğu sürece [/ izin veren-](../build/reference/permissive-standards-conformance.md) derleyici seçeneği ayarlanmış.

## <a name="warnings-off-by-default-in-earlier-versions"></a>Önceki sürümlerde varsayılan olarak kapalı uyarıları

Bu uyarılar derleyici Visual Studio 2015 tarihinden önceki sürümlerinde varsayılan olarak kapalı olan:

|||
|-|-|
|[C4302](../error-messages/compiler-warnings/compiler-warning-level-2-c4302.md) (Düzey 2)|'*dönüştürme*': gelen kesilmesi '*type1*'to'*type2*'|
|[C4311](../error-messages/compiler-warnings/compiler-warning-level-1-c4311.md) (düzey 1)|'*değişkeni*': gelen işaretçi kesilmesi '*türü*'to'*türü*'|
|[C4312](../error-messages/compiler-warnings/compiler-warning-level-1-c4312.md) (düzey 1)|'*işlemi*': dönüştürme '*type1*'to'*type2*' büyük boyutu|
|[C4319](../error-messages/compiler-warnings/compiler-warning-level-1-c4319.md) (düzey 1)|'*işleci*': sıfır genişletme '*type1*'to'*type2*' büyük boyutu|

Visual Studio 2012 önce derleyici sürümlerinde varsayılan olarak devre dışı bu uyarı oluştu:

|||
|-|-|
|[C4431](../error-messages/compiler-warnings/compiler-warning-level-4-c4431.md) (düzey 4)|tür belirticisi eksik - int varsayıldı. Not: C artık varsayılan int desteği içermiyor|

## <a name="see-also"></a>Ayrıca Bkz.

[warning](../preprocessor/warning.md)
