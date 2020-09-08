---
title: Tür-genel matematik
description: Bağımsız değişken türüne göre doğru matematik işlevini çağıran C kodu yazmayı kolaylaştıran <tgmath. h> içindeki makroları açıklar.
ms.date: 9/3/2020
helpviewer_keywords:
- CRT tgmath.h
ms.openlocfilehash: 8994edcaa05247a16d90b47bca8ec26fca27cda7
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89557679"
---
# <a name="type-generic-math"></a>Tür-genel matematik

ISO C standart 11 (C11) ve üzeri için \<tgmath.h> üst bilgi, ve dahil olmak üzere ek olarak, \<math.h> \<complex.h> parametrelerinin türlerine göre ilgili matematik işlevini çağıran makrolar sağlar.

C çalışma zamanı kitaplığı matematik işlevleri gerçek ve karmaşık değişkenlerde gelir. Her varyant, bağımsız değişkenin türüne bağlı olarak üç çeşitlerle gelir: `float` , `double` ve `long double` . C, C++ gibi aşırı yüklemeyi desteklemediğinden, her çeşit farklı bir ada sahiptir. Örneğin, gerçek bir kayan nokta değerinin mutlak değerini almak için,, ya da, sırasıyla, veya `fabsf` `fabs` `fabsl` değeri geçirdiğinize bağlı olarak, veya ' `float` `double` ı çağırın `long double` . Karmaşık mutlak değeri almak için,,, ve ' den birini, sırasıyla,, `cabsf` `cabs` `cabsl` `float` `double` ve karmaşık bir değer geçirdiğinize bağlı olarak çağırın `long double` . Bağımsız değişkenler yukarıda bahsedilen türlerden hiçbiriyle eşleşmezse, bağımsız değişkenler Double olsa da işlev seçilir.

\<tgmath.h> çağırmak için doğru matematik işlevinin seçimini kolaylaştıran makrolar içerir. Makrolar geçirdikleri türü inceler ve sonra sağ işlevi çağırır. Örneğin, makro öğesine bağlandığında öğesine bağlanır `sqrt` `sqrt(9.9f)` `sqrtf()` `sqrt(9.9)` `sqrt()` . Genel parametre için en az bir makro bağımsız değişkeni karmaşıksa, makro karmaşık bir işleve bağlanır; Aksi takdirde, gerçek bir işlevi çağırır.

İçindeki tür genel makrolar, \<tgmath.h> bağımsız değişken türüne göre atama veya farklı işlev adları seçmeyi gerektirmeyen daha taşınabilir kod yazmanızı sağlar.

Bu makrolar kendi üst bilgisinde bulunur, böylece üst bilgi kullanılarak yazılan programlar `<math.h>` kesilir. `double x = sin(42);`Bu nedenle, her zaman eklediğiniz sırada olduğu gibi davranır \<math.h> . Bu durumda bile, \<tgmath.h> veya yerine üst bilgi dahil edildiğinde mevcut C programlarının çoğu etkilenmez \<math.h> \<complex.h> .

Aşağıdaki tabloda ' de kullanılabilen makrolar \<tgmath.h> ve neleri genişlettikleri listelenmiştir. `modf` karşılık gelen bir tür genel makrosu olmadığından bu tabloya dahil değildir çünkü tür çözümlemesini karmaşımmadan güvenli hale getirme seçimini yapmaz.

|Makroya  |Gerçek</br>`float`  | Gerçek</br>`double` | Gerçek</br>`long double` | Complex</br>`float` | Complex</br>`double` | Complex</br>`long double` |
|---------|---------|---------|---------|---------|---------|---------|
`acos` | [acosf](reference/mbsnbicmp-mbsnbicmp-l.md) | [acos](reference/mbsnbicmp-mbsnbicmp-l.md) | [acosl](reference/mbsnbicmp-mbsnbicmp-l.md) | [cacosf](reference/cacos-cacosf-cacosl.md) | [Kacos](reference/cacos-cacosf-cacosl.md) | [kacosl](reference/cacos-cacosf-cacosl.md) |
`acosh` | [acoshf](reference/acosh-acoshf-acoshl.md) | [acosh](reference/acosh-acoshf-acoshl.md) | [acoshl](reference/acosh-acoshf-acoshl.md) | [cacoshf](reference/cacosh-cacoshf-cacoshl.md) | [cacosh](reference/cacosh-cacoshf-cacoshl.md) | [kacoşl](reference/cacosh-cacoshf-cacoshl.md) |
`asin` | [asinf](reference/asin-asinf-asinl.md) | [Asin](reference/asin-asinf-asinl.md) | [asinl](reference/asin-asinf-asinl.md) | [casinf](reference/casin-casinf-casinl.md) | [Casin](reference/casin-casinf-casinl.md) | [casinl](reference/casin-casinf-casinl.md) |
`asinh` | [asinhf](reference/asin-asinf-asinl.md) | [ASİNH](reference/asin-asinf-asinl.md) | [asinhl](reference/asin-asinf-asinl.md) | [casinhf](reference/casinh-casinhf-casinhl.md) | [casinh](reference/casinh-casinhf-casinhl.md) | [casinhl](reference/casinh-casinhf-casinhl.md) |
`atan` | [atanf](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [atan](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [atanl](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [catanf](reference/catan-catanf-catanl.md) | [Catan dili](reference/catan-catanf-catanl.md) | [catanl](reference/catan-catanf-catanl.md) |
`atanh` | [atanhf](reference/atanh-atanhf-atanhl.md) | [ATANH](reference/atanh-atanhf-atanhl.md) | [atanhl](reference/atanh-atanhf-atanhl.md) | [catanhf](reference/catanh-catanhf-catanhl.md) | [catanh](reference/catanh-catanhf-catanhl.md) | [catanhl](reference/catanh-catanhf-catanhl.md) |
`cos` | [cosf](reference/cos-cosf-cosl.md) | [cos](reference/cos-cosf-cosl.md) | [COSL](reference/cos-cosf-cosl.md) | [ccosf](reference/ccos-ccosf-ccosl.md) | [ccos](reference/ccos-ccosf-ccosl.md) | [ccosl](reference/ccos-ccosf-ccosl.md) |
`cosh` | [coshf](reference/cosh-coshf-coshl.md) | [Cosh](reference/cosh-coshf-coshl.md) | [coshl](reference/cosh-coshf-coshl.md) | [ccoshf](reference/ccosh-ccoshf-ccoshl.md) | [ccosh](reference/ccosh-ccoshf-ccoshl.md) | [ccoshl](reference/ccosh-ccoshf-ccoshl.md) |
`exp` | [expf](reference/exp-expf.md) | [exp](reference/exp-expf.md) | [expl](reference/exp-expf.md) | [cexpf](reference/cexp-cexpf-cexpl.md) | [cexp](reference/cexp-cexpf-cexpl.md) | [cexpl](reference/cexp-cexpf-cexpl.md) |
`fabs` | [fabsf](reference/fabs-fabsf-fabsl.md) | [fabs](reference/fabs-fabsf-fabsl.md) | [fabsl](reference/fabs-fabsf-fabsl.md) | [cabsf](reference/cabs-cabsf-cabsl.md) | [Cabs](reference/cabs-cabsf-cabsl.md) | [cabsl](reference/cabs-cabsf-cabsl.md) |
`log` | [logf](reference/log-logf-log10-log10f.md) | [açmasını](reference/log-logf-log10-log10f.md) | [günlüğe kaydetme](reference/log-logf-log10-log10f.md) | [clogf](reference/clog-clogf-clogl.md) | [CLOG](reference/clog-clogf-clogl.md) | [clogl](reference/clog-clogf-clogl.md) |
`pow` | [powf](reference/pow-powf-powl.md) | [POW](reference/pow-powf-powl.md) | [ptıl](reference/pow-powf-powl.md) | [cpowf](reference/cpow-cpowf-cpowl.md) | [cpow](reference/cpow-cpowf-cpowl.md) | [cpowl](reference/cpow-cpowf-cpowl.md) |
`sin` | [sinf](reference/sin-sinf-sinl.md) | [sin](reference/sin-sinf-sinl.md) | [sinl](reference/sin-sinf-sinl.md) | [csinf](reference/csin-csinf-csinl.md) | [CSV](reference/csin-csinf-csinl.md) | [csinl](reference/csin-csinf-csinl.md) |
`sinh` | [sinhf](reference/sinh-sinhf-sinhl.md) | [sinh](reference/sinh-sinhf-sinhl.md) | [sinhl](reference/sinh-sinhf-sinhl.md) | [csinhf](reference/csinh-csinhf-csinhl.md) | [csinh](reference/csinh-csinhf-csinhl.md) | [csinhl](reference/csinh-csinhf-csinhl.md) |
`sqrt` | [sqrtf](reference/sqrt-sqrtf-sqrtl.md) | [k](reference/sqrt-sqrtf-sqrtl.md) | [sqrtl](reference/sqrt-sqrtf-sqrtl.md) | [csqrtf](reference/csqrt-csqrtf-csqrtl.md) | [csqrt](reference/csqrt-csqrtf-csqrtl.md) | [csqrtl](reference/csqrt-csqrtf-csqrtl.md) |
`tan` | [tanf](reference/tan-tanf-tanl.md) | [Başlangıçtan](reference/tan-tanf-tanl.md) | [tanl](reference/tan-tanf-tanl.md) | [ctanf](reference/ctan-ctanf-ctanl.md) | [ctan dili](reference/ctan-ctanf-ctanl.md) | [ctanl](reference/ctan-ctanf-ctanl.md) |
`tanh` | [tanhf](reference/tanh-tanhf-tanhl.md) | [tanh](reference/tanh-tanhf-tanhl.md) | [tanhl](reference/tanh-tanhf-tanhl.md) | [ctanhf](reference/ctanh-ctanhf-ctanhl.md) | [ctanh](reference/ctanh-ctanhf-ctanhl.md) | [ctanhl](reference/ctanh-ctanhf-ctanhl.md) |
`atan2` | [atan2f](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [atan2](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [atan2l](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | - | - | - |
`cbrt` | [cbrtf](reference/cbrt-cbrtf-cbrtl.md) | [cbrt](reference/cbrt-cbrtf-cbrtl.md) | [cbrtl](reference/cbrt-cbrtf-cbrtl.md) | - | - | - |
`ceil` | [ceilf](reference/ceil-ceilf-ceill.md) | [Ceil](reference/ceil-ceilf-ceill.md) | [ceill](reference/ceil-ceilf-ceill.md) | - | - | - |
`copysign` | [copysignf](reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md) | [copysign](reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md) | [copysignl](reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md) | - | - | - |
`erf` | [erff](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | [işlevi](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | [ERFL](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | - | - | - |
`erfc` | [erfcf](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | [erfc](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | [erfcl](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | - | - | - |
`exp2` | [exp2f](reference/exp2-exp2f-exp2l.md) | [exp2](reference/exp2-exp2f-exp2l.md) | [exp2l](reference/exp2-exp2f-exp2l.md) | - | - | - |
`expm1` | [expm1f](reference/expm1-expm1f-expm1l.md) | [expm1](reference/expm1-expm1f-expm1l.md) | [expm1l](reference/expm1-expm1f-expm1l.md) | - | - | - |
`fdim` | [fdimf](reference/fdim-fdimf-fdiml.md) | [fdim](reference/fdim-fdimf-fdiml.md) | [fdiml](reference/fdim-fdimf-fdiml.md) | - | - | - |
`floor` | [floorf](reference/floor-floorf-floorl.md) | [sını](reference/floor-floorf-floorl.md) | [floorl](reference/floor-floorf-floorl.md) | - | - | - |
`fma` | [fmaf](reference/fma-fmaf-fmal.md) | [FMA](reference/fma-fmaf-fmal.md) | [Fmal](reference/fma-fmaf-fmal.md) | - | - | - |
`fmax` | [fmaxf](reference/fmax-fmaxf-fmaxl.md) | [Fmax](reference/fmax-fmaxf-fmaxl.md) | [fmaxl](reference/fmax-fmaxf-fmaxl.md) | - | - | - |
`fmin` | [fminf](reference/fmin-fminf-fminl.md) | [fmin](reference/fmin-fminf-fminl.md) | [fminl](reference/fmin-fminf-fminl.md) | - | - | - |
`fmod` | [fmodf](reference/fmod-fmodf.md) | [FMOD](reference/fmod-fmodf.md) | [fmodl](reference/fmod-fmodf.md) | - | - | - |
`frexp` | [frexpf](reference/frexp.md) | [frexp](reference/frexp.md) | [frexpl](reference/frexp.md) | - | - | - |
`hypot` | [hypotf](reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md) | [hypot](reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md) | [hypotl](reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md) | - | - | - |
`ilogb` | [ilogbf](reference/ilogb-ilogbf-ilogbl2.md) | [ilogb](reference/ilogb-ilogbf-ilogbl2.md) | [ılogbl](reference/ilogb-ilogbf-ilogbl2.md) | - | - | - |
`ldexp` | [ldexpf](reference/ldexp.md) | [ldexp](reference/ldexp.md) | [ldexpl](reference/ldexp.md) | - | - | - |
`lgamma` | [lgammaf](reference/lgamma-lgammaf-lgammal.md) | [lgamma](reference/lgamma-lgammaf-lgammal.md) | [lgammal](reference/lgamma-lgammaf-lgammal.md) | - | - | - |
`llrint` | [llrintf](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | [llrint](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | [llrintl](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | - | - | - |
`llround` | [llroundf](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | [llround](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | [llroundl](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | - | - | - |
`log10` | [log10f](reference/log-logf-log10-log10f.md) | [log10](reference/log-logf-log10-log10f.md) | [log10l](reference/log-logf-log10-log10f.md) | - | - | - |
`log1p` | [log1pf](reference/log1p-log1pf-log1pl2.md) | [log1p](reference/log1p-log1pf-log1pl2.md) | [log1pl](reference/log1p-log1pf-log1pl2.md) | - | - | - |
`log2` | [log2f](reference/log2-log2f-log2l.md) | [log2](reference/log2-log2f-log2l.md) | [log2l](reference/log2-log2f-log2l.md) | - | - | - |
`logb` | [logbf](reference/logb-logbf-logbl-logb-logbf.md) | [logb](reference/logb-logbf-logbl-logb-logbf.md) | [logbl](reference/logb-logbf-logbl-logb-logbf.md) | - | - | - |
`lrint` | [lrintf](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | [lrint](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | [lrintl](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | - | - | - |
`lround` | [lroundf](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | [lround](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | [lroundl](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | - | - | - |
`nearbyint` | [nearbyintf](reference/nearbyint-nearbyintf-nearbyintl1.md) | [nearbyint](reference/nearbyint-nearbyintf-nearbyintl1.md) | [yaklaştığında, Ulusl](reference/nearbyint-nearbyintf-nearbyintl1.md) | - | - | - |
`nextafter` | [nextafterf](reference/nextafter-functions.md) | [nextafter](reference/nextafter-functions.md) | [nextafterl](reference/nextafter-functions.md) | - | - | - |
`nexttoward` | [nexttowardf](reference/nextafter-functions.md) | [nextdoğru](reference/nextafter-functions.md) | [nexttowardl](reference/nextafter-functions.md) | - | - | - |
`remainder` | [remainderf](reference/remainder-remainderf-remainderl.md) | [geri kalanında](reference/remainder-remainderf-remainderl.md) | [remainderl](reference/remainder-remainderf-remainderl.md) | - | - | - |
`remquo` | [remquof](reference/remquo-remquof-remquol.md) | [remquo](reference/remquo-remquof-remquol.md) | [remquol](reference/remquo-remquof-remquol.md) | - | - | - |
`rint` | [rintf](reference/rint-rintf-rintl.md) | [Yazdır](reference/rint-rintf-rintl.md) | [rintl](reference/rint-rintf-rintl.md) | - | - | - |
`round` | [roundf](reference/round-roundf-roundl.md) | [gidiş](reference/round-roundf-roundl.md) | [roundl](reference/round-roundf-roundl.md) | - | - | - |
`scalbln` | [scalblnf](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | [scalbln](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | [scalblnl](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | - | - | - |
`scalbn` | [scalbnf](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | [scalbn](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | [scalbümnl](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | - | - | - |
`tgamma` | [tgammaf](reference/tgamma-tgammaf-tgammal.md) | [tgamma](reference/tgamma-tgammaf-tgammal.md) | [tgammal](reference/tgamma-tgammaf-tgammal.md) | - | - | - |
`trunc` | [truncf](reference/trunc-truncf-truncl.md) | [TRUNC](reference/trunc-truncf-truncl.md) | [truncl](reference/trunc-truncf-truncl.md) | - | - | - |
`carg` | - | - | - | [cargf](reference/carg-cargf-cargl.md) | [Carg](reference/carg-cargf-cargl.md) | [cargl](reference/carg-cargf-cargl.md) |
`conj` | - | - | - | [conjf](reference/conj-conjf-conjl.md) | [conj](reference/conj-conjf-conjl.md) | [conjl](reference/conj-conjf-conjl.md) |
`creal` | - | - | - | [crealf](reference/creal-crealf-creall.md) | [creal](reference/creal-crealf-creall.md) | [Creall](reference/creal-crealf-creall.md) |
`cimag` | - | - | - | [cımıknatıf](reference/cimag-cimagf-cimagl.md) | [cımag](reference/cimag-cimagf-cimagl.md) | [cımagl](reference/cimag-cimagf-cimagl.md) |
`cproj` | - | - | - | [cprojf](reference/cproj-cprojf-cprojl.md) | [cproj](reference/cproj-cprojf-cprojl.md) | [cprojl](reference/cproj-cprojf-cprojl.md) |

## <a name="requirements"></a>Gereksinimler

[std: c++ 11](../build/reference/std-specify-language-standard-version.md) veya üzeri gereklidir.

Windows SDK sürüm 10.0.20201.0 veya üzeri.

## <a name="see-also"></a>Ayrıca bkz.

[C çalışma zamanı kitaplığı başvurusu](c-run-time-library-reference.md)
