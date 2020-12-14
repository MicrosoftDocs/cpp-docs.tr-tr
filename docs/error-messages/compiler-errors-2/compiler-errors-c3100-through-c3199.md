---
description: 'Daha fazla bilgi edinin: C3100 Ile derleyici hataları C3199'
title: C3100 ile C3199 arasındaki derleyici hataları
ms.date: 04/21/2019
f1_keywords:
- C3102
- C3105
- C3107
- C3108
- C3109
- C3111
- C3112
- C3119
- C3122
- C3123
- C3124
- C3125
- C3127
- C3128
- C3129
- C3143
- C3144
- C3146
- C3147
- C3148
- C3151
- C3158
- C3164
- C3165
- C3169
- C3177
- C3178
- C3184
- C3188
- C3191
- C3193
helpviewer_keywords:
- C3102
- C3105
- C3107
- C3108
- C3109
- C3111
- C3112
- C3119
- C3122
- C3123
- C3124
- C3125
- C3127
- C3128
- C3129
- C3143
- C3144
- C3146
- C3147
- C3148
- C3151
- C3158
- C3164
- C3165
- C3169
- C3177
- C3178
- C3184
- C3188
- C3191
- C3193
ms.assetid: 7bc40c2f-6a8d-488a-b665-f39375afee77
ms.openlocfilehash: d2398fa8ae783a34662efc361730a5054a982458
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238719"
---
# <a name="compiler-errors-c3100-through-c3199"></a>C3100 ile C3199 arasındaki derleyici hataları

Belgenin bu bölümündeki makaleler, derleyici tarafından oluşturulan hata iletilerinin bir alt kümesini açıklar.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Hata iletileri

|Hata|İleti|
|-----------|-------------|
|[Derleyici hatası C3100](compiler-error-c3100.md)|'*tanımlayıcı*': bilinmeyen öznitelik niteleyicisi|
|[Derleyici hatası C3101](compiler-error-c3101.md)|'*tanımlayıcı*' adlandırılmış öznitelik bağımsız değişkeni için geçersiz ifade|
|Derleyici hatası C3102|Kullanımdan kalktı.|
|[Derleyici hatası C3103](compiler-error-c3103.md)|'*tanımlayıcı*': Yinelenen adlandırılmış bağımsız değişken|
|[Derleyici hatası C3104](compiler-error-c3104.md)|geçersiz öznitelik bağımsız değişkeni|
|Derleyici hatası C3105|'*symbol*': öznitelik olarak kullanılamaz|
|[Derleyici hatası C3106](compiler-error-c3106.md)|'*Attribute*': adlandırılmamış bağımsız değişkenler adlandırılmış bağımsız değişkenlerden önce gelmelidir|
|Derleyici hatası C3107|'*Attribute*': yerel özniteliklerin üye işlevleri tanımlanamıyor|
|Derleyici hatası C3108|Başlatıcı listesi bir ifade olmadığından tür çıkarılamıyor|
|Derleyici hatası C3109|'*tanımlayıcı*': Arabirim yöntemlerinin ' __stdcall ' veya ' __cdecl ' çağırma kuralını kullanması gerekir|
|[Derleyici hatası C3110](compiler-error-c3110.md)|'*Function*': bir com arabirimi yöntemini aşırı yükleyemezsiniz|
|Derleyici hatası C3111|Başlatıcı listesi, bir şablon parametresi için varsayılan bağımsız değişken olarak kullanılamaz|
|Derleyici hatası C3112|'*interface*': bir arabirim yalnızca genel veya ad alanı kapsamında bildirilemez|
|[Derleyici hatası C3113](compiler-error-c3113.md)|' interface/enum ' bir şablon/genel olamaz|
|[Derleyici hatası C3114](compiler-error-c3114.md)|'*Identifier*': geçerli bir adlandırılmış öznitelik bağımsız değişkeni değil|
|[Derleyici hatası C3115](compiler-error-c3115.md)|'*Attribute*': Bu özniteliğe '*Yapı*' üzerinde izin verilmiyor|
|[Derleyici hatası C3116](compiler-error-c3116.md)|'*belirtici*': arabirim yöntemi için geçersiz depolama sınıfı|
|[Derleyici hatası C3117](compiler-error-c3117.md)|'*interface*': bir arabirimin yalnızca bir taban sınıfı olabilir|
|[Derleyici hatası C3118](compiler-error-c3118.md)|'*interface*': arabirimler sanal devralmayı desteklemez|
|Derleyici hatası C3119|alignas (void) öğesine izin verilmiyor|
|[Derleyici hatası C3120](compiler-error-c3120.md)|'*tanımlayıcı*': arabirim yöntemleri değişken bağımsız değişken listesi alamaz|
|[Derleyici hatası C3121](compiler-error-c3121.md)|'*Class*' sınıfının GUID 'si değiştirilemiyor|
|Derleyici hatası C3122|'*interface*': bir WinRT genel arabiriminin GUID 'si olamaz|
|Derleyici hatası C3123|WinRT genel arabiriminde kısıtlamalar olamaz|
|Derleyici hatası C3124|' signed Char ' geçerli bir WinRT veri türü değil. Bunun yerine ' işaretsiz Char ', ' wchar_t ' veya ' signed Short ' kullanın.|
|Derleyici hatası C3125|'*Type*': tür doğrudan veya dolaylı olarak ' Platform:: Exception ' öğesinden türetilemez|
|[Derleyici hatası C3126](compiler-error-c3126.md)|yönetilen/WinRT türü '*Type*' içinde bir '*Union*' birleşimi tanımlanamaz|
|Derleyici hatası C3127|'*Type*': '*nitelik*' nitelik yalnızca bir WinRT başvuru sınıfında kullanılabilir|
|Derleyici hatası C3128|'*Type*', '*Type*' ile tanıtılan bir vtable içermiyor|
|Derleyici hatası C3129|'*Type*': __default_vptr_for_base yalnızca yerel olarak tanımlanmış polimorfik türlerde ve tabanlarında kullanılabilir|
|[Derleyici hatası C3130](compiler-error-c3130.md)|İç derleyici hatası: eklenen kod bloğu PDB 'ye yazılamadı|
|[Derleyici hatası C3131](compiler-error-c3131.md)|Projenin ' name ' özelliği olan bir ' Module ' özniteliği olmalıdır|
|[Derleyici hatası C3132](compiler-error-c3132.md)|'*Parameter*': parametre dizileri yalnızca ' Single-boyutlu Managed/wınrt Array ' türünde bir biçimsel bağımsız değişkene uygulanabilir|
|[Derleyici hatası C3133](compiler-error-c3133.md)|Öznitelikler C++ vararg 'larına uygulanamaz|
|[Derleyici hatası C3134](compiler-error-c3134.md)|'*Value*': '*Argument*' öznitelik bağımsız değişkeninin değeri geçerli '*Type*' türünde değil|
|[Derleyici hatası C3135](compiler-error-c3135.md)|'*tanımlayıcı*': bir özellik ' const ' veya ' volatile ' türüne sahip olamaz|
|[Derleyici hatası C3136](compiler-error-c3136.md)|'*interface*': com arabirimi yalnızca başka bir com arabiriminden devralınabilir, '*ıNTERFACE*' bir com arabirimi değil|
|[Derleyici hatası C3137](compiler-error-c3137.md)|'*tanımlayıcı*': bir özellik başlatılamıyor|
|[Derleyici hatası C3138](compiler-error-c3138.md)|'*tanımlayıcı*': '*Attribute*' arabirimi IDispatch 'ten veya IDispatch 'ten devralan bir arabirimden devralmalıdır|
|[Derleyici hatası C3139](compiler-error-c3139.md)|'*Type*': üye olmadan bir udt dışarı aktarılamıyor|
|[Derleyici hatası C3140](compiler-error-c3140.md)|aynı derleme biriminde birden fazla ' Module ' özniteliği olamaz|
|[Derleyici hatası C3141](compiler-error-c3141.md)|'*interface*': arabirimler yalnızca genel devralmayı destekler|
|[Derleyici hatası C3142](compiler-error-c3142.md)|'*Property*': bir özelliğin adresini alamaz|
|Derleyici hatası C3143|'*Argument*': öznitelik bağımsız değişkeni birden fazla değere sahip olamaz|
|Derleyici hatası C3144|'*Attribute*': öznitelik açık bağımsız değişkenler gerektiriyor, '*Argument*' adlandırılmamış|
|[Derleyici hatası C3145](compiler-error-c3145.md)|'*tanımlayıcı*': genel veya statik değişken '*Type*' yönetilen/WinRT türüne sahip olamaz|
|Derleyici hatası C3146|Kullanımdan kalktı.|
|Derleyici hatası C3147|Kullanımdan kalktı.|
|Derleyici hatası C3148|Kullanımdan kalktı.|
|[Derleyici hatası C3149](compiler-error-c3149.md)|'*Type*': Bu tür, üst düzey '*token*' olmadan burada kullanılamaz|
|[Derleyici hatası C3150](compiler-error-c3150.md)|'*Yapı*': '*Attribute*' yalnızca bir sınıfa, yapıya, arabirime, diziye veya işaretçiye uygulanabilir|
|Derleyici hatası C3151|Kullanımdan kalktı.|
|[Derleyici hatası C3152](compiler-error-c3152.md)|'*Function*': '*anahtar sözcüğü*' yalnızca bir sınıfa, yapıya veya sanal üye işleve uygulanabilir|
|[Derleyici hatası C3153](compiler-error-c3153.md)|'*interface*': bir arabirimin örneğini oluşturamazsınız|
|[Derleyici hatası C3154](compiler-error-c3154.md)|Üç nokta önüne ', ' bekleniyor. Virgülle ayrılmış olmayan üç nokta, parametre dizisi işlevlerinde desteklenmez.|
|[Derleyici hatası C3155](compiler-error-c3155.md)|özellik dizin oluşturucuda özniteliklere izin verilmez|
|[Derleyici hatası C3156](compiler-error-c3156.md)|'*Class*': yönetilen/WinRT türünde yerel bir tanımınız olamaz|
|[Derleyici hatası C3157](compiler-error-c3157.md)|ParamArray özniteliği yalnızca son parametreye uygulanabilir|
|Derleyici hatası C3158|'*Function*': '*anahtar sözcüğü*' yalnızca bir sanal üye işleve uygulanabilir|
|[Derleyici hatası C3159](compiler-error-c3159.md)|'*tanımlayıcı*': değer türüne işaretçiler dizisi bildirilemez|
|[Derleyici hatası C3160](compiler-error-c3160.md)|'*Type*': yönetilen/WinRT sınıfının veri üyesi bu türe sahip olamaz|
|[Derleyici hatası C3161](compiler-error-c3161.md)|'*interface*': arabirim içinde sınıf, yapı veya arabirim iç içe geçirme geçersizdir; bir sınıf veya yapıda iç içe geçme arabirimi geçersizdir|
|[Derleyici hatası C3162](compiler-error-c3162.md)|'*Type*': yok edicisi olan bir başvuru türü statik veri üyesi '*member*' türü olarak kullanılamaz|
|[Derleyici hatası C3163](compiler-error-c3163.md)|'*Class*': öznitelikler önceki bildirimle tutarsız|
|Derleyici hatası C3164|Kullanımdan kalktı.|
|Derleyici hatası C3165|'*Value*': bir integral veya kayan nokta değerine dönüştürülemez|
|[Derleyici hatası C3166](compiler-error-c3166.md)|Kullanımdan kalktı. '*Type*': yönetilen/WinRT sınıfının veri üyesi '*pointer_type* iç *managed_pointer_type*' türüne sahip olamaz|
|[Derleyici hatası C3167](compiler-error-c3167.md)|.NET Framework başlatılamıyor: yüklü olduğundan emin olun|
|[Derleyici hatası C3168](compiler-error-c3168.md)|'*Type*': sabit listesi için temeldeki tür geçersiz|
|Derleyici hatası C3169|'*Type*': ' Auto ' türü '*Type*' öğesinden çıkarılamıyor|
|[Derleyici hatası C3170](compiler-error-c3170.md)|bir projede farklı modül tanımlayıcıları olamaz|
|[Derleyici hatası C3171](compiler-error-c3171.md)|'*module*': bir projede farklı modül öznitelikleri belirtilemez|
|[Derleyici hatası C3172](compiler-error-c3172.md)|'*tanımlayıcı*': bir projede farklı idl_module öznitelikleri belirtilemez|
|[Derleyici hatası C3173](compiler-error-c3173.md)|IDL birleştirmede sürüm uyumsuzluğu|
|[Derleyici hatası C3174](compiler-error-c3174.md)|Modül özniteliği belirtilmedi|
|[Derleyici hatası C3175](compiler-error-c3175.md)|'*Function*': yönetilmeyen '*Function*' işlevinden yönetilen türün bir yöntemi çağrılamaz|
|[Derleyici hatası C3176](compiler-error-c3176.md)|'*Type*': yerel değer türü bildirilemez|
|Derleyici hatası C3177|'*Type*' içeren bir türe dönüştürme işleviniz olamaz|
|Derleyici hatası C3178|'*Type*': varsayılan bağımsız değişkenlerle bir işlevde ParamArray kullanılamaz|
|[Derleyici hatası C3179](compiler-error-c3179.md)|adlandırılmamış bir yönetilen/WinRT türüne izin verilmiyor|
|[Derleyici hatası C3180](compiler-error-c3180.md)|'*Type*': ad, '*sayı*' karakter olan meta veri sınırını aşıyor|
|[Derleyici hatası C3181](compiler-error-c3181.md)|'*Type*': *işleç* için geçersiz işlenen|
|[Derleyici hatası C3182](compiler-error-c3182.md)|'*Type*': bir üye using bildirimi veya erişim bildirimi yönetilen/WinRT türü içinde geçersizdir|
|[Derleyici hatası C3183](compiler-error-c3183.md)|yönetilen/WinRT türü '*Class*' içinde adlandırılmamış sınıf, yapı veya birleşim tanımlanamıyor|
|Derleyici hatası C3184|Kullanımdan kalktı.|
|[Derleyici hatası C3185](compiler-error-c3185.md)|' TypeId ': yönetilen/WinRT türü '*tür*' üzerinde kullanılır, bunun yerine '*operator*' kullanın|
|Derleyici hatası C3186|Kullanımdan kalktı.|
|[Derleyici hatası C3187](compiler-error-c3187.md)|'*Identifier*': yalnızca bir işlevin gövdesinde kullanılabilir|
|Derleyici hatası C3188|Kullanımdan kalktı.|
|[Derleyici hatası C3189](compiler-error-c3189.md)|' TypeId<*bildirimci*> ': Bu sözdizimi artık desteklenmiyor; bunun yerine:: typeid kullanın|
|[Derleyici hatası C3190](compiler-error-c3190.md)|Belirtilen şablon bağımsız değişkenleriyle '*bildirimci*', '*Type*' öğesinin herhangi bir üye işlevinin açık örneklemesi değil|
|Derleyici hatası C3191|Kullanımdan kalktı.|
|[Derleyici hatası C3192](compiler-error-c3192.md)|sözdizimi hatası: ' ^ ' bir önek işleci değil (' * ' mi demek istediniz?)|
|Derleyici hatası C3193|'*Yapı*': '/CLR ' veya '/ZW ' komut satırı seçeneğini gerektirir|
|[Derleyici hatası C3194](compiler-error-c3194.md)|'*Type*': bir değer türünün atama işleci olamaz|
|[Derleyici hatası C3195](compiler-error-c3195.md)|'*anahtar sözcüğü*': ayrılmıştır ve bir başvuru sınıfının veya değer türünün üyesi olarak kullanılamaz. CLR/WinRT işleçleri ' operator ' anahtar sözcüğü kullanılarak tanımlanmalıdır|
|[Derleyici hatası C3196](compiler-error-c3196.md)|'*tanımlayıcı*': birden fazla kez kullanıldı|
|[Derleyici hatası C3197](compiler-error-c3197.md)|'*anahtar sözcüğü*': yalnızca tanımlarda kullanılabilir|
|[Derleyici hatası C3198](compiler-error-c3198.md)|kayan noktalı pragmaların geçersiz kullanımı: fenv_access pragma yalnızca hassas modda çalışır|
|[Derleyici hatası C3199](compiler-error-c3199.md)|kayan noktalı pragmaların geçersiz kullanımı: özel durumlar, kesin olmayan modda desteklenmez|

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ derleyicisi ve derleme araçları hataları ve uyarıları](../compiler-errors-1/c-cpp-build-errors.md) \
[C2000 ile C3999 arasındaki derleyici hataları](../compiler-errors-1/compiler-errors-c2000-c3999.md)
