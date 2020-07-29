---
title: C karmaşık matematik desteği
ms.date: 05/14/2019
f1_keywords:
- c.complex
helpviewer_keywords:
- complex numbers, math routines
- math routines
- complex numbers
ms.openlocfilehash: dac032940ed9d96764b64809c5f8901ac273898b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215185"
---
# <a name="c-complex-math-support"></a>C karmaşık matematik desteği

Microsoft C çalışma zamanı kitaplığı (CRT), ISO C99 tarafından gerekenlerden bazıları dahil olmak üzere karmaşık matematik kitaplığı işlevleri sağlar. Derleyici bir **`complex`** veya **`_Complex`** anahtar sözcüğünü doğrudan desteklemez, bu nedenle Microsoft uygulama karmaşık sayıları temsil etmek için yapı türlerini kullanır.

Bu işlevler, performansı doğruluk altına alacak şekilde uygulanır. Doğru şekilde yuvarlanmış sonucun üretilmesi, canlı olarak elde edilebilir hale gelebilir, ancak bu işlevler doğru bir şekilde yuvarlanmış sonuca yakın bir şekilde bir kapatma sağlamak üzere tasarlanmıştır. Çoğu durumda, üretilen sonuç doğru bir şekilde yuvarlanmış sonucu +/-1 ULP içinde, ancak daha fazla doğruluk olduğu durumlar olabilir.

Karmaşık matematik yordamları, uygulamaları için kayan nokta matematik kitaplığı işlevlerine dayanır. Bu işlevlerin farklı CPU mimarileri için farklı uygulamaları vardır. Örneğin, 32 bit x86 CRT, 64 bit x64 CRT 'den farklı bir uygulamaya sahip olabilir. Ayrıca, bazı işlevlerden belirli bir CPU mimarisi için birden çok uygulama olabilir. En verimli uygulama, CPU tarafından desteklenen yönerge kümelerine bağlı olarak çalışma zamanında dinamik olarak seçilir. Örneğin, 32 bit x86 CRT 'de, bazı işlevlerde hem x87 uygulama hem de bir SSE2 uygulama vardır. SSE2 destekleyen bir CPU üzerinde çalışırken, daha hızlı SSE2 uygulama kullanılır. SSE2 desteklemeyen bir CPU üzerinde çalışırken, daha yavaş x87 uygulama kullanılır. Matematik kitaplığı işlevlerinin farklı uygulamaları, sonuçlarını oluşturmak için farklı CPU yönergeleri ve farklı algoritmalar kullanabileceğinden, işlevler CPU 'larda farklı sonuçlar üretebilir. Çoğu durumda, sonuçlar doğru bir şekilde yuvarlanmış sonucu +/-1 ULP içinde, ancak gerçek sonuçlar CPU 'larda farklılık gösterebilir.

## <a name="types-used-in-complex-math"></a>Karmaşık matematik için kullanılan türler

Complex. h üstbilgisinin Microsoft uygulamasında, bu türler C99 standart yerel karmaşık türler için eşdeğer olarak tanımlanmaktadır:

|Standart tür|Microsoft türü|
|-|-|
|**`float complex`** veya**`float _Complex`**|**_Fcomplex**|
|**`double complex`** veya**`double _Complex`**|**_Dcomplex**|
|**`long double complex`** veya**`long double _Complex`**|**_Lcomplex**|

Math. h üst bilgisi, [_cabs](../c-runtime-library/reference/cabs.md) işlevi için kullanılan ayrı bir tür, **struct _complex**tanımlar. **Struct _complex** türü, benzer karmaşık matematik işlevleri [CAB, cabsf, cabsl](../c-runtime-library/reference/cabs-cabsf-cabsl.md)tarafından kullanılmaz.

## <a name="complex-constants-and-macros"></a>Karmaşık sabitler ve makrolar

**_Fcomplex** **, tarafından** başlatılan karmaşık tür olarak tanımlanır `{ 0.0f, 1.0f }` .

## <a name="trigonometric-functions"></a>Trigonometrik işlevleri

|İşlev|Açıklama|
|-|-|
|[cacos, cacosf, cacosl](../c-runtime-library/reference/cacos-cacosf-cacosl.md)|Karmaşık bir sayının karmaşık yay kosinüsünü hesaplama|
|[casin, casinf, casinl](../c-runtime-library/reference/casin-casinf-casinl.md)|Karmaşık bir sayının karmaşık yay sinüsünü hesaplama|
|[catan, catanf, catanl](../c-runtime-library/reference/catan-catanf-catanl.md)|Karmaşık bir sayının karmaşık yay tanjantını hesaplama|
|[ccos, ccosf, ccosl](../c-runtime-library/reference/ccos-ccosf-ccosl.md)|Karmaşık bir sayının karmaşık kosinüsünü hesaplama|
|[csin, csinf, csinl](../c-runtime-library/reference/csin-csinf-csinl.md)|Karmaşık bir sayının karmaşık sinüsünü hesaplama|
|[ctan, ctanf, ctanl](../c-runtime-library/reference/ctan-ctanf-ctanl.md)|Karmaşık bir sayının karmaşık tanjantını hesaplama|

## <a name="hyperbolic-functions"></a>Hiperbolik İşlevler

|İşlev|Açıklama|
|-|-|
|[cacosh, cacoshf, cacoshl](../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)|Karmaşık bir sayının karmaşık Ark hiperbolik kosinüsünü hesaplama|
|[casinh, casinhf, casinhl](../c-runtime-library/reference/casinh-casinhf-casinhl.md)|Karmaşık bir sayının karmaşık yay hiperbolik sinüsünü hesaplama|
|[catanh, catanhf, catanhl](../c-runtime-library/reference/catanh-catanhf-catanhl.md)|Karmaşık bir sayının karmaşık yay hiperbolik tanjantını hesaplama|
|[ccosh, ccoshf, ccoshl](../c-runtime-library/reference/ccosh-ccoshf-ccoshl.md)|Karmaşık bir sayının karmaşık hiperbolik kosinüsünü hesaplama|
|[csinh, csinhf, csinhl](../c-runtime-library/reference/csinh-csinhf-csinhl.md)|Karmaşık bir sayının karmaşık hiperbolik sinüsünü hesaplama|
|[ctanh, ctanhf, ctanhl](../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)|Karmaşık bir sayının karmaşık hiperbolik tanjantını hesaplama|

## <a name="exponential-and-logarithmic-functions"></a>Üstel ve Logaritmik işlevler

|İşlev|Açıklama|
|-|-|
|[cexp, cexpf, cexpl](../c-runtime-library/reference/cexp-cexpf-cexpl.md)|Karmaşık bir sayının karmaşık taban*e* üssünü hesaplama|
|[clog, clogf, clogl](../c-runtime-library/reference/clog-clogf-clogl.md)|Karmaşık bir sayının karmaşık doğal (taban-*e*) logaritmasını hesaplama|
|[clog10, clog10f, clog10l](../c-runtime-library/reference/clog10-clog10f-clog10l.md)|Karmaşık bir sayının karmaşık 10 tabanında logaritmasını hesaplama|

## <a name="power-and-absolute-value-functions"></a>Güç ve mutlak değer işlevleri

|İşlev|Açıklama|
|-|-|
|[cabs, cabsf, cabsl](../c-runtime-library/reference/cabs-cabsf-cabsl.md)|Karmaşık bir sayının karmaşık mutlak değerini (Norm, mod veya büyüklük olarak da bilinir) hesaplama|
|[cpow, cpowf, cpowl](../c-runtime-library/reference/cpow-cpowf-cpowl.md)|X<sup>y</sup> karmaşık güç işlevini hesaplama|
|[csqrt, csqrtf, csqrtl](../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)|Karmaşık bir sayının karmaşık kare kökünü hesaplama|

## <a name="manipulation-functions"></a>İşleme işlevleri

|İşlev|Açıklama|
|-|-|
|[_Cbuild, _FCbuild, _LCbuild](../c-runtime-library/reference/cbuild-fcbuild-lcbuild.md)|Gerçek ve sanal parçalardan karmaşık bir sayı oluşturun|
|[carg, cargf, cargl](../c-runtime-library/reference/carg-cargf-cargl.md)|Karmaşık bir sayının bağımsız değişkenini (aşama açısı da denir) hesaplama|
|[cimag, cimagf, cimagl](../c-runtime-library/reference/cimag-cimagf-cimagl.md)|Karmaşık bir sayının sanal bölümünü hesaplama|
|[conj, conjf, conjl](../c-runtime-library/reference/conj-conjf-conjl.md)|Karmaşık bir sayının karmaşık eşleniğini hesaplama|
|[cproj, cprojf, cprojl](../c-runtime-library/reference/cproj-cprojf-cprojl.md)|Karmaşık bir sayının, Riemann sphere üzerine projeksiyonu hesaplama|
|[creal, crealf, creall](../c-runtime-library/reference/creal-crealf-creall.md)|Karmaşık bir sayının gerçek bölümünü hesaplama|
|[norm, normf, norml](../c-runtime-library/reference/norm-normf-norml1.md)|Karmaşık bir sayının kare cinsinden büyüklüğünü hesaplama|

## <a name="operation-functions"></a>İşlem işlevleri

Karmaşık numaralar Microsoft derleyicisinde yerel bir tür olmadığından, standart aritmetik işleçler karmaşık türlerde tanımlı değildir. Kolaylık olması için, bu karmaşık matematik kitaplığı işlevleri, Kullanıcı kodunda karmaşık sayıların sınırlı işlemesini etkinleştirmek üzere verilmiştir:

|İşlev|Açıklama|
|-|-|
|[_Cmulcc, _FCmulcc, _LCmulcc](../c-runtime-library/reference/cmulcc-fcmulcc-lcmulcc.md)|İki karmaşık sayıyı çarp|
|[_Cmulcr, _FCmulcr, _LCmulcr](../c-runtime-library/reference/cmulcr-fcmulcr-lcmulcr.md)|Karmaşık ve kayan noktalı bir sayıyı çarpma|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
