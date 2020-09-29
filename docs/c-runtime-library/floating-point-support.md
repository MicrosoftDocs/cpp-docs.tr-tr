---
title: Matematik ve kayan nokta desteği
description: Microsoft Universal C çalışma zamanı kitaplığı 'nda (UCRT) kayan nokta desteğini açıklar
ms.date: 9/14/2020
f1_keywords:
- c.math
helpviewer_keywords:
- floating-point numbers, math routines
- math routines
- floating-point numbers
ms.assetid: e4fcaf69-5c8e-4854-a9bb-1f412042131e
ms.openlocfilehash: d1caaf5c9c0cfc7a3b6650bcb72a66b4c0028e28
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502116"
---
# <a name="math-and-floating-point-support"></a>Matematik ve kayan nokta desteği

Evrensel C çalışma zamanı kitaplığı (UCRT), ISO C99 tarafından gerekenlerden bazıları dahil olmak üzere çok sayıda integral ve kayan nokta matematik kitaplığı işlevi sağlar. Kayan nokta işlevleri, performansı doğruluk altına alacak şekilde uygulanır. Doğru şekilde yuvarlanmış sonucun üretilmesi, canlı olarak elde edilebilir hale gelebilir, ancak bu işlevler doğru bir şekilde yuvarlanmış sonuca yakın bir şekilde bir kapatma sağlamak üzere tasarlanmıştır. Çoğu durumda, üretilen sonuç doğru bir şekilde yuvarlanmış sonucu +/-1 ULP içinde, ancak daha fazla doğruluk olduğu durumlar olabilir.

ISO C standart 11 (C11) ve üzeri için \<tgmath.h> üst bilgi, ve dahil olmak üzere ek olarak, \<math.h> \<complex.h> parametrelerinin türlerine göre ilgili matematik işlevini çağıran makrolar sağlar. Ayrıntılar için bkz. [tür-genel matematik](tgmath.md) .

Kayan nokta matematik kitaplığı işlevlerinin birçoğu, farklı CPU mimarileri için farklı uygulamalara sahiptir. Örneğin, 32 bit x86 CRT, 64 bit x64 CRT 'den farklı bir uygulamaya sahip olabilir. Ayrıca, bazı işlevlerden belirli bir CPU mimarisi için birden çok uygulama olabilir. En verimli uygulama, CPU tarafından desteklenen yönerge kümelerine bağlı olarak çalışma zamanında dinamik olarak seçilir. Örneğin, 32 bit x86 CRT 'de, bazı işlevlerde hem x87 uygulama hem de bir SSE2 uygulama vardır. SSE2 destekleyen bir CPU üzerinde çalışırken, daha hızlı SSE2 uygulama kullanılır. SSE2 desteklemeyen bir CPU üzerinde çalışırken, daha yavaş x87 uygulama kullanılır. Matematik kitaplığı işlevlerinin farklı uygulamaları, sonuçlarını oluşturmak için farklı CPU yönergeleri ve farklı algoritmalar kullanabileceğinden, işlevler CPU 'larda farklı sonuçlar üretebilir. Çoğu durumda, sonuçlar doğru bir şekilde yuvarlanmış sonucu +/-1 ULP içinde, ancak gerçek sonuçlar CPU 'larda farklılık gösterebilir.

Microsoft C/C++ ' ın önceki 16 bit sürümleri ve Microsoft Visual C++ **`long double`** türü 80 bitlik bir duyarlık kayan nokta veri türü olarak destekliyordu. Visual C++ sonraki sürümlerinde **`long double`** veri türü, türü ile özdeş olan 64 bitlik bir duyarlık kayan nokta veri türüdür **`double`** . Derleyici, **`long double`** ve **`double`** ayrı türler olarak davranır, ancak **`long double`** işlevler **`double`** karşılıklarıyla aynıdır. CRT, **`long double`** ISO C99 kaynak kodu uyumluluğu için matematik işlevlerinin sürümlerini sağlar, ancak ikili temsilinin diğer derleyicilerden farklı olabileceğini unutmayın.

## <a name="supported-math-and-floating-point-routines"></a>Desteklenen matematik ve kayan nokta yordamları

|Yordam|Kullanın|
|-|-|
[abs, labs, llabs, _abs64](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Bir tamsayı türünün mutlak değerini hesaplar
[acos, acosf, acosl](../c-runtime-library/reference/acos-acosf-acosl.md)|Yay kosinüs değerini hesaplar
[acosh, acoshf, acoshl](../c-runtime-library/reference/acosh-acoshf-acoshl.md)|Hiperbolik yay kosinüs değerini hesaplar
[asin, asinf, asinl](../c-runtime-library/reference/asin-asinf-asinl.md)|Yay sinüsünü hesaplar
[asinh, asinhf, asinhl](../c-runtime-library/reference/asinh-asinhf-asinhl.md)|Hiperbolik yay sinüsünü hesaplar
[atan, atanf, atanl, atan2, atan2f, atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Yay tanjantını hesaplar
[atanh, atanhf, atanhl](../c-runtime-library/reference/atanh-atanhf-atanhl.md)|Hiperbolik yay tanjantını hesaplar
[_atodbl, _atodbl_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Yerel ayara özgü bir dizeyi öğesine dönüştürür **`double`**
[atof, _atof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Bir dizeyi öğesine dönüştürür **`double`**
[_atoflt, _atoflt_l, _atoldbl, _atoldbl_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Yerel ayara özgü dizeyi bir veya öğesine dönüştürür **`float`****`long double`**
[cbrt, cbrtf, cbrtl](../c-runtime-library/reference/cbrt-cbrtf-cbrtl.md)|Küp kökünü hesaplar
[ceil, ceilf, ceill](../c-runtime-library/reference/ceil-ceilf-ceill.md)|Tavan hesaplar
[_chgsign, _chgsignf, _chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|Toplamsal tersini hesaplar
[_clear87, _clearfp](../c-runtime-library/reference/clear87-clearfp.md)|Kayan nokta durum kaydını alır ve temizler
[_control87, \_ _control87_2, _controlfp](../c-runtime-library/reference/control87-controlfp-control87-2.md)|Kayan nokta denetim sözcüğünü alır ve ayarlar
[_controlfp_s](../c-runtime-library/reference/controlfp-s.md)|**_Controlfp** güvenli sürümü
[copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|Bir bağımsız değişkenin büyüklüğüne ve diğerinin işaretine sahip bir değer döndürür
[cos, cosf, cosl](../c-runtime-library/reference/cos-cosf-cosl.md)|Sinüsü hesaplar
[cosh, coshf, coshl](../c-runtime-library/reference/cosh-coshf-coshl.md)|Hiperbolik sinüsü hesaplar
[div, ldiv, lldiv](../c-runtime-library/reference/div.md)|Bölümü ve iki tamsayı değerinin kalanını hesaplar
[_ecvt](../c-runtime-library/reference/ecvt.md), [ecvt](../c-runtime-library/reference/posix-ecvt.md)|Bir **`double`** dizeye dönüştürür
[_ecvt_s](../c-runtime-library/reference/ecvt-s.md)|**_Ecvt** güvenli sürümü
[HATAİŞLEV, erff, ERFL](../c-runtime-library/reference/erf-erff-erfl-erfc-erfcf-erfcl.md)|Hata işlevini hesaplar
[erfc, erfcf, erfcl](../c-runtime-library/reference/erf-erff-erfl-erfc-erfcf-erfcl.md)|Tamamlayıcı hata işlevini hesaplar
[exp, expf, expl](../c-runtime-library/reference/exp-expf.md)|Üstel *e*<sup>x</sup> 'i hesaplar
[exp2, exp2f, exp2l](../c-runtime-library/reference/exp2-exp2f-exp2l.md)|Üstel 2<sup>x</sup> 'i hesaplar
[expm1, expm1f, expm1l](../c-runtime-library/reference/expm1-expm1f-expm1l.md)|*E*<sup>x</sup>-1 hesaplar
[fabs, fabsf, fabsl](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|Kayan nokta türünün mutlak değerini hesaplar
[_fcvt](../c-runtime-library/reference/fcvt.md), [fcvt](../c-runtime-library/reference/posix-fcvt.md)|Kayan noktalı sayıyı dizeye dönüştürür
[_fcvt_s](../c-runtime-library/reference/fcvt-s.md)|**_Fcvt** güvenli sürümü
[fdim, fdimf, fdiml](../c-runtime-library/reference/fdim-fdimf-fdiml.md)|İki değer arasındaki pozitif farkı belirler
[feclearexcept](../c-runtime-library/reference/feclearexcept1.md)|Belirtilen kayan nokta özel durumlarını temizler
[fegetenv](../c-runtime-library/reference/fegetenv1.md)|Geçerli kayan nokta ortamını depolar
[fegetexceptflag](../c-runtime-library/reference/fegetexceptflag2.md)|Belirtilen kayan nokta özel durum durumunu alır
[fegetround](../c-runtime-library/reference/fegetround-fesetround2.md)|Kayan nokta yuvarlama modunu alır
[feholdexcept](../c-runtime-library/reference/feholdexcept2.md)|Durdurma olmayan kayan nokta özel durum modunu ayarlar
[feraiseexcept](../c-runtime-library/reference/feraiseexcept.md)|Belirtilen kayan nokta özel durumlarını başlatır
[fesetenv](../c-runtime-library/reference/fesetenv1.md)|Geçerli kayan nokta ortamını ayarlar
[fesetexceptflag](../c-runtime-library/reference/fesetexceptflag2.md)|Belirtilen kayan nokta durum bayraklarını ayarlar
[fesetround](../c-runtime-library/reference/fegetround-fesetround2.md)|Belirtilen kayan nokta yuvarlama modunu ayarlar
[fetestexcept](../c-runtime-library/reference/fetestexcept1.md)|Hangi kayan nokta özel durum bayraklarının ayarlandığını belirler
[feupdateenv](../c-runtime-library/reference/feupdateenv.md)|Kayan nokta ortamını geri yükler ve önceki özel durumları başlatır
[floor, floorf, floorl](../c-runtime-library/reference/floor-floorf-floorl.md)|Tabanı hesaplar
[fma, fmaf, fmal](../c-runtime-library/reference/fma-fmaf-fmal.md)|Bir fkullanılan çarpmayı hesaplar-Ekle
[fmax, fmaxf, fmaxl](../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)|Bağımsız değişkenlerin en büyük sayısını hesaplar
[fmin, fminf, fminl](../c-runtime-library/reference/fmin-fminf-fminl.md)|Bağımsız değişkenlerin minimum sayısını hesaplar
[FMOD, fmodf, fmodl](../c-runtime-library/reference/fmod-fmodf.md)|Kayan nokta kalanını hesaplar
[_fpclass, _fpclassf](../c-runtime-library/reference/fpclass-fpclassf.md)|Kayan nokta değerinin sınıflandırmasını döndürür
[fpclassify](../c-runtime-library/reference/fpclassify.md)|Kayan nokta değerinin sınıflandırmasını döndürür
[_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md)|Kayan nokta özel durumları için bir işleyici ayarlar
[_fpreset](../c-runtime-library/reference/fpreset.md)|Kayan nokta ortamını sıfırlar
[frexp, frexpf, frexpl](../c-runtime-library/reference/frexp.md)|Kayan noktalı bir sayının Mantis ve üssünü alır
[_gcvt](../c-runtime-library/reference/gcvt.md), [gcvt](../c-runtime-library/reference/posix-gcvt.md)|Kayan noktalı sayıyı dizeye dönüştürür
[_gcvt_s](../c-runtime-library/reference/gcvt-s.md)|**_Gcvt** güvenli sürümü
[_get_FMA3_enable, _set_FMA3_enable](../c-runtime-library/reference/get-fma3-enable-set-fma3-enable.md)|X64 üzerinde FMA3 yönergelerinin kullanımı için bir bayrak alır veya ayarlar
[hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|Hipotenüsü hesaplar
[ilogb, ilogbf, ilogbl](../c-runtime-library/reference/ilogb-ilogbf-ilogbl2.md)|Taban-2 üssün oluşan tamsayıyı hesaplar
[imaxabs](../c-runtime-library/reference/imaxabs.md)|Bir tamsayı türünün mutlak değerini hesaplar
[imaxdiv](../c-runtime-library/reference/imaxdiv.md)|Bölümü ve iki tamsayı değerinin kalanını hesaplar
[isfinite, _finite, _finitef](../c-runtime-library/reference/finite-finitef.md)|Değerin sonlu olup olmadığını belirler
[isgreater, isgreaterequal, isless, islessequal, islessgreater, isunordered](../c-runtime-library/reference/floating-point-ordering.md)|İki kayan nokta değerinin sırasını karşılaştırın
[isinf](../c-runtime-library/reference/isinf.md)|Kayan nokta değerinin sonsuz olup olmadığını belirler
[isnan, _isnan, _isnanf](../c-runtime-library/reference/isnan-isnan-isnanf.md)|NaN için kayan noktalı bir değer sınar
[isnormal](../c-runtime-library/reference/isnormal.md)|Kayan nokta değerinin hem sonlu hem de alt normal olmadığını sınar
[_j0, _j1, _jn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|Bessel işlevini hesaplar
[ldexp, ldexpf, ldexpl](../c-runtime-library/reference/ldexp.md)|Hesaplar x * 2<sup>n</sup>
[lgamma, lgammaf, lgammal](../c-runtime-library/reference/lgamma-lgammaf-lgammal.md)|Gama işlevinin mutlak logaritmasına ilişkin doğal logaritmayı hesaplar
[llrint, llrintf, llrintl](../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)|Kayan noktalı bir değeri en yakın **`long long`** değere yuvarlar
[llround, llroundf, llroundl](../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)|Kayan noktalı bir değeri en yakın **`long long`** değere yuvarlar
[log, logf, logl, log10, log10f, log10l](../c-runtime-library/reference/log-logf-log10-log10f.md)|Doğal veya 10 tabanında logaritmayı hesaplar
[log1p, log1pf, log1pl](../c-runtime-library/reference/log1p-log1pf-log1pl2.md)|1 + x 'in doğal logaritmasını hesaplar
[log2, log2f, log2l](../c-runtime-library/reference/log2-log2f-log2l.md)|2 tabanında logaritmayı hesaplar
[logb, logbf, logbl, _logb, _logbf](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|Kayan nokta değerinin üssünü döndürür
[lrint, lrintf, lrintl](../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)|Kayan noktalı bir değeri en yakın **`long`** değere yuvarlar
[_lrotl, _lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|Bir tamsayı değerini sola veya sağa döndürür
[lround, lroundf, lroundl](../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)|Kayan noktalı bir değeri en yakın **`long`** değere yuvarlar
[_matherr](../c-runtime-library/reference/matherr.md)|Varsayılan matematik hata işleyicisi
[__max](../c-runtime-library/reference/max.md)|İki değerden daha büyük bir değer döndüren makro
[__min](../c-runtime-library/reference/min.md)|İki değerden daha küçük bir değer döndüren makro
[modf, modff, modfl](../c-runtime-library/reference/modf-modff-modfl.md)|Kayan nokta değerini kesirli ve tamsayı bölümlerine böler
[nan, nanf, nanl](../c-runtime-library/reference/nan-nanf-nanl.md)|Sessiz bir NaN değeri döndürür
[nearbyint, nearbyintf, nearbyintl](../c-runtime-library/reference/nearbyint-nearbyintf-nearbyintl1.md)|Yuvarlatılmış değeri döndürür
[nextafter, nextafterf, nextafterl, _nextafter _nextafterf](../c-runtime-library/reference/nextafter-functions.md)|Sonraki gösterilemeyen kayan nokta değerini döndürür
[Next, nexttowardf, nexttowardl](../c-runtime-library/reference/nextafter-functions.md)|Sonraki gösterilemeyen kayan nokta değerini döndürür
[pow, powf, powl](../c-runtime-library/reference/pow-powf-powl.md)|*X*<sup>*y*</sup> değerini döndürür
[remainder, remainderf, remainderl](../c-runtime-library/reference/remainder-remainderf-remainderl.md)|İki kayan nokta değerinin kalan bölümünü hesaplar
[remquo, remquof, remquol](../c-runtime-library/reference/remquo-remquof-remquol.md)|İki tamsayı değerinin kalanını hesaplar
[rint, rintf, rintl](../c-runtime-library/reference/rint-rintf-rintl.md)|Kayan nokta değerini yuvarlar
[_rotl, _rotl64, _rotr, _rotr64](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|Tamsayı türlerinde bitleri döndürür
[round, roundf, roundl](../c-runtime-library/reference/round-roundf-roundl.md)|Kayan nokta değerini yuvarlar
[_scalb, _scalbf](../c-runtime-library/reference/scalb.md)|Bağımsız değişkeni 2 kuvvetle ölçeklendirir
[scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl](../c-runtime-library/reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md)|Kayan noktalı sayıyı **FLT_RADIX** integral bir gücüyle çarpar
[_set_controlfp](../c-runtime-library/reference/set-controlfp.md)|Kayan nokta denetim sözcüğünü ayarlar
[_set_SSE2_enable](../c-runtime-library/reference/set-sse2-enable.md)|SSE2 talimatlarını etkinleştirilir veya devre dışı bırakır
[signbit](../c-runtime-library/reference/signbit.md)|Kayan nokta değerinin işaret bitini sınar
[sin, sinf, sinl](../c-runtime-library/reference/sin-sinf-sinl.md)|Sinüsü hesaplar
[sinh, sinhf, sinhl](../c-runtime-library/reference/sinh-sinhf-sinhl.md)|Hiperbolik sinüsü hesaplar
[sqrt, sqrtf, sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|Kare kökünü hesaplar
[_status87, _statusfp, _statusfp2](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|Kayan nokta durum sözcüğünü alır
[strtof, _strtof_l](../c-runtime-library/reference/strtof-strtof-l-wcstof-wcstof-l.md)|Bir dizeyi öğesine dönüştürür **`float`**
[strsöyle, _strtold_l](../c-runtime-library/reference/strtold-strtold-l-wcstold-wcstold-l.md)|Bir dizeyi öğesine dönüştürür **`long double`**
[tan, tanf, tanl](../c-runtime-library/reference/tan-tanf-tanl.md)|Tanjantı hesaplar
[tanh, tanhf, tanhl](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|Hiperbolik tanjantı hesaplar
[tgamma, tgammaf, tgammal](../c-runtime-library/reference/tgamma-tgammaf-tgammal.md)|Gama işlevini hesaplar
[trunc, truncf, truncl](../c-runtime-library/reference/trunc-truncf-truncl.md)|Kesirli kısmını keser
[_wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Geniş bir dizeyi öğesine dönüştürür **`double`**
[_y0, _y1, _yn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|Bessel işlevini hesaplar

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)\
[Kayan nokta temel elemanları](../c-runtime-library/reference/floating-point-primitives.md)
