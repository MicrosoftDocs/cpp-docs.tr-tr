---
title: "Varsayılan olarak kapalı olan derleyici uyarıları | Microsoft Docs"
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- warnings, compiler
- cl.exe compiler, setting options
ms.assetid: 69809cfb-a38a-4035-b154-283a61938df8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c447389de1accfe95674855645fe044e1d3df41
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="compiler-warnings-that-are-off-by-default"></a>Varsayılan Olarak Kapalı Olan Derleyici Uyarıları

Derleyici, çoğu kullanıcının bunları görmek istemediğinden, varsayılan olarak kapatılmış uyarılar içerir. Ancak, aşağıdaki seçeneklerden birini kullanarak bu uyarıları etkinleştirebilirsiniz.

**#pragma Uyarısı (varsayılan:** *warning_number* **)**  
Belirtilen uyarı (*warning_number*), varsayılan düzeyinde etkinleştirilir. Uyarılara yönelik belgeler varsayılan uyarı düzeyini içerir.

**#pragma Uyarısı (** *warning_level* **:** *warning_number* **)**  
Belirtilen uyarı (*warning_number*) belirtilen düzeyinde etkinleştirilir (*warning_level*).

[/ Wall](../build/reference/compiler-option-warning-level.md)  
**/ Duvar** varsayılan olarak kapalı olan tüm uyarıları sağlar.

Aşağıdaki uyarılar varsayılan olarak kapalıdır.

|||
|-|-|
|[C4061](../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md) (düzey 4)|Numaralandırıcı '*tanımlayıcısı*'ın bir anahtar Enum'*numaralandırma*' açıkça bir servis talebi etiketle işlenmedi|
|[C4062](../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md) (level 4)|Numaralandırıcı '*tanımlayıcısı*'ın bir anahtar Enum'*numaralandırma*' değil işlenir|
|C4191 (düzey 3)|'*işleci*': Güvenli olmayan bir dönüştürme '*type_of_expression*'to'*type_required*'|
|[C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) (level 4)|'*tanımlayıcısı*': dönüştürme '*type1*'to'*type2*', olası veri kaybını|
|[C4254](../error-messages/compiler-warnings/compiler-warning-level-4-c4254.md) (level 4)|'*işleci*': dönüştürme '*type1*'to'*type2*', olası veri kaybını|
|[C4255](../error-messages/compiler-warnings/compiler-warning-level-4-c4255.md) (level 4)|'*işlevi*': verilen hiçbir işlev prototipi: dönüştürme '(void)' için ' (')|
|[C4263](../error-messages/compiler-warnings/compiler-warning-level-4-c4263.md) (level 4)|'*işlevi*': üye işlevini geçersiz bir temel sınıf sanal üye işlevi|
|[C4264](../error-messages/compiler-warnings/compiler-warning-level-1-c4264.md) (düzey 1)|'*virtual_function*': temel sanal üyesi işlevinden için kullanılabilir geçersiz kılma '*sınıfı*'; işlevi gizli|
|[C4265](../error-messages/compiler-warnings/compiler-warning-level-3-c4265.md) (Düzey 3)|'*sınıfı*': sınıfı sanal işlevlere sahiptir, ancak yıkıcı sanal değil|
|[C4266](../error-messages/compiler-warnings/compiler-warning-level-4-c4266.md) (düzey 4)|'*işlevi*': temel sanal üyesi işlevinden için kullanılabilir geçersiz kılma '*türü*'; işlevi gizli|
|[C4287](../error-messages/compiler-warnings/compiler-warning-level-3-c4287.md) (Düzey 3)|'*işleci*': İmzasız negatif sabit uyuşmazlığı|
|[C4289](../error-messages/compiler-warnings/compiler-warning-level-4-c4289.md) (level 4)|kullanılan standart olmayan uzantısı: '*var*': for döngüsü denetim değişkeni için-döngüde bildirilen for döngüsü kapsamı dışında kullanılır|
|[C4296](../error-messages/compiler-warnings/compiler-warning-level-4-c4296.md) (level 4)|'*işleci*': ifade değer her zaman false|
|[C4339](../error-messages/compiler-warnings/compiler-warning-level-4-c4339.md) (level 4)|'*türü*': Tanımsız Tür kullanımını algılandı CLR meta veri - bu türün kullanımı, bir çalışma zamanı özel durumuna neden olabilir|
|[C4342](../error-messages/compiler-warnings/compiler-warning-level-1-c4342.md) (düzey 1)|davranış değişikliği: '*işlevi*' çağrılır, ancak üye işleci önceki sürümlerde çağrıldı|
|[C4350](../error-messages/compiler-warnings/compiler-warning-level-1-c4350.md) (level 1)|davranış değişikliği: '*Üye1*'yerine adında'*üye2*'|
|[C4355](../error-messages/compiler-warnings/compiler-warning-c4355.md)|'this' : taban üye başlatıcı listesinde kullanıldı|
|[C4365](../error-messages/compiler-warnings/compiler-warning-level-4-c4365.md) (level 4)|'*eylem*': dönüştürme '*type_1*'to'*type_2*', imzalı ve imzasız uyuşmazlığı|
|C4370 (level 3)|daha iyi paketleme nedeniyle sınıfın düzeni önceki bir derleyici sürümünden farklı|
|[C4371](../error-messages/compiler-warnings/c4371.md) (Düzey 3)|'*classname*': sınıf yerleşimini üyesinin daha iyi paketleme nedeniyle Derleyici önceki bir sürümünden değişmiş olabilir '*üye*'|
|C4388 (level 4)|İmzalı/imzasız uyuşmazlığı|
|[C4412'yi](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) (Düzey 2)|'*işlevi*': işlev imzası içeren türü '*türü*'; Saf kod arasında geçirmek için güvenli ve karma veya yerel C++ nesneleri|
|C4426 (level 1)|en iyi duruma getirme bayrakları üstbilgisi de dahil olmak sonra değiştirilen #pragma optimize() nedeniyle olabilir|
|[C4435](../error-messages/compiler-warnings/compiler-warning-level-4-c4435.md) (level 4)|'*class1*': nesne düzeni /vd2 altında nedeniyle sanal taban değiştirir '*Ders2*'|
|[C4437](../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md) (düzey 4)|Sanal Taban gelen dynamic_cast '*class1*'to'*Ders2*' bazı bağlamlarda başarısız olabilir|
|C4444 (level 3)|en üst düzey '__unaligned' bu bağlamda uygulanmadı|
|C4464 (level 4)|göreli yol dahil içeren '..'|
|C4472 (level 1)|'*tanımlayıcısı*' yerel Enum: yönetilen bir enum bildirmek için bir erişim belirteci (özel/ortak) Ekle|
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
|C4574 (level 4)|'*tanımlayıcısı*'0 ' olarak tanımlanan': kullanılacak mu demek istediniz ' #if *tanımlayıcısı*'?|
|C4582 (level 4)|'*türü*': Oluşturucu örtük olarak çağrılmaz|
|C4583 (level 4)|'*türü*': yıkıcı örtük olarak çağrılmaz|
|C4587 (level 1)|'*anonymous_structure*': davranış değişikliği: Oluşturucusu artık dolaylı olarak çağrılır|
|C4588 (düzey 1)|'*anonymous_structure*': davranış değişikliği: yıkıcı artık dolaylı olarak çağrılır|
|C4598 (düzey 1 ve Düzey 3)|' #include "*üstbilgi*"': üstbilgi numarası *numarası* önceden derlenmiş üst bilgi, bu konumda geçerli derleme eşleşmiyor.|
|C4599 (Düzey 3)|'*seçeneği* *yolu*': komut satırı bağımsız değişken numarası *numarası* önceden derlenmiş üstbilgi eşleşmiyor.|
|C4605 (düzey 1)|' /D*makrosu*' geçerli bir komut satırında belirtilen, ancak ne zaman önceden derlenmiş üst bilgi oluşturulmuş belirtilmedi|
|[C4619](../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md) (Düzey 3)|#pragma uyarısı: uyarı numarası yok '*numarası*'|
|[C4623](../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md) (level 4)|'derived class': bir taban sınıf varsayılan oluşturucusuna erişilemediğinden varsayılan oluşturucu üretilemedi|
|[C4625](../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md) (level 4)|'derived class': bir taban sınıf kopya oluşturucusuna erişilemediğinden kopya oluşturucu üretilemedi|
|[C4626](../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md) (level 4)|'derived class': bir taban sınıf atama işlecine erişilemediğinden atama işleci üretilemedi|
|[C4628](../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md) (düzey 1)|-Ze ile digraf kullanılması desteklenmez. Karakter dizisi '*digraph*'alternatif belirteci için yorumlanan değil'*char*'|
|[C4640](../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md) (Düzey 3)|'*örneği*': yerel statik nesne yapımı iş parçacığı açısından güvenli değil|
|C4647 (Düzey 3)|davranış değişikliği: __is_pod (*türü*) önceki sürümlerde farklı bir değere sahip|
|C4654 (level 4)|Kod önce yerleştirilmiş dahil önceden derlenmiş başlık satırı yok sayılacak. Kodu önceden derlenmiş üstbilgi ekleyin.|
|[C4668](../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md) (düzey 4)|'*simgesi*'için '0' ile değiştirerek bir önişlemci makrosu olarak tanımlanmadığından'*yönergeleri*'|
|[C4682](../error-messages/compiler-warnings/compiler-warning-level-4-c4682.md) (düzey 4)|'*sembol*': [in] varsayarak belirtilen yönlü parametre özniteliği yok|
|[C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md) (Düzey 3)|'*kullanıcı tanımlı tür*': olası değişiklik davranış UDT değişikliği iade çağırma|
|[C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) (düzey 1)|'*işlevi*': İmza özel olmayan üye olarak içeren derleme özel yerel tür '*NATIVE_TYPE*'|
|[C4710](../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md) (level 4)|'*işlevi*': değil içermesinden işlevi|
|[C4738](../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md) (Düzey 3)|32 bit kayan sonuç bellekte depolanıyor, olası performans kaybı|
|[C4746](../error-messages/compiler-warnings/compiler-warning-c4746.md)|volatile erişimini '*ifade*' / volatile tabi olan:\<ISO &#124; ms > ayarlama; __iso_volatile_load/deposu iç işlevler kullanmayı düşünün|
|C4749 (level 4)|Koşullu desteklenen: non standard düzeni türüne uygulanacağını offsetof '*türü*'|
|C4767 (level 4)|Bölüm adı '*sembol*' 8 karakterden uzun ve bağlayıcı tarafından kesilecek|
|C4768 (level 3)|bağlantı belirtimi önce __declspec öznitelikleri göz ardı edilir|
|C4774 (level 4)|'*dize*': biçim dizesi bağımsız değişkeni beklenen *numarası* bir dize sabit değeri değil|
|C4786 (level 3)|'*simgesi*': nesne adı için kesildi '*numarası*' hata ayıklama bilgileri karakter|
|[C4820](../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md) (level 4)|'*bayt*'Doldurma bayt eklenen sonra yapı'*member_name*'|
|C4826 (level 2)|Dönüştürme '*type1*'to'*type2*' oturum genişletilmiş olduğu. Bu, çalışma zamanı beklenmeyen davranışlara neden olabilir.|
|C4837 (düzey 4)|trigrafı algılandı: '?? *karakter*'yerine'*karakter*'|
|C4841 (level 4)|kullanılan standart uzantısı: offsetof içinde kullanılan bileşik üye göstergesi|
|C4842 (level 4)|'birden çok devralmayı kullanma türüne uygulanacağını offsetof' sonucunu derleyici sürümler arasında tutarlı olması garanti edilmez|
|[C4868](../error-messages/compiler-warnings/compiler-warning-c4868.md) (düzey 4)|'_dosya_(*line_number*)' derleyici zorla küme ayracı içine alınan başlatma listesinde soldan sağa değerlendirme sırası|
|[C4905](../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md) (düzey 1)|geniş düz dize 'LPSTR' değerine atandı|
|[C4906](../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md) (düzey 1)|düz dize 'LPWSTR' değerine atandı|
|[C4917](../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md) (düzey 1)|'*bildirimcisi*': GUID yalnızca bir sınıf, arabirimi veya ad alanı ile ilişkilendirilebilir|
|[C4928](../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md) (düzey 1)|hatalı kopya başlatma; birden çok kullanıcı tanımlı dönüştürme örtük olarak uygulandı|
|[C4931](../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md) (düzey 4)|tür kitaplığının sayı bit işaretçiler için oluşturulduğunu varsayıyoruz|
|[C4946](../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md) (düzey 1)|ilgili sınıflar arasında kullanılan reinterpret_cast: '*class1*'ve'*Ders2*'|
|C4962|'*işlevi*': Profil temelli iyileştirmeler iyileştirmeler profil verileri tutarsız hale gelmesine neden olduğundan devre dışı|
|[C4986](../error-messages/compiler-warnings/compiler-warning-c4986.md) (level 4)|'*sembol*': özel durum belirtimi önceki bildirimi eşleşmiyor|
|C4987 (level 4)|standart olmayan uzantı kullanıldı: 'throw (...)'|
|C4988 (level 4)|'*sembol*': değişken bildirilen dış sınıfı ya da işlevin kapsamı|
|C5022|'*türü*': belirtilen birden çok taşıma oluşturucuları|
|C5023|'*türü*': belirtilen birden çok taşıma atama işleçleri|
|C5024 (level 4)|'*türü*': Oluşturucusu silindi olarak örtük olarak tanımlanmıştı taşıma|
|C5025 (level 4)|'*türü*': atama işleci silindi olarak örtük olarak tanımlanmıştı taşıma|
|C5026 (düzey 1 ve düzey 4)|'*türü*': Oluşturucusu silindi olarak örtük olarak tanımlanmıştı taşıma|
|C5027 (düzey 1 ve düzey 4)|'*türü*': atama işleci silindi olarak örtük olarak tanımlanmıştı taşıma|
|C5029 (level 4)|kullanılan standart olmayan uzantısı: C++ hizalama öznitelikleri değişkenleri, veri üyeleri ve yalnızca etiket türleri için geçerlidir|
|C5031 (level 4)|#pragma warning(pop): farklı bir dosya gönderilen uyarı durumuna pencerelerinin büyük olasılıkla uyuşmazlığı|
|C5032 (level 4)|#pragma warning(push) karşılık gelen hiçbir #pragma warning(pop) ile algılandı|
|C5035|özelliğini kullanın '*özelliği*' neden işlevi *işlevi* Konuk kodu olarak derlenecek|
|C5036 (level 1)|VarArgs işlev işaretçisi dönüştürme /hybrid:x86arm64 ile derleme yapılırken '*type1*'to'*type2*'|

Bu uyarılar sürece kapalıdır [/ izin veren-](../build/reference/permissive-standards-conformance.md) derleyici seçeneği ayarlanır:

|||
|-|-|
|[C4471 (düzey 4)](../error-messages/compiler-warnings/compiler-warning-level-4-c4471.md)|kapsamsız bir numaralandırmanın ileri dönük bildiriminin bir temel türü olmalıdır (int varsayıldı)|
|[C4608 (Düzey 3)](../error-messages/compiler-warnings/compiler-warning-level-3-c4608.md)|'*union_member*'zaten başka bir bileşim üyesi başlatıcısı listesinde tarafından başlatıldı'*union_member*'|

Bu uyarılar derleyici Visual Studio 2015 tarihinden önceki sürümlerinde varsayılan olarak kapalı olan:

|||
|-|-|
|[C4302](../error-messages/compiler-warnings/compiler-warning-level-2-c4302.md) (Düzey 2)|'*dönüştürme*': gelen kesilmesi '*type1*'to'*type2*'|
|[C4311](../error-messages/compiler-warnings/compiler-warning-level-1-c4311.md) (düzey 1)|'*değişkeni*': gelen işaretçi kesilmesi '*türü*'to'*türü*'|
|[C4312](../error-messages/compiler-warnings/compiler-warning-level-1-c4312.md) (düzey 1)|'*işlemi*': dönüştürme '*type1*'to'*type2*' büyük boyutu|
|[C4319](../error-messages/compiler-warnings/compiler-warning-level-1-c4319.md) (düzey 1)|'*işleci*': sıfır genişletme '*type1*'to'*type2*' büyük boyutu|

Bu uyarılar Visual Studio 2012 önce derleyici sürümlerinde varsayılan olarak kapalı olan:

|||
|-|-|
|[C4431](../error-messages/compiler-warnings/compiler-warning-level-4-c4431.md) (düzey 4)|tür belirticisi eksik - int varsayıldı. Not: C artık varsayılan int desteği içermiyor|

## <a name="see-also"></a>Ayrıca Bkz.

[warning](../preprocessor/warning.md)
