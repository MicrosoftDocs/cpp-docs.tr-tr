---
title: Derleyici hataları C3000 C3099 aracılığıyla | Microsoft Docs
ms.custom: ''
ms.date: 11/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
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
dev_langs:
- C++
ms.assetid: 01b7b9cb-b351-4b5a-8cb0-1fcddb08d2ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0941b2bd6b998e8beb18fa7e5960aa93beb6a80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284725"
---
# <a name="compiler-errors-c3000-through-c3099"></a>Derleyici hataları C3000 C3099 aracılığıyla

Bu bölümdeki makaleleri belgelerin derleyici tarafından oluşturulan hata iletileri kümesini açıklayın.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Hata iletileri

|Hata|İleti|
|-----------|-------------|
|Derleyici Hatası C3000|Kullanımdan kalktı.|
|[Derleyici Hatası C3001](compiler-error-c3001.md)|'*ileti*': bir OpenMP yönergesi adı bekleniyor|
|[Derleyici Hatası C3002](compiler-error-c3002.md)|'*Ad1* *ad2*': birden çok OpenMP yönergesi adları|
|[Derleyici Hatası C3003](compiler-error-c3003.md)|'*yönergesi*': OpenMP yönergesi adı sonra yönerge yan tümcelerinde izin verilmiyor|
|[Derleyici Hatası C3004](compiler-error-c3004.md)|'*yan tümcesi*': yan tümcesi OpenMP üzerinde geçerli değil '*yönergesi*' yönergesi|
|[Derleyici Hatası C3005](compiler-error-c3005.md)|'*ileti*': OpenMP üzerinde karşılaştı beklenmeyen belirteç '*yönergesi*' yönergesi|
|[Derleyici Hatası C3006](compiler-error-c3006.md)|'*yan tümcesi*': OpenMP yan tümcesinde '*yönergesi*' yönergesi beklenen bağımsız değişken eksik|
|[Derleyici Hatası C3007](compiler-error-c3007.md)|'*yan tümcesi*': OpenMP yan tümcesinde '*yönergesi*' yönergesi bağımsız değişkeni olmaz|
|[Derleyici Hatası C3008](compiler-error-c3008.md)|*bağımsız değişkeni*': bağımsız değişken kapanış eksik ')' OpenMP üzerinde '*yönergesi*' yönergesi|
|[Derleyici Hatası C3009](compiler-error-c3009.md)|'*etiket*': OpenMP yapılandırılmış bloğu izin içine atlama|
|[Derleyici Hatası C3010](compiler-error-c3010.md)|'*etiket*': OpenMP yapılandırılmış blok izin dışında atlama|
|[Derleyici Hatası C3011](compiler-error-c3011.md)|Satır içi derleme doğrudan paralel bir bölge içinde izin verilmiyor|
|[Derleyici Hatası C3012](compiler-error-c3012.md)|'*işlevi*': doğrudan paralel bir bölge içinde izin verilmiyor iç işlevi|
|[Derleyici Hatası C3013](compiler-error-c3013.md)|'*yan tümcesi*': yan tümcesi yalnızca görünebilir kez OpenMP üzerinde '*yönergesi*' yönergesi|
|[Derleyici Hatası C3014](compiler-error-c3014.md)|Beklenen bir OpenMP aşağıdaki döngünün '*yönergesi*' yönergesi|
|[Derleyici Hatası C3015](compiler-error-c3015.md)|OpenMP başlatma 'için' deyimi yanlış biçime sahip|
|[Derleyici Hatası C3016](compiler-error-c3016.md)|'*tanımlayıcısı*': 'için' deyimi OpenMP dizin değişken tamsayı türü imzalı|
|[Derleyici Hatası C3017](compiler-error-c3017.md)|OpenMP sonlandırma testinde 'için' deyimi yanlış biçime sahip|
|[Derleyici Hatası C3018](compiler-error-c3018.md)|'*tanımlayıcısı*': 'için' test veya artan OpenMP dizin değişkeni kullanmalıdır '*değişkeni*'|
|[Derleyici Hatası C3019](compiler-error-c3019.md)|OpenMP aralıkla 'için' deyimi yanlış biçime sahip|
|[Derleyici Hatası C3020](compiler-error-c3020.md)|'*değişkeni*': OpenMP dizin değişkeni 'için' döngü döngü gövdesine değiştirilemez|
|[Derleyici Hatası C3021](compiler-error-c3021.md)|'*bağımsız değişkeni*': OpenMP üzerinde boş olmayan bağımsız değişken '*yönergesi*' yönergesi|
|[Derleyici Hatası C3022](compiler-error-c3022.md)|'*yönergesi*': Geçersiz zamanlama türü, '*yönergesi*'üzerinde OpenMP'*yönergesi*' yönergesi|
|[Derleyici Hatası C3023](compiler-error-c3023.md)|'*bağımsız değişkeni*': OpenMP bağımsız değişkende karşılaştı beklenmeyen belirteç '*yönergesi*' yan tümcesi|
|[Derleyici Hatası C3024](compiler-error-c3024.md)|'schedule(runtime)': chunk_size ifade izin verilmiyor|
|[Derleyici Hatası C3025](compiler-error-c3025.md)|'*yan tümcesi*': tam sayı ifade bekleniyordu|
|[Derleyici Hatası C3026](compiler-error-c3026.md)|'*yan tümcesi*': sabit ifadesi pozitif olmalıdır|
|[Derleyici Hatası C3027](compiler-error-c3027.md)|'*yan tümcesi*': aritmetik veya işaretçi ifade bekleniyordu|
|[Derleyici Hatası C3028](compiler-error-c3028.md)|'*üye*': bir veri paylaşımı yan tümcesinde yalnızca bir değişken ya da statik veri üyesi kullanılabilir|
|[Derleyici Hatası C3029](compiler-error-c3029.md)|'*sembol*': yalnızca bir kez veri Paylaşımı'görünebilir yan tümcelerinde OpenMP yönergesi|
|[Derleyici Hatası C3030](compiler-error-c3030.md)|'*tanımlayıcısı*': değişkeni '*yönergesi*' yan tümcesi/yönergesi başvuru türüne sahip olamaz|
|[Derleyici Hatası C3031](compiler-error-c3031.md)|'*tanımlayıcısı*': 'azaltma' yan tümcesinde değişkeni skaler aritmetik türe sahip olmalıdır|
|[Derleyici Hatası C3032](compiler-error-c3032.md)|'*tanımlayıcısı*': değişkeni '*yan tümcesi*'yan tümcesi eksik türü olamaz'*türü*'|
|[Derleyici Hatası C3033](compiler-error-c3033.md)|'*tanımlayıcısı*': değişkeni '*yan tümcesi*' yan tümcesi const nitelenmiş tür sahip olamaz|
|[Derleyici Hatası C3034](compiler-error-c3034.md)|OpenMP '*yönergesi*'yönergesi doğrudan iç içe geçirilemez içinde'*yönergesi*' yönergesi|
|[Derleyici Hatası C3035](compiler-error-c3035.md)|OpenMP 'sıralı' yönergesi gerekir bağlamak doğrudan 'İçin' veya 'için parallel' 'sıralı' yan tümcesi ile yönergesi|
|[Derleyici Hatası C3036](compiler-error-c3036.md)|'*yan tümcesi*': OpenMP 'azaltma' yan tümcesinde geçersiz işleç simgesi|
|[Derleyici Hatası C3037](compiler-error-c3037.md)|'*tanımlayıcısı*': değişkeni '*yan tümcesi*' yan tümcesi içeriği kapsayan paylaşılabilecek gerekir|
|[Derleyici Hatası C3038](compiler-error-c3038.md)|'*tanımlayıcısı*': 'özel' yan tümcesinde değişkeni, içeriği kapsayan içinde azaltma değişkeni olamaz|
|[Derleyici Hatası C3039](compiler-error-c3039.md)|'*tanımlayıcısı*': 'için' deyimi OpenMP dizin değişken azaltma değişkeni olamaz|
|[Derleyici Hatası C3040](compiler-error-c3040.md)|'*tanımlayıcısı*': 'azaltma' yan tümcesinde değişkeninin türü, azaltma işleci ile uyumlu değil '*işleci*'|
|[Derleyici Hatası C3041](compiler-error-c3041.md)|'*tanımlayıcısı*': 'copyprivate' yan tümcesinde değişkeni içeriği kapsayan özel olmalıdır|
|[Derleyici Hatası C3042](compiler-error-c3042.md)|'copyprivate' ve 'nowait' yan tümceleri üzerinde OpenMP birlikte bulunamaz '*yönergesi*' yönergesi|
|[Derleyici Hatası C3043](compiler-error-c3043.md)|OpenMP 'kritik' yönergesi aynı ada sahip 'kritik' yönergesinde iç içe olamaz|
|[Derleyici Hatası C3044](compiler-error-c3044.md)|'bölüm': yalnızca doğrudan bir OpenMP 'bölüm' yönergesi altında iç içe geçmiş|
|[Derleyici Hatası C3045](compiler-error-c3045.md)|Bileşik deyim beklenen OpenMP 'bölüm' yönergesi aşağıdaki. Eksik ' {'|
|[Derleyici Hatası C3046](compiler-error-c3046.md)|OpenMP '#pragma omp bölümler' bölgede yapılandırılmış blok eksik|
|[Derleyici Hatası C3047](compiler-error-c3047.md)|'Bölüm' bölge '#pragma omp bölümü tarafından' gelmelidir OpenMP yapılandırılmış bloğunda|
|[Derleyici Hatası C3048](compiler-error-c3048.md)|'#Pragma omp atomik' aşağıdaki ifade yanlış biçime sahiptir|
|[Derleyici Hatası C3049](compiler-error-c3049.md)|'*bağımsız değişkeni*': OpenMP 'default' yan tümcesinde geçersiz bağımsız değişken|
|[Derleyici Hatası C3050](compiler-error-c3050.md)|'*sınıfı*': ref sınıfı devralınmalıdır olamaz '*tanımlayıcısı*'|
|Derleyici Hatası C3051|Kullanımdan kalktı.|
|[Derleyici Hatası C3052](compiler-error-c3052.md)|'*tanımlayıcısı*': değişken veri paylaşımı yan default(none) yan tümcesi altında görünmüyor|
|[Derleyici Hatası C3053](compiler-error-c3053.md)|'*tanımlayıcısı*': 'threadprivate' geçerli yalnızca genel veya statik veri öğeleri için|
|[Derleyici Hatası C3054](compiler-error-c3054.md)|bir genel bir sınıf veya işlevi '#pragma omp paralel' şu anda desteklenmiyor|
|[Derleyici Hatası C3055](compiler-error-c3055.md)|'*tanımlayıcısı*': 'threadprivate' yönergesinde kullanılmadan önce sembol başvurulamaz|
|[Derleyici Hatası C3056](compiler-error-c3056.md)|'*tanımlayıcısı*': simgesi değil 'threadprivate' yönergesi ile aynı kapsamda|
|[Derleyici Hatası C3057](compiler-error-c3057.md)|'*tanımlayıcısı*': 'threadprivate' simgelerin dinamik başlatma şu anda desteklenmiyor|
|[Derleyici Hatası C3058](compiler-error-c3058.md)|'*tanımlayıcısı*': 'copyin' yan tümcesinde kullanılmadan önce 'threadprivate' bildirilmemiş simgesi|
|[Derleyici Hatası C3059](compiler-error-c3059.md)|'*tanımlayıcısı*': 'threadprivate' simgesi kullanılamaz '*yan tümcesi*' yan tümcesi|
|[Derleyici Hatası C3060](compiler-error-c3060.md)|'*tanımlayıcısı*': arkadaş işlevi (bunu yalnızca bildirilebilir) bir tam ad kullanmayı bir sınıf içinde tanımlanmamış|
|Derleyici Hatası C3061|işleç '*işleci*': numaralandırma üzerinde izin verilmiyor '*türü*'türündeki temel alınan'*türü*'|
|[Derleyici Hatası C3062](compiler-error-c3062.md)|'*tanımlayıcısı*': Numaralandırıcı gerektirir değeri temel alınan türü olduğundan '*türü*'|
|[Derleyici Hatası C3063](compiler-error-c3063.md)|işleç '*işleci*': tüm işlenenleri aynı numaralandırma türü olmalıdır|
|Derleyici Hatası C3064|'*tanımlayıcısı*': basit bir tür olması veya bir çözmek gerekir|
|[Derleyici Hatası C3065](compiler-error-c3065.md)|özellik bildirimi sınıfı olmayan kapsamında izin verilmiyor|
|[Derleyici Hatası C3066](compiler-error-c3066.md)|Bu tür bir nesne çağrılabilir birden çok yolla bu bağımsız değişken|
|Derleyici Hatası C3067|Başlatıcı listesi kullanılamaz [] ile yerleşik işleci|
|[Derleyici Hatası C3068](compiler-error-c3068.md)|'*tanımlayıcısı*': 'naked' işlevi bir C++ özel durum oluştuysa, geriye doğru izleme gerektirecek nesneleri içeremez|
|[Derleyici Hatası C3069](compiler-error-c3069.md)|işleç '*işleci*': numaralandırma türü için izin verilmiyor|
|[Derleyici Hatası C3070](compiler-error-c3070.md)|'*tanımlayıcısı*': özelliği bir 'set' yöntemi yok|
|[Derleyici Hatası C3071](compiler-error-c3071.md)|işleç '*işleci*' ref sınıfı ya da bir değer türü örneği için yalnızca uygulanabilir|
|[Derleyici Hatası C3072](compiler-error-c3072.md)|işleç '*işleci*' birli '%' işleci bir ref örneği dönüştürmek için sınıf bir tanıtıcı türü ref sınıfı kullanım örneği uygulanamaz|
|[Derleyici Hatası C3073](compiler-error-c3073.md)|'*tanımlayıcısı*': ref sınıfı, kullanıcı tanımlı kopya oluşturucu yok|
|Derleyici Hatası C3074|parantez içine alınmış Başlatıcısı ile bir dizi başlatılamaz|
|[Derleyici Hatası C3075](compiler-error-c3075.md)|'*tanımlayıcısı*': başvuru türünde bir örnek eklenemiyor '*türü*', değer türü|
|[Derleyici Hatası C3076](compiler-error-c3076.md)|'*tanımlayıcısı*': başvuru türünde bir örnek eklenemiyor '*türü*', yerel tür içinde|
|[Derleyici Hatası C3077](compiler-error-c3077.md)|'*tanımlayıcısı*': bir sonlandırıcı yalnızca bir başvuru türü üyesi olabilir|
|Derleyici Hatası C3078|dizi boyutu yeni ifadelerinde belirtilmelidir|
|Derleyici Hatası C3079|Başlatıcı Listesi Bu atama işlecinin sağ işleneni olarak kullanılamaz|
|[Derleyici Hatası C3080](compiler-error-c3080.md)|'*sonlandırıcıyı*': bir sonlandırıcı depolama-sınıfı-tanımlayıcısı olamaz|
|Derleyici Hatası C3081|Kullanımdan kalktı.|
|Derleyici Hatası C3082|Kullanımdan kalktı.|
|[Derleyici Hatası C3083](compiler-error-c3083.md)|'*tanımlayıcısı*': simgenin sol tarafındaki bir '::' bir tür olmalıdır|
|[Derleyici Hatası C3084](compiler-error-c3084.md)|'*tanımlayıcısı*': yıkıcı/sonlandırıcıyı olamaz '*anahtar sözcüğü*'|
|[Derleyici Hatası C3085](compiler-error-c3085.md)|'*tanımlayıcısı*': bir oluşturucu olamaz '*anahtar sözcüğü*'|
|Derleyici Hatası C3086|'std::initializer_list' bulunamıyor: yapmanız # < initializer_list > include|
|[Derleyici Hatası C3087](compiler-error-c3087.md)|'*tanımlayıcısı*': çağrısı '*bildirimi*' zaten bu üye başlatır|
|Derleyici Hatası C3088|'*sınıfı*': öznitelik oluşturucunun biçimsel bağımsız değişkenler adlı|
|Derleyici Hatası C3089|'*tanımlayıcısı*': parametre adı hiçbir veri üyenin adını eşleşmiyor|
|Derleyici Hatası C3090|'*sınıfı*': öznitelik sınıfı, bir şablon olamaz|
|Derleyici Hatası C3091|'*sınıfı*': öznitelik sınıfı, temel sınıflar olamaz|
|Derleyici Hatası C3092|'*sınıfı*': öznitelik sınıfı üyesi biraz alan, 'static' veya 'const' olamaz|
|Derleyici Hatası C3093|'*türü*': öznitelik sınıfı üyesi için izin verilmiyor türü '*üye*'|
|[Derleyici Hatası C3094](compiler-error-c3094.md)|'*özniteliği*': anonim kullanım izin verilmiyor|
|[Derleyici Hatası C3095](compiler-error-c3095.md)|'*özniteliği*': öznitelik olamaz yinelenen|
|[Derleyici Hatası C3096](compiler-error-c3096.md)|'*özniteliği*': yalnızca öznitelik sınıfları veri üyeleri özniteliği izin verilir|
|[Derleyici Hatası C3097](compiler-error-c3097.md)|'*özniteliği*': öznitelik kapsamı, ile ' derleme:' veya ' modül:'|
|Derleyici Hatası C3098|'*tanımlayıcısı*': özniteliğine sahip kullanıcı tanımlı oluşturucu yok|
|[Derleyici Hatası C3099](compiler-error-c3099.md)|'*anahtar sözcüğü*': kullanma [System::AttributeUsageAttribute] / [Windows::Foundation::Metadata::AttributeUsageAttribute] yönetilen WinRT öznitelikleri|
