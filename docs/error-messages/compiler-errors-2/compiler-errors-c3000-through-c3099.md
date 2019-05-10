---
title: C3000 ile C3099 arasındaki derleyici hataları
ms.date: 04/21/2019
f1_keywords:
- C3051
- C3061
- C3064
- C3067
- C3074
- C3078
- C3079
- C3081
- C3082
- C3086
- C3088
- C3089
- C3090
- C3091
- C3092
- C3093
- C3098
helpviewer_keywords:
- C3051
- C3061
- C3064
- C3067
- C3074
- C3078
- C3079
- C3081
- C3082
- C3086
- C3088
- C3089
- C3090
- C3091
- C3092
- C3093
- C3098
ms.assetid: 01b7b9cb-b351-4b5a-8cb0-1fcddb08d2ab
ms.openlocfilehash: 08c7b691d6390e6c1070fc71dff116604731ebab
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64856919"
---
# <a name="compiler-errors-c3000-through-c3099"></a>C3000 ile C3099 arasındaki derleyici hataları

Belgelerin bu bölümdeki makaleleri bir alt kümesini derleyici tarafından oluşturulan hata iletilerini açıklayın.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Hata iletileri

|Hata|`Message`|
|-----------|-------------|
|Derleyici Hatası C3000|Kullanımdan kalktı.|
|[Derleyici Hatası C3001](compiler-error-c3001.md)|'*ileti*': OpenMP yönergesi adı bekleniyor|
|[Derleyici Hatası C3002](compiler-error-c3002.md)|'*name1* *name2*': birden fazla OpenMP yönergesi adı|
|[Derleyici Hatası C3003](compiler-error-c3003.md)|'*yönergesi*': OpenMP yönergesi adına yönerge yan tümcelerinden sonra izin verilmiyor|
|[Derleyici Hatası C3004](compiler-error-c3004.md)|'*yan tümcesi*': yan tümce OpenMP'üzerinde geçerli değil '*yönergesi*' yönergesi|
|[Derleyici Hatası C3005](compiler-error-c3005.md)|'*ileti*': beklenmeyen belirteçle karşılaşıldı üzerinde OpenMP '*yönergesi*' yönergesi|
|[Derleyici Hatası C3006](compiler-error-c3006.md)|'*yan tümcesi*': OpenMP yan tümcesinde '*yönergesi*' yönergesi, beklenen bağımsız değişken eksik|
|[Derleyici Hatası C3007](compiler-error-c3007.md)|'*yan tümcesi*': OpenMP yan tümcesinde '*yönergesi*' yönergesi, bir bağımsız değişken almaz|
|[Derleyici Hatası C3008](compiler-error-c3008.md)|*bağımsız değişken*': bağımsız değişken eksik kapanış ')' OpenMP üzerinde '*yönergesi*' yönergesi|
|[Derleyici Hatası C3009](compiler-error-c3009.md)|'*etiket*': OpenMP yapısal bloğunun izin içine atlamaya|
|[Derleyici Hatası C3010](compiler-error-c3010.md)|'*etiket*': OpenMP yapısal bloğunun izin dışına atlamaya|
|[Derleyici Hatası C3011](compiler-error-c3011.md)|Satır içi derleme doğrudan bir paralel bölgenin içinde izin verilmiyor|
|[Derleyici Hatası C3012](compiler-error-c3012.md)|'*işlevi*': iç işlev doğrudan bir paralel bölgenin içinde izin verilmiyor|
|[Derleyici Hatası C3013](compiler-error-c3013.md)|'*yan tümcesi*': yan tümcesi yalnızca görüntülenebilir kez üzerinde OpenMP '*yönergesi*' yönergesi|
|[Derleyici Hatası C3014](compiler-error-c3014.md)|Beklenen bir for döngüsü aşağıdaki OpenMP '*yönergesi*' yönergesi|
|[Derleyici Hatası C3015](compiler-error-c3015.md)|başlatma OpenMP 'for' deyimindeki hatalı biçimde|
|[Derleyici Hatası C3016](compiler-error-c3016.md)|'*tanımlayıcı*': OpenMP 'for' deyimindeki dizin değişkeni integral türünün işaretli gerekir|
|[Derleyici Hatası C3017](compiler-error-c3017.md)|OpenMP 'for' deyimindeki sonlandırma sınaması hatalı biçimde|
|[Derleyici Hatası C3018](compiler-error-c3018.md)|'*tanımlayıcı*': OpenMP 'for' sınama veya artırma dizin değişkeni kullanılmalıdır '*değişkeni*'|
|[Derleyici Hatası C3019](compiler-error-c3019.md)|OpenMP 'for' deyimindeki artış hatalı biçimde|
|[Derleyici Hatası C3020](compiler-error-c3020.md)|'*değişkeni*': OpenMP 'for' döngüsünün dizin değişkeni döngü gövdesi içinde değiştirilemez|
|[Derleyici Hatası C3021](compiler-error-c3021.md)|'*bağımsız değişken*': OpenMP üzerinde boş olmayan bağımsız değişken '*yönergesi*' yönergesi|
|[Derleyici Hatası C3022](compiler-error-c3022.md)|'*yönergesi*': Geçersiz zamanlama türü, '*yönergesi*'on OpenMP'*yönergesi*' yönergesi|
|[Derleyici Hatası C3023](compiler-error-c3023.md)|'*bağımsız değişken*': beklenmeyen belirteçle karşılaşıldı OpenMP bağımsız değişkende '*yönergesi*' yan tümcesi|
|[Derleyici Hatası C3024](compiler-error-c3024.md)|'schedule(runtime)': chunk_size ifadesine izin verilmez|
|[Derleyici Hatası C3025](compiler-error-c3025.md)|'*yan tümcesi*': tam sayı ifade bekleniyor|
|[Derleyici Hatası C3026](compiler-error-c3026.md)|'*yan tümcesi*': sabit ifade pozitif olmalıdır|
|[Derleyici Hatası C3027](compiler-error-c3027.md)|'*yan tümcesi*': aritmetik veya işaretçi ifadesi bekleniyor|
|[Derleyici Hatası C3028](compiler-error-c3028.md)|'*üye*': bir veri paylaşımı yan tümcesinde yalnızca bir değişken veya statik veri üyesi kullanılabilir|
|[Derleyici Hatası C3029](compiler-error-c3029.md)|'*sembol*': yalnızca bir kez veri paylaşımı içinde görünebilir yan tümceleri OpenMP yönergesi|
|[Derleyici Hatası C3030](compiler-error-c3030.md)|'*tanımlayıcı*': değişken, '*yönergesi*' yan tümcesi/yönergesi, başvuru türüne sahip olamaz|
|[Derleyici Hatası C3031](compiler-error-c3031.md)|'*tanımlayıcı*': 'reduction' yan tümcesindeki değişken skalar aritmetik türünde olmalıdır|
|[Derleyici Hatası C3032](compiler-error-c3032.md)|'*tanımlayıcı*': değişken, '*yan tümcesi*'yan tümcesi eksik tür olamaz'*türü*'|
|[Derleyici Hatası C3033](compiler-error-c3033.md)|'*tanımlayıcı*': değişken, '*yan tümcesi*' yan tümcesi, const nitelenmiş türde olamaz|
|[Derleyici Hatası C3034](compiler-error-c3034.md)|OpenMP '*yönergesi*'yönergesi doğrudan iç içe geçirilemez içinde'*yönergesi*' yönergesi|
|[Derleyici Hatası C3035](compiler-error-c3035.md)|OpenMP 'ordered' yönergesi gereken bağlama doğrudan bir 'for' veya 'parallel for' yönergesi 'ordered' yan tümcesiyle|
|[Derleyici Hatası C3036](compiler-error-c3036.md)|'*yan tümcesi*': OpenMP 'reduction' yan tümcesinde geçersiz işleç belirteci|
|[Derleyici Hatası C3037](compiler-error-c3037.md)|'*tanımlayıcı*': değişken, '*yan tümcesi*' yan tümcesi kapsayan bağlamda paylaşılabilir olmalıdır|
|[Derleyici Hatası C3038](compiler-error-c3038.md)|'*tanımlayıcı*': 'private' yan tümcesindeki değişken kapsayan bağlamda bir azaltma değişkeni olamaz|
|[Derleyici Hatası C3039](compiler-error-c3039.md)|'*tanımlayıcı*': OpenMP 'for' deyimindeki dizin değişkeni bir azaltma değişkeni olamaz|
|[Derleyici Hatası C3040](compiler-error-c3040.md)|'*tanımlayıcı*': 'reduction' yan tümcesindeki değişken türünde azaltma işleciyle uyumsuz '*işleci*'|
|[Derleyici Hatası C3041](compiler-error-c3041.md)|'*tanımlayıcı*': 'copyprivate' yan tümcesindeki değişken kapsayan bağlamda özel olmalıdır|
|[Derleyici Hatası C3042](compiler-error-c3042.md)|'copyprivate' ve 'nowait' yan tümceleri OpenMP üzerinde birlikte bulunamaz '*yönergesi*' yönergesi|
|[Derleyici Hatası C3043](compiler-error-c3043.md)|OpenMP 'critical' yönergesi 'critical' yönergesi aynı ada sahip iç içe olamaz|
|[Derleyici Hatası C3044](compiler-error-c3044.md)|'bölüm': yalnızca bir OpenMP 'sections' yönergesinin altında doğrudan iç içe|
|[Derleyici Hatası C3045](compiler-error-c3045.md)|Bir bileşik deyim bekleniyordu OpenMP 'sections' yönergesinden sonra. Eksik ' {'|
|[Derleyici Hatası C3046](compiler-error-c3046.md)|Bir OpenMP '#pragma omp sections' bölgesinde yapısal blok eksik|
|[Derleyici Hatası C3047](compiler-error-c3047.md)|Yapısal bloğunun bir OpenMP 'sections' bölgesindeki '#pragma omp section' gelmelidir|
|[Derleyici Hatası C3048](compiler-error-c3048.md)|'#Pragma omp atomic' sonrasındaki ifade hatalı biçimde|
|[Derleyici Hatası C3049](compiler-error-c3049.md)|'*bağımsız değişken*': OpenMP 'default' yan tümcesinde geçersiz bağımsız değişken|
|[Derleyici Hatası C3050](compiler-error-c3050.md)|'*sınıfı*': başvuru sınıfı devralamaz '*tanımlayıcı*'|
|Derleyici Hatası C3051|Kullanımdan kalktı.|
|[Derleyici Hatası C3052](compiler-error-c3052.md)|'*tanımlayıcı*': değişken bir default(none) yan tümcesi altında bir veri paylaşımı yan tümcesinde görünmüyor|
|[Derleyici Hatası C3053](compiler-error-c3053.md)|'*tanımlayıcı*': 'threadprivate' genel veya statik veri öğeleri için geçerlidir, yalnızca|
|[Derleyici Hatası C3054](compiler-error-c3054.md)|'#pragma omp parallel' şu anda bir genel sınıfta veya işlevde desteklenmiyor|
|[Derleyici Hatası C3055](compiler-error-c3055.md)|'*tanımlayıcı*': simge 'threadprivate' yönergesinde kullanılmadan önce başvurulamaz|
|[Derleyici Hatası C3056](compiler-error-c3056.md)|'*tanımlayıcı*': simge değil 'threadprivate' yönergesiyle aynı kapsamda|
|[Derleyici Hatası C3057](compiler-error-c3057.md)|'*tanımlayıcı*': 'threadprivate' simgelerinin dinamik olarak başlatılması şu anda desteklenmiyor|
|[Derleyici Hatası C3058](compiler-error-c3058.md)|'*tanımlayıcı*': simge 'copyin'yan içinde kullanılmadan önce 'threadprivate' olarak bildirilmedi|
|[Derleyici Hatası C3059](compiler-error-c3059.md)|'*tanımlayıcı*': 'threadprivate' simgesi kullanılamaz '*yan tümcesi*' yan tümcesi|
|[Derleyici Hatası C3060](compiler-error-c3060.md)|'*tanımlayıcı*': bir arkadaş işlev tam adı (Bu yalnızca bildirilebilir) kullanarak bir sınıf içinde tanımlanamaz|
|Derleyici Hatası C3061|işleç '*işleci*': numaralandırma üzerinde izin verilmez '*türü*'ile 'temel türü*türü*'|
|[Derleyici Hatası C3062](compiler-error-c3062.md)|'*tanımlayıcı*': temeldeki tür olduğundan Numaralandırıcı değer gerektiriyor '*türü*'|
|[Derleyici Hatası C3063](compiler-error-c3063.md)|işleç '*işleci*': tüm işlenenler aynı numaralandırma türünde olmalıdır|
|Derleyici Hatası C3064|'*tanımlayıcı*': basit bir tür olması gerekir veya çözümlenmeli|
|[Derleyici Hatası C3065](compiler-error-c3065.md)|sınıf olmayan kapsamda özellik bildirimine izin verilmez|
|[Derleyici Hatası C3066](compiler-error-c3066.md)|Bu türde bir nesne çağrılabilen birden çok yolla bu bağımsız değişken|
|Derleyici Hatası C3067|Başlatıcı listesi kullanılamaz yerleşik operator [] ile|
|[Derleyici Hatası C3068](compiler-error-c3068.md)|'*tanımlayıcı*': 'naked' işlev C++ özel durumu oluştuğunda geriye doğru izleme gerektirecek nesneler içeremez|
|[Derleyici Hatası C3069](compiler-error-c3069.md)|işleç '*işleci*': numaralandırma türü için izin verilmiyor|
|[Derleyici Hatası C3070](compiler-error-c3070.md)|'*tanımlayıcı*': özelliğin bir 'set' yöntemi yok|
|[Derleyici Hatası C3071](compiler-error-c3071.md)|işleç '*işleci*' yalnızca bir başvuru sınıfının veya değer türü örneğine uygulanabilir|
|[Derleyici Hatası C3072](compiler-error-c3072.md)|işleç '*işleci*' ref örneğini dönüştürmek için '%' birli işleci sınıfı için bir tanıtıcı türü bir başvuru sınıfı kullanım örneğine uygulanamaz|
|[Derleyici Hatası C3073](compiler-error-c3073.md)|'*tanımlayıcı*': başvuru sınıfının kullanıcı tanımlı kopya oluşturucu yok|
|Derleyici Hatası C3074|bir dizi, parantez içine alınmış Başlatıcı ile başlatılamaz|
|[Derleyici Hatası C3075](compiler-error-c3075.md)|'*tanımlayıcı*': bir başvuru türünün örneğini katıştırılamıyor '*türü*', değer türünde|
|[Derleyici Hatası C3076](compiler-error-c3076.md)|'*tanımlayıcı*': bir başvuru türünün örneğini katıştırılamıyor '*türü*', bir yerel tür içinde|
|[Derleyici Hatası C3077](compiler-error-c3077.md)|'*tanımlayıcı*': Sonlandırıcı yalnızca başvuru türünün üyesi olabilir|
|Derleyici Hatası C3078|Yeni ifadelerde dizi boyutu belirtilmelidir|
|Derleyici Hatası C3079|Başlatıcı Listesi Bu atama işlecinin sağ işleneni kullanılamaz|
|[Derleyici Hatası C3080](compiler-error-c3080.md)|'*Sonlandırıcı*': Sonlandırıcı bir depolama sınıfı belirticisine sahip olamaz|
|Derleyici Hatası C3081|Kullanımdan kalktı.|
|Derleyici Hatası C3082|Kullanımdan kalktı.|
|[Derleyici Hatası C3083](compiler-error-c3083.md)|'*tanımlayıcı*': sol tarafındaki simge bir '::' bir tür olmalıdır|
|[Derleyici Hatası C3084](compiler-error-c3084.md)|'*tanımlayıcı*': yıkıcı/sonlandırıcıda olamaz '*anahtar sözcüğü*'|
|[Derleyici Hatası C3085](compiler-error-c3085.md)|'*tanımlayıcı*': bir oluşturucu olamaz '*anahtar sözcüğü*'|
|Derleyici Hatası C3086|'std::initializer_list' bulunamıyor: ihtiyacınız #include \<initializer_list >|
|[Derleyici Hatası C3087](compiler-error-c3087.md)|'*tanımlayıcı*': çağrısı '*bildirimi*' bu üyeyi zaten başlatıyor|
|Derleyici Hatası C3088|'*sınıfı*': öznitelik oluşturucusunda biçimsel bağımsız değişkenler adlandırılmış gerekir|
|Derleyici Hatası C3089|'*tanımlayıcı*': parametre adı herhangi bir veri üyesinin adıyla eşleşmiyor|
|Derleyici Hatası C3090|'*sınıfı*': öznitelik sınıfı bir şablon olamaz|
|Derleyici Hatası C3091|'*sınıfı*': öznitelik sınıfının taban sınıfları olamaz|
|Derleyici Hatası C3092|'*sınıfı*': öznitelik sınıfı üyesi bir bit alanı, 'static' veya 'const' olamaz|
|Derleyici Hatası C3093|'*türü*': öznitelik sınıfı üyesi için izin verilmiyor türü '*üye*'|
|[Derleyici Hatası C3094](compiler-error-c3094.md)|'*özniteliği*': anonim kullanım izin verilmiyor|
|[Derleyici Hatası C3095](compiler-error-c3095.md)|'*özniteliği*': öznitelik yinelenemez|
|[Derleyici Hatası C3096](compiler-error-c3096.md)|'*özniteliği*': özniteliğe yalnızca öznitelik sınıflarının veri üyelerinde izin veriliyor|
|[Derleyici Hatası C3097](compiler-error-c3097.md)|'*özniteliği*': özniteliğin kapsamı belirlenmelidir ' derleme:' veya ' modül:'|
|Derleyici Hatası C3098|'*tanımlayıcı*': özniteliği, kullanıcı tanımlı oluşturucusu yok|
|[Derleyici Hatası C3099](compiler-error-c3099.md)|'*anahtar sözcüğü*': kullanma [System::AttributeUsageAttribute] / [Windows::Foundation::Metadata::AttributeUsageAttribute] yönetilen WinRT öznitelikleri|

## <a name="see-also"></a>Ayrıca bkz.

[C /C++ derleyicisi ve derleme araçları hataları ve Uyarıları](../compiler-errors-1/c-cpp-build-errors.md) \
[C3999 arasındaki derleyici hataları C2000-](../compiler-errors-1/compiler-errors-c2000-c3999.md)
