---
title: C karmaşık matematik desteği
ms.date: 03/30/2018
f1_keywords:
- c.complex
helpviewer_keywords:
- complex numbers, math routines
- math routines
- complex numbers
ms.openlocfilehash: 12ba858993d3712cbf390288df60faedc602c90a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452617"
---
# <a name="c-complex-math-support"></a>C karmaşık matematik desteği

Microsoft C çalışma zamanı kitaplığı (CRT), tüm ISO C99 tarafından gerekli olanlar da dahil olmak üzere, karmaşık matematik kitaplığı işlevleri sağlar. Derleyici tarafından doğrudan desteklenmeyen bir **karmaşık** veya **_Complex** anahtar sözcüğü, bu nedenle Microsoft uygulaması yapı türleri karmaşık sayılar temsil için kullanır.

Bu işlevler, doğruluk açısından performans dengelemek için uygulanır. Doğru yuvarlatılmış sonuç oluşturmayı fazla vakit pahalı olabileceği için bu işlevleri verimli bir şekilde doğru yuvarlatılmış sonuca Kapat bir yaklaştırma üretmek için tasarlanmıştır. Olabilir durumlarda çoğu durumda, sonucu içinde +/-1 ulp doğru yuvarlatılmış sonucun, ancak daha büyük bir yanlışlığı olduğu.

Karmaşık matematik yordamlarını kayan kullanan noktası matematik kitaplığı işlevi uygulamaları için. Bu işlevler, farklı CPU mimarileri için farklı uygulamaları vardır. Örneğin, 32-bit x86 CRT 64-bit x64 değerinden farklı bir uygulama olabilir CRT. Ayrıca, bazı işlevler belirli bir CPU mimarisi için birden çok uygulamaları olabilir. En verimli uygulama CPU tarafından desteklenen komut kümelerini bağlı olarak çalışma zamanında dinamik olarak seçilir. Örneğin, 32-bit x86, CRT, bazı işlevler, hem x x87 sahip uygulama ve SSE2 uygulaması. SSE2 destekleyen bir CPU üzerinde çalışırken, daha hızlı SSE2 uygulaması kullanılır. SSE2, uygulama kullanılan daha yavaş x87 desteklemeyen bir CPU üzerinde çalışırken. Matematik kitaplığı işlevi, farklı uygulamalar farklı CPU yönergeleri ve farklı algoritmalar sonuçları üretmek için kullanılıyor olabileceğinden, İşlevler, CPU'lar arasında farklı sonuçlar üretebilir. Çoğu durumda, sonuçlar içinde +/-1 ulp yuvarlatılmış doğru sonucu olan, ancak gerçek sonuçların CPU'lar arasında değişebilir.

## <a name="types-used-in-complex-math"></a>Karmaşık matematik kullanılan türler

Microsoft uygulaması complex.h üstbilgisinin eşdeğerleri C99 standart yerel karmaşık türleri olarak bu tür tanımlar:

|Standart türü|Microsoft türü|
|-|-|
|**float karmaşık** veya **_Complex Kaydır**|**_FComplex**|
|**çift karmaşık** veya **çift _Complex**|**_DComplex**|
|**uzun çift karmaşık** veya **_Complex uzun çift**|**_LComplex**|

Ayrı bir tür math.h üstbilgi tanımlar **yapı _complex**için kullanılan [_cabs](../c-runtime-library/reference/cabs.md) işlevi. **Yapı _complex** türü eşdeğer karmaşık matematik işlevleri tarafından kullanılmaz [cab dosyaları, cabsf cabsl](../c-runtime-library/reference/cabs-cabsf-cabsl.md).

## <a name="complex-constants-and-macros"></a>Karmaşık sabitleri ve makroları

**Ben** olarak tanımlanan **float** karmaşık tür **_FComplex** başlatan `{ 0.0f, 1.0f }`.

## <a name="trigonometric-functions"></a>Trigonometrik İşlevler

|İşlev|Açıklama|
|-|-|
|[cacos, cacosf, cacosl](../c-runtime-library/reference/cacos-cacosf-cacosl.md)|Karmaşık bir sayıyı karmaşık ark kosinüsünü hesaplar|
|[casin, casinf, casinl](../c-runtime-library/reference/casin-casinf-casinl.md)|Karmaşık bir sayıyı karmaşık ark sinüsünü hesaplar|
|[catan, catanf, catanl](../c-runtime-library/reference/catan-catanf-catanl.md)|Karmaşık bir sayıyı karmaşık ark tanjantını hesaplar|
|[ccos, ccosf, ccosl](../c-runtime-library/reference/ccos-ccosf-ccosl.md)|Karmaşık bir sayıyı karmaşık kosinüsünü hesaplar|
|[csin, csinf, csinl](../c-runtime-library/reference/csin-csinf-csinl.md)|Karmaşık bir sayıyı karmaşık sinüsünü hesaplar|
|[ctan, ctanf, ctanl](../c-runtime-library/reference/ctan-ctanf-ctanl.md)|Karmaşık bir sayıyı karmaşık tanjantını hesaplar|

## <a name="hyperbolic-functions"></a>Hiperbolik İşlevler

|İşlev|Açıklama|
|-|-|
|[cacosh, cacoshf, cacoshl](../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)|Karmaşık bir sayıyı karmaşık yay hiperbolik kosinüsünü hesaplar|
|[casinh, casinhf, casinhl](../c-runtime-library/reference/casinh-casinhf-casinhl.md)|Karmaşık bir sayıyı karmaşık yay hiperbolik sinüsünü hesaplar|
|[catanh, catanhf, catanhl](../c-runtime-library/reference/catanh-catanhf-catanhl.md)|Karmaşık bir sayıyı karmaşık yay hiperbolik tanjantını hesaplar|
|[ccosh, ccoshf, ccoshl](../c-runtime-library/reference/ccosh-ccoshf-ccoshl.md)|Karmaşık bir sayıyı karmaşık hiperbolik kosinüsünü hesaplar|
|[csinh, csinhf, csinhl](../c-runtime-library/reference/csinh-csinhf-csinhl.md)|Karmaşık bir sayıyı karmaşık hiperbolik sinüsünü hesaplar|
|[ctanh, ctanhf, ctanhl](../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)|Karmaşık bir sayıyı karmaşık hiperbolik tanjantını hesaplar|

## <a name="exponential-and-logarithmic-functions"></a>Üstel ve Logaritmik işlevleri

|İşlev|Açıklama|
|-|-|
|[cexp, cexpf, cexpl](../c-runtime-library/reference/cexp-cexpf-cexpl.md)|Temel - karmaşık işlem*e* , karmaşık bir sayıyı üstel|
|[clog, clogf, clogl](../c-runtime-library/reference/clog-clogf-clogl.md)|Karmaşık doğal işlem (temel -*e*) karmaşık bir sayıyı logaritması|
|[clog10, clog10f, clog10l](../c-runtime-library/reference/clog10-clog10f-clog10l.md)|Karmaşık bir sayıyı karmaşık 10 tabanında logaritmasını hesaplar|

## <a name="power-and-absolute-value-functions"></a>Güç ve mutlak değer işlevleri

|İşlev|Açıklama|
|-|-|
|[cabs, cabsf, cabsl](../c-runtime-library/reference/cabs-cabsf-cabsl.md)|Karmaşık bir sayının mutlak (norm, modül ya da büyüklük olarak da bilinir) karmaşık değer işlem|
|[cpow, cpowf, cpowl](../c-runtime-library/reference/cpow-cpowf-cpowl.md)|Güç karmaşık işlevi x işlem<sup>y</sup>|
|[csqrt, csqrtf, csqrtl](../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)|Karmaşık bir sayıyı karmaşık kare kökünü hesaplar|

## <a name="manipulation-functions"></a>İşleme işlevleri

|İşlev|Açıklama|
|-|-|
|[_Cbuild, _FCbuild, _LCbuild](../c-runtime-library/reference/cbuild-fcbuild-lcbuild.md)|Karmaşık bir sayıyı reel ve sanal parçalarından oluşturun|
|[carg, cargf, cargl](../c-runtime-library/reference/carg-cargf-cargl.md)|Karmaşık bir sayıyı (aşama açı olarak da bilinir) bağımsız işlem|
|[cimag, cimagf, cimagl](../c-runtime-library/reference/cimag-cimagf-cimagl.md)|Karmaşık bir sayıyı sanal parçası işlem|
|[conj, conjf, conjl](../c-runtime-library/reference/conj-conjf-conjl.md)|Karmaşık bir sayının karmaşık çiftini işlem|
|[cproj, cprojf, cprojl](../c-runtime-library/reference/cproj-cprojf-cprojl.md)|Bir projeksiyon Riemann küre üzerine karmaşık bir sayının işlem|
|[creal, crealf, creall](../c-runtime-library/reference/creal-crealf-creall.md)|Karmaşık bir sayıyı gerçek parçası işlem|
|[Norm, normf, norml](../c-runtime-library/reference/norm-normf-norml1.md)|Karmaşık bir sayının karesini büyüklük işlem|

## <a name="operation-functions"></a>İşlem işlevleri

Karmaşık sayılar Microsoft derleyici yerel bir tür olmadığından, standart aritmetik işleçler karmaşık türler üzerinde tanımlı değil. Kolaylık olması için bu karmaşık matematik kitaplığı işlevi, kullanıcı kodundaki karmaşık sayıların sınırlı düzenlemeyi etkinleştirmek için sağlanır:

|İşlev|Açıklama|
|-|-|
|[_Cmulcc, _FCmulcc, _LCmulcc](../c-runtime-library/reference/cmulcc-fcmulcc-lcmulcc.md)|İki karmaşık sayılar Çarp|
|[_Cmulcr, _FCmulcr, _LCmulcr](../c-runtime-library/reference/cmulcr-fcmulcr-lcmulcr.md)|Karmaşık ve bir kayan noktalı sayı çarpın|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
