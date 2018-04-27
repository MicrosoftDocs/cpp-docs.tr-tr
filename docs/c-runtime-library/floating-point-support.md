---
title: Matematik ve kayan nokta desteği | Microsoft Docs
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- c.math
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers, math routines
- math routines
- floating-point numbers
ms.assetid: e4fcaf69-5c8e-4854-a9bb-1f412042131e
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 358f47716ee998d5070e226ee71f865d6bfc64a4
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="math-and-floating-point-support"></a>Matematik ve kayan nokta desteği

Evrensel C çalışma zamanı kitaplığı (UCRT) tüm ISO C99 tarafından gerekli olanlar da dahil olmak üzere birçok Entegral ve kayan nokta matematik kitaplık işlevleri sağlar. Kayan nokta işlevleri performans doğruluk ile dengelemek için uygulanır. Doğru yuvarlatılmış sonuç üretme şekilde basımı karşılamayacak kadar pahalı olabilir çünkü bu işlevler verimli bir şekilde doğru yuvarlatılmış sonucu yaklaşık üretmek için tasarlanmıştır. Olabilir ancak durumlarda çoğu durumda, üretilen içinde doğru yuvarlatılmış sonuç 1 ulp +/-sonucudur büyük yanlış bilgi olduğu.

Kayan birçok noktasının matematik kitaplık işlevleri sahip farklı uygulamalar farklı CPU mimari için. Örneğin, 32-bit x86 CRT 64-bit x64 daha farklı bir uygulama olabilir CRT. Ayrıca, bazı işlevler belirli bir CPU mimarisi için birden çok uygulamaları olabilir. En verimli uygulama CPU tarafından desteklenen yönerge kümeleri bağlı olarak çalışma zamanında dinamik olarak seçilir. Örneğin, 32-bit x86 içinde CRT, bazı işlevler sahip hem bir x87 uygulama ve SSE2 uygulaması. SSE2 destekleyen bir CPU üzerinde çalışırken, daha hızlı SSE2 uygulama kullanılır. SSE2, uygulama kullanılan yavaş x87 desteklemeyen bir CPU üzerinde çalışırken. Matematik kitaplığı işlevlerin farklı uygulamalar farklı CPU yönergeleri ve farklı algoritmalar sonuçları üretmek için kullanılıyor olabileceğinden, işlevleri CPU'lar arasında farklı sonuçlar doğurabilir. Çoğu durumda, doğru yuvarlatılmış sonuç 1 ulp +/-içinde sonucu olan, ancak gerçek sonuçları CPU'lar arasında değişebilir.

Microsoft C/C++ ve desteklenen Microsoft Visual C++ önceki 16 bit sürümlerini **uzun çift** 80 bit duyarlık kayan nokta veri türü olarak türü. Visual C++, sonraki sürümlerinde **uzun çift** veri türü olan bir 64-bit duyarlık kayan nokta veri türü için aynı **çift** türü. Derleyici değerlendirir **uzun çift** ve **çift** farklı türler olarak ancak **uzun çift** işlevleri aynı kendi **çift** ortaklarınıza. CRT sağlar **uzun çift** ISO C99 matematik işlevleri sürümleri kaynak kod uyumluluğu, ancak diğer derleyiciler ikili gösterim değişebilir unutmayın.

## <a name="supported-math-and-floating-point-routines"></a>Desteklenen matematik ve kayan nokta yordamları

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-|-|
[abs, labs, llabs, _abs64](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Bir tamsayı türünde mutlak değeri hesaplar
[acos, acosf, acosl](../c-runtime-library/reference/acos-acosf-acosl.md)|Ark kosinüsünü hesaplar
[acosh, acoshf, acoshl](../c-runtime-library/reference/acosh-acoshf-acoshl.md)|Hiperbolik ark kosinüsünü hesaplar
[asin, asinf, asinl](../c-runtime-library/reference/asin-asinf-asinl.md)|Ark sinüsünü hesaplar
[asinh, asinhf, asinhl](../c-runtime-library/reference/asinh-asinhf-asinhl.md)|Hiperbolik ark sinüsünü hesaplar
[atan, atanf, atanl, atan2, atan2f, atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Ark tanjantını hesaplar
[atanh, atanhf, atanhl](../c-runtime-library/reference/atanh-atanhf-atanhl.md)|Hiperbolik ark tanjantını hesaplar
[_atodbl, _atodbl_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Yerel ayarlara özgü dizeye dönüştürür bir **çift**
[atof, _atof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Bir dizeye dönüştürür bir **çift**
[_atoflt, _atoflt_l, _atoldbl, _atoldbl_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Yerel ayarlara özgü dizeye dönüştürür bir **float** veya **uzun çift**
[cbrt, cbrtf, cbrtl](../c-runtime-library/reference/cbrt-cbrtf-cbrtl.md)|Küp kök hesaplar
[ceil, ceilf, ceill](../c-runtime-library/reference/ceil-ceilf-ceill.md)|Tavan hesaplar
[_chgsign, _chgsignf, _chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|ADDITIVE ters hesaplar
[_clear87, _clearfp](../c-runtime-library/reference/clear87-clearfp.md)|Alır ve kayan nokta durum kaydı temizler
[_control87, \__control87_2, _controlfp](../c-runtime-library/reference/control87-controlfp-control87-2.md)|Alır ve kayan nokta denetim sözcüğü ayarlar
[_controlfp_s](../c-runtime-library/reference/controlfp-s.md)|Güvenli sürümü **_controlfp**
[copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|Bir bağımsız değişken büyüklük ve başka bir oturum sahip bir değer döndürür
[cos, cosf, cosl](../c-runtime-library/reference/cos-cosf-cosl.md)|Sinüsünü hesaplar
[COSH, coshf, coshl](../c-runtime-library/reference/cosh-coshf-coshl.md)|Hiperbolik sinüsünü hesaplar
[div, ldiv, lldiv](../c-runtime-library/reference/div.md)|Sayının ve iki tamsayı değerleri geri kalanı hesaplar
[_ecvt](../c-runtime-library/reference/ecvt.md), [ecvt](../c-runtime-library/reference/posix-ecvt.md)|Dönüştüren bir **çift** dizeye
[_ecvt_s](../c-runtime-library/reference/ecvt-s.md)|Güvenli sürümü **_ecvt**
[erf, erff, erfl](../c-runtime-library/reference/erf-erff-erfl-erfc-erfcf-erfcl.md)|Hata işlevini hesaplar
[erfc, erfcf, erfcl](../c-runtime-library/reference/erf-erff-erfl-erfc-erfcf-erfcl.md)|Tamamlayıcı hata işlevini hesaplar
[exp, expf, expl](../c-runtime-library/reference/exp-expf.md)|Üstel hesaplar *e*<sup>x</sup>
[exp2, exp2f, exp2l](../c-runtime-library/reference/exp2-exp2f-exp2l.md)|Üstel 2 hesaplar<sup>x</sup>
[expm1, expm1f, expm1l](../c-runtime-library/reference/expm1-expm1f-expm1l.md)|Hesaplar *e*<sup>x</sup>-1
[fabs, fabsf, fabsl](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|Kayan nokta türü mutlak değeri hesaplar
[_fcvt](../c-runtime-library/reference/fcvt.md), [fcvt](../c-runtime-library/reference/posix-fcvt.md)|Kayan noktalı sayı bir dizeye dönüştürür
[_fcvt_s](../c-runtime-library/reference/fcvt-s.md)|Güvenli sürümü **_fcvt**
[fdim, fdimf, fdiml](../c-runtime-library/reference/fdim-fdimf-fdiml.md)|Pozitif değerler arasındaki farkın iki belirler
[feclearexcept](../c-runtime-library/reference/feclearexcept1.md)|Kayan nokta özel durumlar temizler belirtilen
[fegetenv](../c-runtime-library/reference/fegetenv1.md)|Geçerli kayan nokta ortamı depolar
[fegetexceptflag](../c-runtime-library/reference/fegetexceptflag2.md)|Belirtilen kayan nokta özel durumu alır
[fegetround](../c-runtime-library/reference/fegetround-fesetround2.md)|Kayan nokta yuvarlama modu alır
[feholdexcept](../c-runtime-library/reference/feholdexcept2.md)|Ayarlar stop kayan nokta özel durum modu
[feraiseexcept](../c-runtime-library/reference/feraiseexcept.md)|Belirtilen kayan nokta özel durumları oluşturur
[fesetenv](../c-runtime-library/reference/fesetenv1.md)|Geçerli kayan nokta ortamını ayarlar
[fesetexceptflag](../c-runtime-library/reference/fesetexceptflag2.md)|Belirtilen kayan nokta durumu bayrakları ayarlar
[fesetround](../c-runtime-library/reference/fegetround-fesetround2.md)|Belirtilen kayan nokta yuvarlama modu ayarlar
[fetestexcept](../c-runtime-library/reference/fetestexcept1.md)|Hangi kayan nokta özel durumu bayraklarını ayarlayın belirler
[feupdateenv](../c-runtime-library/reference/feupdateenv.md)|Kayan nokta bir ortam yükler sonra önceki özel durumları oluşturur
[_finite, _finitef](../c-runtime-library/reference/finite-finitef.md)|Bir değer sınırlı olup olmadığını belirler
[floor, floorf, floorl](../c-runtime-library/reference/floor-floorf-floorl.md)|Floor hesaplar
[fma, fmaf, fmal](../c-runtime-library/reference/fma-fmaf-fmal.md)|Fused multiply-add hesaplar
[fmax, fmaxf, fmaxl](../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)|Bağımsız değişkenler maksimum hesaplar
[fmin, fminf, fminl](../c-runtime-library/reference/fmin-fminf-fminl.md)|Bağımsız değişkenler gereken hesaplar
[fmod, fmodf, fmodl](../c-runtime-library/reference/fmod-fmodf.md)|Kayan nokta kalanı hesaplar
[_fpclass, _fpclassf](../c-runtime-library/reference/fpclass-fpclassf.md)|Kayan nokta değeri sınıflandırmasını döndürür
[fpclassify](../c-runtime-library/reference/fpclassify.md)|Kayan nokta değeri sınıflandırmasını döndürür
[_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md)|Kayan nokta özel durumlar için bir işleyici ayarlar
[_fpreset](../c-runtime-library/reference/fpreset.md)|Kayan nokta ortamı sıfırlar
[frexp, frexpf, frexpl](../c-runtime-library/reference/frexp.md)|Mantis ve üs bir kayan noktalı sayının alır
[_gcvt](../c-runtime-library/reference/gcvt.md), [gcvt](../c-runtime-library/reference/posix-gcvt.md)|Kayan noktalı sayı bir dizeye dönüştürür
[_gcvt_s](../c-runtime-library/reference/gcvt-s.md)|Güvenli sürümü **_gcvt**
[_get_FMA3_enable, _set_FMA3_enable](../c-runtime-library/reference/get-fma3-enable-set-fma3-enable.md)|Alır veya üzerinde x64 FMA3 yönergeleri kullanımı için bir bayrak ayarlar
[hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|Hipotenüsü hesaplar
[ilogb, ilogbf, ilogbl](../c-runtime-library/reference/ilogb-ilogbf-ilogbl2.md)|Tamsayı base-2 üs hesaplar
[imaxabs](../c-runtime-library/reference/imaxabs.md)|Bir tamsayı türünde mutlak değeri hesaplar
[imaxdiv](../c-runtime-library/reference/imaxdiv.md)|Sayının ve iki tamsayı değerleri geri kalanı hesaplar
[isnan, _isnan, _isnanf](../c-runtime-library/reference/isnan-isnan-isnanf.md)|Kayan nokta değeri NaN için test
[_j0, _j1, _jn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|Bessel işlevi hesaplar
[ldexp, ldexpf, ldexpl](../c-runtime-library/reference/ldexp.md)|Hesaplar x * 2<sup>n</sup>
[lgamma, lgammaf, lgammal](../c-runtime-library/reference/lgamma-lgammaf-lgammal.md)|Gama işlevi mutlak değerini doğal logaritmasını hesaplar
[llrint, llrintf, llrintl](../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)|Kayan noktalı bir sayıyı yuvarlar en yakın **uzun uzun** değeri
[llround, llroundf, llroundl](../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)|Kayan noktalı bir sayıyı yuvarlar en yakın **uzun uzun** değeri
[Günlük, logf, logl, log10, log10f, log10l](../c-runtime-library/reference/log-logf-log10-log10f.md)|Doğal ya da 10 tabanında logaritmasını hesaplar
[log1p, log1pf, log1pl](../c-runtime-library/reference/log1p-log1pf-log1pl2.md)|1 + x doğal logaritmasını hesaplar
[log2, log2f, log2l](../c-runtime-library/reference/log2-log2f-log2l.md)|2 tabanındaki logaritmasını hesaplar
[logb, logbf, logbl, _logb, _logbf](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|Kayan nokta değeri üs döndürür
[lrint, lrintf, lrintl](../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)|Kayan noktalı bir sayıyı yuvarlar en yakın **uzun** değeri
[_lrotl, _lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|Bir tamsayı değeri sola veya sağa döndürür
[lround, lroundf, lroundl](../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)|Kayan noktalı bir sayıyı yuvarlar en yakın **uzun** değeri
[_matherr](../c-runtime-library/reference/matherr.md)|Varsayılan matematik hata işleyicisi
[__max](../c-runtime-library/reference/max.md)|İki değerden daha büyük döndürür makrosu
[__min](../c-runtime-library/reference/min.md)|İki değerden daha küçük döndürür makrosu
[modf, modff, modfl](../c-runtime-library/reference/modf-modff-modfl.md)|Bir kayan nokta değeri kesirli ve tamsayı bölümleri ayırır
[nan, nanf, nanl](../c-runtime-library/reference/nan-nanf-nanl.md)|Sessiz NaN değerini döndürür
[nearbyint, nearbyintf, nearbyintl](../c-runtime-library/reference/nearbyint-nearbyintf-nearbyintl1.md)|Yuvarlanmış değeri döndürür
[nextafter, nextafterf, nextafterl, _nextafter, _nextafterf](../c-runtime-library/reference/nextafter-functions.md)|Sonraki gösterilebilir kayan nokta değeri döndürür
[nexttoward, nexttowardf, nexttowardl](../c-runtime-library/reference/nextafter-functions.md)|Sonraki gösterilebilir kayan nokta değeri döndürür
[pow, powf, powl](../c-runtime-library/reference/pow-powf-powl.md)|Değerini döndürür *x*<sup>*y*</sup>
[remainder, remainderf, remainderl](../c-runtime-library/reference/remainder-remainderf-remainderl.md)|Kayan nokta değerlerinin iki sayının kalanı hesaplar
[remquo, remquof, remquol](../c-runtime-library/reference/remquo-remquof-remquol.md)|İki tamsayı değerleri geri kalanı hesaplar
[rint, rintf, rintl](../c-runtime-library/reference/rint-rintf-rintl.md)|Kayan nokta değeri yuvarlar
[_rotl, _rotl64, _rotr, _rotr64](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|Tamsayı türleri bit döndürür
[round, roundf, roundl](../c-runtime-library/reference/round-roundf-roundl.md)|Kayan nokta değeri yuvarlar
[_scalb, _scalbf](../c-runtime-library/reference/scalb.md)|Ölçek bağımsız değişkeni 2'in tarafından
[scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl](../c-runtime-library/reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md)|Kayan noktalı sayı bir tam sayı gücünü tarafından çarpar **flt_radıx**
[_set_controlfp](../c-runtime-library/reference/set-controlfp.md)|Kayan nokta denetim sözcüğü ayarlar
[_set_SSE2_enable](../c-runtime-library/reference/set-sse2-enable.md)|Etkinleştirir veya devre dışı bırakır SSE2 yönergeleri
[Sin, sinf, sinl](../c-runtime-library/reference/sin-sinf-sinl.md)|Sinüsünü hesaplar
[SİNH, sinhf, sinhl](../c-runtime-library/reference/sinh-sinhf-sinhl.md)|Hiperbolik sinüsünü hesaplar
[sqrt, sqrtf, sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|Kare kökünü hesaplar
[_status87, _statusfp, _statusfp2](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|Kayan nokta durum sözcüğünü alır
[strtof, _strtof_l](../c-runtime-library/reference/strtof-strtof-l-wcstof-wcstof-l.md)|Bir dizeye dönüştürür bir **float**
[strtold, _strtold_l](../c-runtime-library/reference/strtold-strtold-l-wcstold-wcstold-l.md)|Bir dizeye dönüştürür bir **uzun** **çift**
[Bronz, tanf, tanl](../c-runtime-library/reference/tan-tanf-tanl.md)|Tanjantını hesaplar
[TANH, tanhf, tanhl](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|Hiperbolik tanjantını hesaplar
[tgamma, tgammaf, tgammal](../c-runtime-library/reference/tgamma-tgammaf-tgammal.md)|Gama işlevi hesaplar
[trunc, truncf, truncl](../c-runtime-library/reference/trunc-truncf-truncl.md)|Kesirli bölümü tamsayıya dönüştürür
[_wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Geniş bir dizeye dönüştürür bir **çift**
[_y0, _y1, _yn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|Bessel işlevi hesaplar

## <a name="see-also"></a>Ayrıca bkz.

[Kategorilere göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
