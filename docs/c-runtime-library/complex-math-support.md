---
title: C karmaşık matematik destek | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.complex
dev_langs:
- C++
helpviewer_keywords:
- complex numbers, math routines
- math routines
- complex numbers
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 661e1367ea64713cf7a143f276cd195d54fecf85
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="c-complex-math-support"></a>C karmaşık matematik desteği

Microsoft C çalışma zamanı kitaplığı (CRT) tüm ISO C99 tarafından gerekli olanlar da dahil olmak üzere karmaşık matematik kitaplık işlevleri sağlar. Derleyici tarafından doğrudan desteklenmeyen bir **karmaşık** veya **_Complex** anahtar sözcüğü, bu nedenle Microsoft uygulaması yapı türleri karmaşık numaralar temsil için kullanır.

Bu işlevler, performans doğruluk ile dengelemek için uygulanır. Doğru yuvarlatılmış sonuç üretme şekilde basımı karşılamayacak kadar pahalı olabilir çünkü bu işlevler verimli bir şekilde doğru yuvarlatılmış sonucu yaklaşık üretmek için tasarlanmıştır. Olabilir ancak durumlarda çoğu durumda, üretilen içinde doğru yuvarlatılmış sonuç 1 ulp +/-sonucudur büyük yanlış bilgi olduğu.

Kayan karmaşık matematik yordamları kullanan noktası uygulamalarının için matematik kitaplık işlevleri. Bu işlevler farklı uygulamalar farklı CPU mimari için vardır. Örneğin, 32-bit x86 CRT 64-bit x64 daha farklı bir uygulama olabilir CRT. Ayrıca, bazı işlevler belirli bir CPU mimarisi için birden çok uygulamaları olabilir. En verimli uygulama CPU tarafından desteklenen yönerge kümeleri bağlı olarak çalışma zamanında dinamik olarak seçilir. Örneğin, 32-bit x86 içinde CRT, bazı işlevler sahip hem bir x87 uygulama ve SSE2 uygulaması. SSE2 destekleyen bir CPU üzerinde çalışırken, daha hızlı SSE2 uygulama kullanılır. SSE2, uygulama kullanılan yavaş x87 desteklemeyen bir CPU üzerinde çalışırken. Matematik kitaplığı işlevlerin farklı uygulamalar farklı CPU yönergeleri ve farklı algoritmalar sonuçları üretmek için kullanılıyor olabileceğinden, işlevleri CPU'lar arasında farklı sonuçlar doğurabilir. Çoğu durumda, doğru yuvarlatılmış sonuç 1 ulp +/-içinde sonucu olan, ancak gerçek sonuçları CPU'lar arasında değişebilir.

## <a name="types-used-in-complex-math"></a>Karmaşık matematik içinde kullanılan türleri

Complex.h üstbilgi Microsoft uyarlamasını bu tür olarak eşdeğerleri C99 standart yerel karmaşık türleri için tanımlar:

|Standart türü|Microsoft türü|
|-|-|
|**float karmaşık** veya **_Complex float**|**_FComplex**|
|**çift karmaşık** veya **çift _Complex**|**_DComplex**|
|**uzun çift karmaşık** veya **uzun çift _Complex**|**_LComplex**|

Ayrı bir türü math.h üstbilgi tanımlayan **yapısı _complex**için kullanılan [_cabs](../c-runtime-library/reference/cabs.md) işlevi. **Yapısı _complex** türü eşdeğer karmaşık matematik işlevleri tarafından kullanılmaz [cab dosyaları, cabsf, cabsl](../c-runtime-library/reference/cabs-cabsf-cabsl.md).

## <a name="complex-constants-and-macros"></a>Karmaşık sabitleri ve makrolar

**I** olarak tanımlanan **float** karmaşık tür **_FComplex** tarafından başlatılan `{ 0.0f, 1.0f }`.

## <a name="trigonometric-functions"></a>Trigonometrik İşlevler

|İşlev|Açıklama|
|-|-|
|[cacos, cacosf, cacosl](../c-runtime-library/reference/cacos-cacosf-cacosl.md)|Karmaşık bir sayının karmaşık ark kosinüsünü işlem|
|[casin, casinf, casinl](../c-runtime-library/reference/casin-casinf-casinl.md)|Karmaşık sayıyı karmaşık ark sinüsünü işlem|
|[catan, catanf, catanl](../c-runtime-library/reference/catan-catanf-catanl.md)|Karmaşık sayıyı karmaşık ark tanjantını işlem|
|[ccos, ccosf, ccosl](../c-runtime-library/reference/ccos-ccosf-ccosl.md)|Karmaşık bir sayının karmaşık kosinüsünü işlem|
|[csin, csinf, csinl](../c-runtime-library/reference/csin-csinf-csinl.md)|Karmaşık bir karmaşık sayının sinüsünü işlem|
|[ctan, ctanf, ctanl](../c-runtime-library/reference/ctan-ctanf-ctanl.md)|Karmaşık bir karmaşık sayının tanjantını işlem|

## <a name="hyperbolic-functions"></a>Hiperbolik İşlevler

|İşlev|Açıklama|
|-|-|
|[cacosh, cacoshf, cacoshl](../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)|Karmaşık yay karmaşık bir sayının hiperbolik kosinüsünü işlem|
|[casinh, casinhf, casinhl](../c-runtime-library/reference/casinh-casinhf-casinhl.md)|Karmaşık bir sayının karmaşık Ark hiperbolik sinüsü işlem|
|[catanh, catanhf, catanhl](../c-runtime-library/reference/catanh-catanhf-catanhl.md)|Karmaşık bir sayının karmaşık Ark hiperbolik tanjantı işlem|
|[ccosh, ccoshf, ccoshl](../c-runtime-library/reference/ccosh-ccoshf-ccoshl.md)|Karmaşık bir sayının hiperbolik kosinüsünü karmaşık işlem|
|[csinh, csinhf, csinhl](../c-runtime-library/reference/csinh-csinhf-csinhl.md)|Karmaşık bir sayının hiperbolik sinüsünü karmaşık işlem|
|[ctanh, ctanhf, ctanhl](../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)|Karmaşık bir sayının hiperbolik tanjantını karmaşık işlem|

## <a name="exponential-and-logarithmic-functions"></a>Üstel ve Logaritmik işlevleri

|İşlev|Açıklama|
|-|-|
|[cexp, cexpf, cexpl](../c-runtime-library/reference/cexp-cexpf-cexpl.md)|Temel - karmaşık işlem*e* karmaşık bir sayının üstel|
|[clog, clogf, clogl](../c-runtime-library/reference/clog-clogf-clogl.md)|Karmaşık doğal işlem (temel -*e*) logaritmasını karmaşık bir sayının|
|[clog10, clog10f, clog10l](../c-runtime-library/reference/clog10-clog10f-clog10l.md)|Karmaşık karmaşık sayının 10 tabanında logaritmasını işlem|

## <a name="power-and-absolute-value-functions"></a>Güç ve mutlak değer işlevleri

|İşlev|Açıklama|
|-|-|
|[cabs, cabsf, cabsl](../c-runtime-library/reference/cabs-cabsf-cabsl.md)|Karmaşık bir sayının mutlak (norm, modül veya büyüklük olarak da adlandırılır) karmaşık değer işlem|
|[cpow, cpowf, cpowl](../c-runtime-library/reference/cpow-cpowf-cpowl.md)|Karmaşık güç işlevi x işlem<sup>y</sup>|
|[csqrt, csqrtf, csqrtl](../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)|Karmaşık karmaşık bir sayının kare kökünü işlem|

## <a name="manipulation-functions"></a>İşleme işlevleri

|İşlev|Açıklama|
|-|-|
|[_Cbuild, _FCbuild, _LCbuild](../c-runtime-library/reference/cbuild-fcbuild-lcbuild.md)|Karmaşık sayıyı gerçek ve sanal bölümlerinden oluşturun|
|[carg, cargf, cargl](../c-runtime-library/reference/carg-cargf-cargl.md)|(Aşaması açı olarak da bilinir) bağımsız değişkeni karmaşık bir sayının işlem|
|[cimag, cimagf, cimagl](../c-runtime-library/reference/cimag-cimagf-cimagl.md)|Karmaşık sayıyı sanal parçası işlem|
|[conj, conjf, conjl](../c-runtime-library/reference/conj-conjf-conjl.md)|Karmaşık bir sayının karmaşık çiftini işlem|
|[cproj, cprojf, cprojl](../c-runtime-library/reference/cproj-cprojf-cprojl.md)|Bir yansıtma Riemann küre üzerine karmaşık bir sayının işlem|
|[creal, crealf, creall](../c-runtime-library/reference/creal-crealf-creall.md)|Karmaşık bir sayının gerçek bölüm işlem|
|[Norm, normf, norml](../c-runtime-library/reference/norm-normf-norml1.md)|Karmaşık bir sayının kare büyüklük işlem|

## <a name="operation-functions"></a>İşlem işlevleri

Karmaşık numaralar Microsoft derleyici yerel tür olmadığı için standart aritmetik işleçler karmaşık türler üzerinde tanımlı değil. Kolaylık olması için kullanıcı kodundaki karmaşık numaralar sınırlı işlenmesini etkinleştirmek için bu karmaşık matematik kitaplık işlevleri sağlanır:

|İşlev|Açıklama|
|-|-|
|[_Cmulcc, _FCmulcc, _LCmulcc](../c-runtime-library/reference/cmulcc-fcmulcc-lcmulcc.md)|Çarp iki karmaşık numaralar|
|[_Cmulcr, _FCmulcr, _LCmulcr](../c-runtime-library/reference/cmulcr-fcmulcr-lcmulcr.md)|Karmaşık ve kayan noktalı sayı çarpın|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
