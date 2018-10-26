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
ms.openlocfilehash: c7b48b2382ee22cc5d11c1145dc494aca4e7997f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083197"
---
# <a name="compiler-warnings-that-are-off-by-default"></a>Varsayılan olarak kapalı olan derleyici uyarıları
Derleyici, çoğu Geliştirici bunları görmek istemediğinden, varsayılan olarak kapalı uyarıları içerir. Bazı durumlarda, bunlar bir stil seçimi temsil ortak deyimleri eski koduna sahip olan veya dil için bir Microsoft uzantısı yararlanın. Diğer durumlarda, bunlar burada programcılar beklenmeyen veya tanımsız davranışa neden yanlış varsayımlarda bulunmaları genellikle olun bir alanı belirtir. Bu uyarıların bazıları kitaplığı üst bilgilerinde çok gürültülü olabilir. C çalışma zamanı kitaplıkları ve C++ Standart Kitaplığı yalnızca uyarı düzeyinde uyarı yaymak için hedeflenen [/W4](../build/reference/compiler-option-warning-level.md).

## <a name="enable-warnings-that-are-off-by-default"></a>Varsayılan olarak kapalı olan uyarıları etkinleştir

Normalde varsayılan olarak aşağıdaki seçeneklerden birini kullanarak kapalıdır uyarıları etkinleştirebilirsiniz:

- **#pragma Uyarısı (varsayılan:** *warning_number* **)**

   Belirtilen uyarı (*warning_number*), varsayılan düzeyinde etkinleştirilir. Uyarılara yönelik belgeler varsayılan uyarı düzeyini içerir.

- **#pragma Uyarısı (** *warning_level* **:** *warning_number* **)**

   Belirtilen uyarı (*warning_number*) belirtilen düzeyde etkin (*warning_level*).

- [/ Wall](../build/reference/compiler-option-warning-level.md)

   `/Wall` Varsayılan olarak kapalı olan tüm uyarıları etkinleştirir. Bu seçeneği kullanırsanız, ayrı ayrı ayarları kullanarak kapatabilirsiniz [/wd](../build/reference/compiler-option-warning-level.md) seçeneği.

- [/w*Lnnnn*](../build/reference/compiler-option-warning-level.md)

   Bu uyarı sağlar *nnnn* düzeyinde *L*.

## <a name="warnings-that-are-off-by-default"></a>Varsayılan olarak kapalı olan uyarılar

Aşağıdaki uyarılar Visual Studio 2015 ve sonraki sürümlerinde varsayılan olarak kapalıdır:

|||
|-|-|
|[C4061](../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md) (düzey 4)|Numaralandırıcı '*tanımlayıcı*'numaralandırıcısının switch' ın*numaralandırma*' case etiketi tarafından açıkça işlenmiyor|
|[C4062](../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md) (düzey 4)|Numaralandırıcı '*tanımlayıcı*'numaralandırıcısının switch' ın*numaralandırma*' işlenmezse|
|C4191 (düzey 3)|'*işleci*': Güvenli olmayan dönüştürme '*type_of_expression*'to'*type_required*'|
|[C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) (düzey 4)|'*tanımlayıcı*': dönüştürme '*type1*'to'*type2*', olası veri kaybı|
|[C4254](../error-messages/compiler-warnings/compiler-warning-level-4-c4254.md) (düzey 4)|'*işleci*': dönüştürme '*type1*'to'*type2*', olası veri kaybı|
|[C4255](../error-messages/compiler-warnings/compiler-warning-level-4-c4255.md) (düzey 4)|'*işlevi*': hiçbir işlev prototipi verilmedi: '(') '(void)' olarak dönüştürülüyor|
|[C4263](../error-messages/compiler-warnings/compiler-warning-level-4-c4263.md) (düzey 4)|'*işlevi*': üye işlev hiçbir taban sınıfı sanal üye işlevini Geçersiz Kılmıyor|
|[C4264](../error-messages/compiler-warnings/compiler-warning-level-1-c4264.md) (düzey 1)|'*virtual_function*': taban sanal üye işlev için kullanılabilecek geçersiz kılma yok '*sınıfı*'; işlev gizlendi|
|[C4265](../error-messages/compiler-warnings/compiler-warning-level-3-c4265.md) (Düzey 3)|'*sınıfı*': sınıfın sanal işlevleri var ancak yok edici sanal değil|
|[C4266](../error-messages/compiler-warnings/compiler-warning-level-4-c4266.md) (düzey 4)|'*işlevi*': taban sanal üye işlev için kullanılabilecek geçersiz kılma yok '*türü*'; işlev gizlendi|
|[C4287](../error-messages/compiler-warnings/compiler-warning-level-3-c4287.md) (Düzey 3)|'*işleci*': işaretsiz/negatif sabit uyuşmazlığı|
|[C4289](../error-messages/compiler-warnings/compiler-warning-level-4-c4289.md) (düzey 4)|Standart olmayan uzantı kullanıldı: '*var*': for döngüsünde bildirimi yapılan döngü denetim değişkeni for döngüsü kapsamının dışında kullanılıyor|
|[C4296](../error-messages/compiler-warnings/compiler-warning-level-4-c4296.md) (düzey 4)|'*işleci*': ifade false, her zaman|
|[C4339](../error-messages/compiler-warnings/compiler-warning-level-4-c4339.md) (düzey 4)|'*türü*': Tanımsız Tür algılandı CLR meta verilerinde - bu türün kullanılması çalışma zamanı özel durumuna neden|
|[C4342](../error-messages/compiler-warnings/compiler-warning-level-1-c4342.md) (düzey 1)|davranış değişikliği: '*işlevi*' çağrıldı, ancak önceki sürümlerde bir üye işleç çağrılıyordu|
|[C4350](../error-messages/compiler-warnings/compiler-warning-level-1-c4350.md) (düzey 1)|davranış değişikliği: '*Üye1*'yerine adlandırılan'*üye2*'|
|[C4355](../error-messages/compiler-warnings/compiler-warning-c4355.md)|'this' : taban üye başlatıcı listesinde kullanıldı|
|[C4365](../error-messages/compiler-warnings/compiler-warning-level-4-c4365.md) (düzey 4)|'*eylem*': dönüştürme '*type_1*'to'*type_2*', imzalı/imzasız uyuşmazlığı|
|C4370 (Düzey 3)|daha iyi paketleme nedeniyle sınıfın düzeni önceki bir derleyici sürümünden farklı|
|[C4371](../error-messages/compiler-warnings/c4371.md) (Düzey 3)|'*classname*': sınıfın düzeni önceki bir üyesinin daha iyi paketleme nedeniyle derleyici sürümünden değişmiş olabilir '*üye*'|
|C4388 (düzey 4)|İmzalı/imzasız uyuşmazlığı|
|[C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) (Düzey 2)|'*işlevi*': işlev imzası içeren tür '*türü*'; C++ nesnelerinin saf kod arasında geçirilmesi güvenli değildir ve karma veya yerel|
|C4426 (düzey 1)|iyileştirme bayrakları üst bilgi eklendikten sonra değişti, nedeni #pragma optimize() olabilir <sup>14.1</sup>|
|[C4435](../error-messages/compiler-warnings/compiler-warning-level-4-c4435.md) (düzey 4)|'*class1*': / vd2 altındaki Nesne düzeni sanal tabanı nedeniyle değişecek '*class2*'|
|[C4437](../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md) (düzey 4)|dynamic_cast'sanal tabanından '*class1*'to'*class2*' bazı bağlamlarda başarısız olabilirdi|
|C4444 (Düzey 3)|en üst düzey '__unaligned' bu bağlamda uygulanmadı|
|[C4464](../error-messages/compiler-warnings/c4464.md) (düzey 4)|göreli ekleme yolu içeren '..'|
|[C4471](../error-messages/compiler-warnings/compiler-warning-level-4-c4471.md) (düzey 4)|kapsamsız bir numaralandırmanın İleri dönük bildiriminin bir temel türü (int varsayıldı) olmalıdır <sup>işle</sup>|
|C4472 (düzey 1)|'*tanımlayıcı*' yerel bir numaralandırma: bir yönetilen Numaralandırıcı bildirimi bir erişim belirticisi (private/public) Ekle|
|[C4514](../error-messages/compiler-warnings/compiler-warning-level-4-c4514.md) (düzey 4)|'*işlevi*': başvurulmayan satır içi işlev kaldırıldı|
|[C4536](../error-messages/compiler-warnings/compiler-warning-level-4-c4536.md) (düzey 4)|'type name': tür adı, meta veri sınırını aşıyor '*sınırı*' karakter|
|[C4545](../error-messages/compiler-warnings/compiler-warning-level-1-c4545.md) (düzey 1)|virgülden önceki ifade bir bağımsız değişken listesi olmayan bir işlev olarak değerleniyor|
|[C4546](../error-messages/compiler-warnings/compiler-warning-level-1-c4546.md) (düzey 1)|virgülden önceki işlev çağrısında bağımsız değişken listesi eksik|
|[C4547](../error-messages/compiler-warnings/compiler-warning-level-1-c4547.md) (düzey 1)|'*işleci*': virgülden önceki etkisi yok; işleci yan etkisi olan beklenen işleci|
|[C4548](../error-messages/compiler-warnings/compiler-warning-level-1-c4548.md) (düzey 1)|virgülden önceki ifadenin etkisi yok; yan etkisi olan ifade bekleniyordu|
|[C4549](../error-messages/compiler-warnings/compiler-warning-level-1-c4549.md) (düzey 1)|'*operator1*': virgülden önceki işlecin etkisi yok; kullanmak mı istiyordunuz '*operator2*'?|
|[C4555](../error-messages/compiler-warnings/compiler-warning-level-1-c4555.md) (düzey 1)|ifadenin etkisi yok; yan etkisi olan ifade bekleniyordu|
|[C4557](../error-messages/compiler-warnings/compiler-warning-level-3-c4557.md) (Düzey 3)|'__assume' etkisi içeriyor '*etkisi*'|
|[C4571](../error-messages/compiler-warnings/compiler-warning-level-4-c4571.md) (düzey 4)|Bilgi amaçlı: Visual C++ 7.1 sürümünden sonra değişti catch(...) semantiği; yapılandırılmış özel durumlar (SEH) artık yakalanmıyor|
|C4574 (düzey 4)|'*tanımlayıcı*'' 0'olacak şekilde tanımlanır': kullanmayı mı amaçlamıştınız ' #if *tanımlayıcı*'?|
|C4577 (düzey 1)|'noexcept' hiçbir özel durum işleme modu belirtilmeden kullanılan; özel durum sonlandırma garanti edilmez. / Ehsc belirtin|
|C4582 (düzey 4)|'*türü*': Oluşturucu örtük olarak çağırılmamış|
|C4583 (düzey 4)|'*türü*': yıkıcı örtük olarak çağırılmamış|
|C4587 (düzey 1)|'*anonymous_structure*': davranış değişikliği: Oluşturucu artık örtük olarak çağırılamaz|
|C4588 (düzey 1)|'*anonymous_structure*': davranış değişikliği: yıkıcı artık örtük olarak çağırılamaz|
|C4596 (düzey 4)|'*tanımlayıcı*': üye bildiriminde geçersiz nitelenmiş ad <sup>14.3</sup> <sup>işle</sup>|
|C4598 (düzey 1 ve Düzey 3)|' #include "*üstbilgi*"': üst bilgisi numarası *numarası* önceden derlenmiş üst bilgisinde bu konumda geçerli derleme eşleşmiyor <sup>14.3</sup>|
|C4599 arasındaki (Düzey 3)|'*seçeneği* *yolu*': komut satırı bağımsız değişken numarası *numarası* önceden derlenmiş üst bilgi eşleşmiyor <sup>14.3</sup>|
|C4605 (düzey 1)|' /D*makrosu*' geçerli bir komut satırında belirtilen ancak ne zaman önceden derlenmiş üst bilgi oluşturulmuş belirtilmedi|
|[C4608](../error-messages/compiler-warnings/compiler-warning-level-3-c4608.md) (Düzey 3)|'*union_member*'Başlatıcı listesindeki başka bir birleşim üyesi tarafından başlatılmış'*union_member*' <sup>işle</sup>|
|[C4619](../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md) (Düzey 3)|#pragma uyarısı: uyarı numarası'yok '*sayı*'|
|[C4623](../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md) (düzey 4)|'derived class': bir taban sınıf varsayılan oluşturucusuna erişilemediğinden varsayılan oluşturucu üretilemedi|
|[C4625](../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md) (düzey 4)|'derived class': bir taban sınıf kopya oluşturucusuna erişilemediğinden kopya oluşturucu üretilemedi|
|[C4626](../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md) (düzey 4)|'derived class': bir taban sınıf atama işlecine erişilemediğinden atama işleci üretilemedi|
|[C4628](../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md) (düzey 1)|-Ze ile digraf kullanılması desteklenmez. Karakter dizisi '*digraph*'için alternatif bir belirteç olarak yorumlanmadı'*char*'|
|[C4640](../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md) (Düzey 3)|'*örneği*': yerel durağan nesnenin yapımı iş parçacığı güvenli değil|
|C4647 (Düzey 3)|davranış değişikliği: __is_pod (*türü*) önceki sürümlerde farklı değere sahip|
|C4654 (düzey 4)|Önce yerleştirilmiş kod içeren önceden derlenmiş üst bilgi satırı yok sayılacak. Kodu önceden derlenmiş üst bilgiye ekleyin. <sup>14.1</sup>|
|[C4668](../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md) (düzey 4)|'*sembol*'için '0' ile değiştirerek önişlemci makrosu olarak tanımlanmamış '*yönergeleri*'|
|[C4682](../error-messages/compiler-warnings/compiler-warning-level-4-c4682.md) (düzey 4)|'*sembol*': [in] varsayarak, hiçbir parametre özniteliği belirtilmedi|
|[C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md) (Düzey 3)|'*kullanıcı tanımlı tür*': davranışta olası bir değişiklik, udt'de değişiklik iade çağırma kuralı|
|[C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) (düzey 1)|'*işlevi*': özel üyenin olmayan imzası derleme özel yerel türünü içeriyor '*native_type*'|
|[C4710](../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md) (düzey 4)|'*işlevi*': işlev alınmadı|
|[C4738](../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md) (Düzey 3)|32 bit kayan sonuç bellekte depolanıyor, olası performans kaybı|
|[C4746](../error-messages/compiler-warnings/compiler-warning-c4746.md)|Geçici Erişim '*ifade*' / volatile tabi olduğu:\<ISO&#124;ms > ayarı; iç işlevleri __iso_volatile_load depolama kullanmayı düşünün|
|C4749 (düzey 4)|koşullu olarak desteklenir: olmayan Düzen standart türe uygulanan'offsetof '*türü*'|
|C4767 (düzey 4)|Bölüm adı '*sembol*' 8 karakterden daha uzun ve bağlayıcı tarafından kesilecek|
|C4768 (level 3)|bağlantı belirtiminden önceki __declspec öznitelikleri yoksayılır|
|C4774 (düzey 4)|'*dize*': biçim dizesi bağımsız değişkeninde beklenen *numarası* bir dize sabit değeri değil|
|C4777 (düzey 4)|'*işlevi*': biçim dizesi '*dize*'türünde bir bağımsız değişken gerektirir'*type1*', ancak değişen sayıda bağımsız değişkeni *numarası* türüne sahip '*type2*'|
|C4786 (Düzey 3)|'*sembol*': nesne adı kesildi '*sayı*' hata ayıklama bilgileri karakter|
|[C4820](../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md) (düzey 4)|'*bayt*'bayt doldurma eklenen sonra yapı'*member_name*'|
|C4826 (Düzey 2)|Dönüştürme işlemi '*type1*'to'*type2*' işaret genişletilmiş. Bu, beklenmeyen çalışma zamanı davranışına neden olabilir.|
|C4837 (düzey 4)|Üçlü harf algılandı: '?? *karakter*'yerine'*karakter*'|
|C4841 (düzey 4)|Standart olmayan uzantı kullanıldı: kullanılan offsetof içinde bileşik üye göstergesi|
|C4842 (düzey 4)|birden fazla devralma kullanılarak bir türe uygulanan'offsetof ' sonucunun derleyici yayınları arasında tutarlı olması garanti edilmez|
|[C4868](../error-messages/compiler-warnings/compiler-warning-c4868.md) (düzey 4)|'_dosya_(*line_number*)' derleyici küme ayracıyla belirtilen başlatma listesi soldan sağa Değerlendirme sırasını zorla|
|[C4905](../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md) (düzey 1)|geniş düz dize 'LPSTR' değerine atandı|
|[C4906](../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md) (düzey 1)|düz dize 'LPWSTR' değerine atandı|
|[C4917](../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md) (düzey 1)|'*bildirimci*': bir GUID yalnızca bir sınıf, arabirim veya ad alanı ile ilişkilendirilebilir.|
|[C4928](../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md) (düzey 1)|hatalı kopya başlatma; birden çok kullanıcı tanımlı dönüştürme örtük olarak uygulandı|
|[C4931](../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md) (düzey 4)|tür kitaplığının sayı bit işaretçiler için oluşturulduğunu varsayıyoruz|
|[C4946](../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md) (düzey 1)|reinterpret_cast ilgili sınıflar arasında kullanıldı: '*class1*'ve'*class2*'|
|C4962|'*işlevi*': iyileştirmeler profil verilerinin tutarsız olmasına yol açtığı için devre dışı profil temelli iyileştirmeler|
|[C4986](../error-messages/compiler-warnings/compiler-warning-c4986.md) (düzey 4)|'*sembol*': özel durum belirtimi, önceki bildirimle eşleşmiyor|
|C4987 (düzey 4)|standart olmayan uzantı kullanıldı: 'throw (...)'|
|C4988 (düzey 4)|'*sembol*': değişken sınıf/işlev kapsamının dışında bildirildi|
|C5022|'*türü*': belirtilen birden fazla taşıma oluşturucuları|
|C5023|'*türü*': belirtilen birden fazla taşıma atama işleçleri|
|C5024 (düzey 4)|'*türü*': taşıma Oluşturucusu örtük bir şekilde silindi olarak tanımlandı|
|C5025 (düzey 4)|'*türü*': taşıma atama işleci örtük bir şekilde silindi olarak tanımlandı|
|C5026 (düzey 1 ve düzey 4)|'*türü*': taşıma Oluşturucusu örtük bir şekilde silindi olarak tanımlandı|
|C5027 (düzey 1 ve düzey 4)|'*türü*': taşıma atama işleci örtük bir şekilde silindi olarak tanımlandı|
|C5029 (düzey 4)|Standart olmayan uzantı kullanıldı: C++ hizalama öznitelikleri değişkenlere, veri üyelerine ve etiket türlerine uygulanır|
|C5031 (düzey 4)|#pragma warning(pop): olası uyuşmazlık, farklı bir dosyada atılan uyarı durumu geri çağrılıyor <sup>14.1</sup>|
|C5032 (düzey 4)|Algılanan hiçbir karşılık gelen #pragma warning(pop) olmayan #pragma <sup>14.1</sup>|
|C5034|İç Kullan '*iç*' neden işlevi *işlevi* Konuk kodu derlenmesine <sup>15.3</sup>|
|C5035|özelliğini '*özellik*' neden işlevi *işlevi* Konuk kodu derlenmesine <sup>15.3</sup>|
|C5036 (düzey 1)|VarArgs işlev işaretçisi dönüştürme x86arm64 ile derleme yapılırken '*type1*'to'*type2*' <sup>15.3</sup>|
|[C5038](../error-messages/compiler-warnings/c5038.md) (düzey 4)|veri üyesi '*Üye1*'veri üyesi sonra başlatılacak'*üye2*' <sup>15.3</sup>|
|C5039 (düzey 4)|'*işlevi*': - EHc altında extern C işlevine işaretçi veya başvuru için büyük olasılıkla işlev özel durum atma geçirildi. Bu işlev bir özel durum oluşturursa tanımsız davranış ortaya çıkabilir. <sup>15.5</sup>|
|C5042 (Düzey 3)|'*işlevi*': blok kapsamındaki işlev bildirimleri, standart C++'da belirtilen 'inline' olamaz; 'inline' tanımlayıcısını kaldırın <sup>15.5</sup>|
|[C5045](../error-messages/compiler-warnings/c5045.md)|Derleyici/qspectre anahtarı belirtilmişse bellek yükü için Spectre risk azaltma ekler <sup>15.7</sup>|

<sup>14.1</sup> bu uyarı, Visual Studio 2015 güncelleştirme 1'den itibaren kullanılabilmektedir.<br/>
<sup>14.3</sup> bu uyarı, Visual Studio 2015 güncelleştirme 3'te ' den itibaren kullanılabilmektedir.<br/>
<sup>15.3</sup> bu uyarı, Visual Studio 2017 sürüm 15.3'den itibaren kullanılabilmektedir.<br/>
<sup>15.5</sup> bu uyarı, Visual Studio 2017 15.5 sürümünden itibaren kullanılabilir.<br/>
<sup>15.7</sup> bu uyarı, Visual Studio 2017 sürüm 15.7'den itibaren kullanılabilmektedir.<br/>
<sup>Kalıcı</sup> bu uyarıyı devre dışı olduğu sürece [/ permissive-](../build/reference/permissive-standards-conformance.md) derleyici seçeneği ayarlanır.<br/>

## <a name="warnings-off-by-default-in-earlier-versions"></a>Önceki sürümlerde varsayılan olarak kapalı uyarıları

Visual Studio 2015 önce derleyici sürümlerinde varsayılan olarak kapalı uyarıları şöyleydi:

|||
|-|-|
|[C4302](../error-messages/compiler-warnings/compiler-warning-level-2-c4302.md) (Düzey 2)|'*dönüştürme*': kesildi '*type1*'to'*type2*'|
|[C4311](../error-messages/compiler-warnings/compiler-warning-level-1-c4311.md) (düzey 1)|'*değişkeni*': işaretçi kesilmesi'öğesinden '*türü*'to'*türü*'|
|[C4312](../error-messages/compiler-warnings/compiler-warning-level-1-c4312.md) (düzey 1)|'*işlemi*': dönüştürme '*type1*'to'*type2*' daha büyük boyutlu|
|[C4319](../error-messages/compiler-warnings/compiler-warning-level-1-c4319.md) (düzey 1)|'*işleci*': sıfır genişletme '*type1*'to'*type2*' daha büyük boyutlu|

Bu uyarı, derleyici önce Visual Studio 2012 sürümlerinde varsayılan olarak kapalı şöyleydi:

|||
|-|-|
|[C4431](../error-messages/compiler-warnings/compiler-warning-level-4-c4431.md) (düzey 4)|tür belirticisi eksik - int varsayıldı. Not: C artık varsayılan int desteği içermiyor|

## <a name="see-also"></a>Ayrıca Bkz.

[warning](../preprocessor/warning.md)