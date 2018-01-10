---
title: "Varsayılan olarak kapalı olan derleyici uyarıları | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: cpp-tools
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- warnings, compiler
- cl.exe compiler, setting options
ms.assetid: 69809cfb-a38a-4035-b154-283a61938df8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 48afd89f4b795a4f582d8b9506c527a602a1d2b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warnings-that-are-off-by-default"></a>Varsayılan Olarak Kapalı Olan Derleyici Uyarıları

Derleyici, çoğu kullanıcının bunları görmek istemediğinden, varsayılan olarak kapatılmış uyarılar içerir. Ancak, aşağıdaki seçeneklerden birini kullanarak bu uyarıları etkinleştirebilirsiniz.

`#pragma warning(default : warning_number )`  
Belirtilen uyarı (`warning_number`), varsayılan düzeyinde etkinleştirilir. Uyarılara yönelik belgeler varsayılan uyarı düzeyini içerir.

`#pragma warning( warning_level : warning_number )`  
Belirtilen uyarı (`warning_number`) belirtilen düzeyinde etkinleştirilir (`warning_level`).

[/ Wall](../build/reference/compiler-option-warning-level.md)  
**/ Duvar** varsayılan olarak kapalı olan tüm uyarıları sağlar.

Aşağıdaki uyarılar varsayılan olarak kapalıdır.

|||
|-|-|
|[C4061](../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md) (düzey 4)|'enumeration' numaralandırıcısının switch deyimindeki 'identifier' numaralandırıcısı case etiketi tarafından açıkça işlenmiyor|
|[C4062](../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md) (düzey 4)|'enumeration' numaralandırıcısının switch deyimindeki 'identifier' numaralandırıcısı işlenmiyor|
|C4191 (düzey 3)|'operator/operation': 'type of expression' öğesinden 'type required' öğesine güvensiz dönüştürme|
|[C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) (düzey 4)|'identifier': 'type1' öğesinden 'type2' öğesine dönüştürme, olası veri kaybı|
|[C4254](../error-messages/compiler-warnings/compiler-warning-level-4-c4254.md) (düzey 4)|''operator': 'type1' öğesinden 'type2' öğesine dönüştürme, olası veri kaybı|
|[C4255](../error-messages/compiler-warnings/compiler-warning-level-4-c4255.md) (düzey 4)|'function': hiçbir işlev prototipi verilmedi: '()', '(void)' olarak dönüştürülüyor|
|[C4263](../error-messages/compiler-warnings/compiler-warning-level-4-c4263.md) (düzey 4)|'function': üye işlev hiçbir taban sınıfı sanal üye işlevini geçersiz kılmıyor|
|[C4264](../error-messages/compiler-warnings/compiler-warning-level-1-c4264.md) (düzey 1)|'virtual_function': 'class' tabanındaki sanal üye işlev için kullanılabilecek geçersiz kılma yok; işlev gizlendi|
|[C4265](../error-messages/compiler-warnings/compiler-warning-level-3-c4265.md) (Düzey 3)|'class': sınıfta sanal işlevler var, ancak yıkıcı sanal değil|
|[C4266](../error-messages/compiler-warnings/compiler-warning-level-4-c4266.md) (düzey 4)|'function': 'type' tabanındaki sanal üye işlev için kullanılabilecek geçersiz kılma yok; işlev gizlendi|
|[C4287](../error-messages/compiler-warnings/compiler-warning-level-3-c4287.md) (Düzey 3)|'operator': işaretsiz/negatif sabit uyuşmazlığı|
|[C4289](../error-messages/compiler-warnings/compiler-warning-level-4-c4289.md) (düzey 4)|standart olmayan uzantı kullanıldı : 'var': for döngüsünde bildirimi yapılan döngü denetim değişkeni for döngüsü kapsamının dışında kullanılıyor|
|[C4296](../error-messages/compiler-warnings/compiler-warning-level-4-c4296.md) (düzey 4)|'operator': ifade her zaman yanlış|
|[C4339](../error-messages/compiler-warnings/compiler-warning-level-4-c4339.md) (düzey 4)|'type': CLR meta verilerinde tanımsız tür kullanıldığı saptandı - bu türün kullanılması çalışma zamanı özel durumuna neden olabilir|
|[C4342](../error-messages/compiler-warnings/compiler-warning-level-1-c4342.md) (düzey 1)|behavior change: 'function' çağrıldı, ancak önceki sürümlerde bir üye işleç çağrılıyordu|
|[C4350](../error-messages/compiler-warnings/compiler-warning-level-1-c4350.md) (düzey 1)|behavior change: 'member2' yerine 'member1' çağrıldı|
|[C4355](../error-messages/compiler-warnings/compiler-warning-c4355.md)|'this' : taban üye başlatıcı listesinde kullanıldı|
|[C4365](../error-messages/compiler-warnings/compiler-warning-level-4-c4365.md) (düzey 4)|'action': 'type_1' öğesinden 'type_2' öğesine dönüştürme, imzalı/imzasız uyuşmazlığı|
|C4370 (Düzey 3)|daha iyi paketleme nedeniyle sınıfın düzeni önceki bir derleyici sürümünden farklı|
|C4371 (Düzey 3)|'member' üyesinin daha iyi paketlenmesi nedeniyle sınıfın düzeni önceki bir derleyici sürümünden farklı olabilir|
|C4388 (düzey 4)|İmzalı/imzasız uyuşmazlığı|
|[C4412'yi](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) (Düzey 2)|'function': işlev imzası 'type' türü içeriyor; C++ nesnelerinin saf kod ile karma veya yerel kod arasında geçirilmesi güvenli değildir|
|C4426 (düzey 1)|en iyi duruma getirme bayrakları üstbilgisi de dahil olmak sonra değiştirilen #pragma optimize() nedeniyle olabilir|
|[C4435](../error-messages/compiler-warnings/compiler-warning-level-4-c4435.md) (düzey 4)|'class1' : /vd2 altındaki nesne düzeni 'class2' sanal tabanı nedeniyle değişecek|
|[C4437](../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md) (düzey 4)|sanal taban 'class1' öğesinden 'class2' öğesine dynamic_cast bazı bağlamlarda başarısız olabilirdi|
|C4444 (Düzey 3)|en üst düzey '__unaligned' bu bağlamda uygulanmadı|
|C4464 (düzey 4)|göreli yol dahil içeren '..'|
|C4472 (düzey 1)|'identifier' is a native enum: bir erişim belirticisi (private/public) ekleyerek bir yönetilen numaralandırıcı bildirimi yapın|
|[C4514](../error-messages/compiler-warnings/compiler-warning-level-4-c4514.md) (düzey 4)|'function': başvurulmayan bir satır içi işlevi kaldırıldı|
|[C4536](../error-messages/compiler-warnings/compiler-warning-level-4-c4536.md) (düzey 4)|'type name': tür adı 'limit' karakter olan meta veri sınırını aşıyor|
|[C4545](../error-messages/compiler-warnings/compiler-warning-level-1-c4545.md) (düzey 1)|virgülden önceki ifade bir bağımsız değişken listesi olmayan bir işlev olarak değerleniyor|
|[C4546](../error-messages/compiler-warnings/compiler-warning-level-1-c4546.md) (düzey 1)|virgülden önceki işlev çağrısında bağımsız değişken listesi eksik|
|[C4547](../error-messages/compiler-warnings/compiler-warning-level-1-c4547.md) (düzey 1)|'operator': virgülden önceki işlecin etkisi yok; yan etkisi olan işleç bekleniyordu|
|[C4548](../error-messages/compiler-warnings/compiler-warning-level-1-c4548.md) (düzey 1)|virgülden önceki ifadenin etkisi yok; yan etkisi olan ifade bekleniyordu|
|[C4549](../error-messages/compiler-warnings/compiler-warning-level-1-c4549.md) (düzey 1)|'operator': virgülden önceki işlecin etkisi yok; 'operator' kullanmak mı istiyordunuz?|
|[C4555](../error-messages/compiler-warnings/compiler-warning-level-1-c4555.md) (düzey 1)|ifadenin etkisi yok; yan etkisi olan ifade bekleniyordu|
|[C4557](../error-messages/compiler-warnings/compiler-warning-level-3-c4557.md) (Düzey 3)|'__assume' 'effect' etkisini içeriyor|
|[C4571](../error-messages/compiler-warnings/compiler-warning-level-4-c4571.md) (düzey 4)|Bilgi amaçlı: Visual C++ 7.1 beri değiştirilen catch(...) semantiği; yapılandırılmış özel durum (SEH) artık yakalandı|
|C4574 (düzey 4)|'identifier' '0' olacak şekilde tanımlandı: '#if identifier' kullanmayı mı amaçlamıştınız?|
|C4582 (düzey 4)|'*türü*': Oluşturucu örtük olarak çağrılmaz|
|C4583 (düzey 4)|'*türü*': yıkıcı örtük olarak çağrılmaz|
|C4587 (düzey 1)|'*anonymous_structure*': davranış değişikliği: Oluşturucusu artık dolaylı olarak çağrılır|
|C4588 (düzey 1)|'*anonymous_structure*': davranış değişikliği: yıkıcı artık dolaylı olarak çağrılır|
|C4598 (düzey 1 ve Düzey 3)|' #include "*üstbilgi*"': üstbilgi numarası *numarası* önceden derlenmiş üst bilgi, bu konumda geçerli derleme eşleşmiyor.|
|C4599 (Düzey 3)|'*seçeneği* *yolu*': komut satırı bağımsız değişken numarası *numarası* önceden derlenmiş üstbilgi eşleşmiyor.|
|C4605 (düzey 1)|' /D*makrosu*' geçerli bir komut satırında belirtilen, ancak ne zaman önceden derlenmiş üst bilgi oluşturulmuş belirtilmedi|
|[C4619](../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md) (Düzey 3)|#pragma warning: 'number' numaralı bir uyarı yok|
|[C4623](../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md) (düzey 4)|'derived class': bir taban sınıf varsayılan oluşturucusuna erişilemediğinden varsayılan oluşturucu üretilemedi|
|[C4625](../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md) (düzey 4)|'derived class': bir taban sınıf kopya oluşturucusuna erişilemediğinden kopya oluşturucu üretilemedi|
|[C4626](../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md) (düzey 4)|'derived class': bir taban sınıf atama işlecine erişilemediğinden atama işleci üretilemedi|
|[C4628](../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md) (düzey 1)|-Ze ile digraf kullanılması desteklenmez. 'digraph' karakter dizisi 'char' için alternatif bir belirteç olarak yorumlanmadı|
|[C4640](../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md) (Düzey 3)|'instance': yerel durağan nesnenin yapımı iş parçacığı güvenli değil|
|C4647 (Düzey 3)|davranış değişikliği: __is_pod (*türü*) önceki sürümlerde farklı bir değere sahip|
|C4654 (düzey 4)|Kod önce yerleştirilmiş dahil önceden derlenmiş başlık satırı yok sayılacak. Kodu önceden derlenmiş üstbilgi ekleyin.|
|[C4668](../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md) (düzey 4)|'*simgesi*'için '0' ile değiştirerek bir önişlemci makrosu olarak tanımlanmadığından'*yönergeleri*'|
|[C4682](../error-messages/compiler-warnings/compiler-warning-level-4-c4682.md) (düzey 4)|'*sembol*': [in] varsayarak belirtilen yönlü parametre özniteliği yok|
|[C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md) (Düzey 3)|'*kullanıcı tanımlı tür*': olası değişiklik davranış UDT değişikliği iade çağırma|
|[C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) (düzey 1)|'*işlevi*': İmza özel olmayan üye olarak içeren derleme özel yerel tür 'NATIVE_TYPE'|
|[C4710](../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md) (düzey 4)|'*işlevi*': değil içermesinden işlevi|
|[C4738](../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md) (Düzey 3)|32 bit kayan sonuç bellekte depolanıyor, olası performans kaybı|
|[C4746](../error-messages/compiler-warnings/compiler-warning-c4746.md)|volatile erişimini '*ifade*' / volatile tabi olan:\<ISO &#124; ms > ayarlama; __iso_volatile_load/deposu iç işlevler kullanmayı düşünün|
|C4749 (düzey 4)|Koşullu desteklenen: non standard düzeni türüne uygulanacağını offsetof '*türü*'|
|C4767 (düzey 4)|Bölüm adı '*sembol*' 8 karakterden uzun ve bağlayıcı tarafından kesilecek|
|C4768 (Düzey 3)|bağlantı belirtimi önce __declspec öznitelikleri göz ardı edilir|
|C4774 (düzey 4)|'*dize*': biçim dizesi bağımsız değişkeni beklenen *numarası* bir dize sabit değeri değil|
|C4786 (Düzey 3)|'*sembol*': nesne adı, hata ayıklama bilgileri 'numara' karakter kesildi|
|[C4820](../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md) (düzey 4)|eklenen 'member_name' oluştur değerinden sonra 'bytes' bayt dolduruluyor|
|C4826 (Düzey 2)|Dönüştürme '*type1*'to'*type2*' oturum genişletilmiş olduğu. Bu, çalışma zamanı beklenmeyen davranışlara neden olabilir.|
|C4837 (düzey 4)|trigrafı algılandı: '?? *karakter*'yerine'*karakter*'|
|C4841 (düzey 4)|kullanılan standart uzantısı: offsetof içinde kullanılan bileşik üye göstergesi|
|C4842 (düzey 4)|'birden çok devralmayı kullanma türüne uygulanacağını offsetof' sonucunu derleyici sürümler arasında tutarlı olması garanti edilmez|
|[C4868](../error-messages/compiler-warnings/compiler-warning-c4868.md) (düzey 4)|'_dosya_(*line_number*)' derleyici zorla küme ayracı içine alınan başlatma listesinde soldan sağa değerlendirme sırası|
|[C4905](../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md) (düzey 1)|geniş düz dize 'LPSTR' değerine atandı|
|[C4906](../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md) (düzey 1)|düz dize 'LPWSTR' değerine atandı|
|[C4917](../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md) (düzey 1)|'declarator': bir GUID yalnızca bir sınıf, arabirim veya ad alanıyla ilişkilendirilebilir|
|[C4928](../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md) (düzey 1)|hatalı kopya başlatma; birden çok kullanıcı tanımlı dönüştürme örtük olarak uygulandı|
|[C4931](../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md) (düzey 4)|tür kitaplığının sayı bit işaretçiler için oluşturulduğunu varsayıyoruz|
|[C4946](../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md) (düzey 1)|reinterpret_cast ilgili sınıflar arasında kullanıldı: 'class1' ve 'class2'|
|C4962|'function': İyileştirmeler profil verilerinin tutarsız olmasına yol açtığı için profil temelli iyileştirmeler devre dışı bırakıldı|
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
|C5031 (düzey 4)|#pragma warning(pop): farklı bir dosya gönderilen uyarı durumuna pencerelerinin büyük olasılıkla uyuşmazlığı|
|C5032 (düzey 4)|#pragma warning(push) karşılık gelen hiçbir #pragma warning(pop) ile algılandı|
|C5035|özelliğini kullanın '*özelliği*' neden işlevi *işlevi* Konuk kodu olarak derlenecek|
|C5036 (düzey 1)|VarArgs işlev işaretçisi dönüştürme /hybrid:x86arm64 ile derleme yapılırken '*type1*'to'*type2*'|

Bu uyarılar sürece kapalıdır [/ izin veren-](../build/reference/permissive-standards-conformance.md) derleyici seçeneği ayarlanır:

|||
|-|-|
|[C4471 (düzey 4)](../error-messages/compiler-warnings/compiler-warning-level-4-c4471.md)|kapsamsız bir numaralandırmanın ileri dönük bildiriminin bir temel türü olmalıdır (int varsayıldı)|
|[C4608 (Düzey 3)](../error-messages/compiler-warnings/compiler-warning-level-3-c4608.md)|' birleşim\_üye ' Başlatıcısı listesinde, 'union_member' başka bir bileşim üyesi tarafından zaten başlatıldı|


Bu uyarılar derleyici Visual Studio 2015 tarihinden önceki sürümlerinde varsayılan olarak kapalı olan:

|||
|-|-|
|[C4302](../error-messages/compiler-warnings/compiler-warning-level-2-c4302.md) (Düzey 2)|'conversion': 'type1' öğesinden 'type2' öğesine kesilme|
|[C4311](../error-messages/compiler-warnings/compiler-warning-level-1-c4311.md) (düzey 1)|'variable' : 'type' öğesinden 'type' öğesine işaretçi kesilmesi|
|[C4312](../error-messages/compiler-warnings/compiler-warning-level-1-c4312.md) (düzey 1)|'operation' : 'type1' öğesinden daha büyük boyutlu 'type2' öğesine dönüştürme|
|[C4319](../error-messages/compiler-warnings/compiler-warning-level-1-c4319.md) (düzey 1)|'işleci': sıfır genişletme 'type1' büyük boyutta 'type2'|

Bu uyarılar Visual Studio 2012 önce derleyici sürümlerinde varsayılan olarak kapalı olan:

|||
|-|-|
|[C4431](../error-messages/compiler-warnings/compiler-warning-level-4-c4431.md) (düzey 4)|tür belirticisi eksik - int varsayıldı. Not: C artık varsayılan int desteği içermiyor|

## <a name="see-also"></a>Ayrıca Bkz.

[warning](../preprocessor/warning.md)
