---
title: Matematik ve kayan nokta desteği
ms.date: 04/06/2018
f1_keywords:
- c.math
helpviewer_keywords:
- floating-point numbers, math routines
- math routines
- floating-point numbers
ms.assetid: e4fcaf69-5c8e-4854-a9bb-1f412042131e
ms.openlocfilehash: 9e1baeb7236e5b1144b52df0bd83cc0f4a4b7796
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558242"
---
# <a name="math-and-floating-point-support"></a>Matematik ve kayan nokta desteği

Evrensel C çalışma zamanı kitaplığı (UCRT), tüm ISO C99 tarafından gerekli olanlar da dahil olmak üzere çoğu integral ve kayan nokta matematik kitaplığı işlevi sağlar. Kayan nokta işlevleri, doğruluk açısından performans dengelemek için uygulanır. Doğru yuvarlatılmış sonuç oluşturmayı fazla vakit pahalı olabileceği için bu işlevleri verimli bir şekilde doğru yuvarlatılmış sonuca Kapat bir yaklaştırma üretmek için tasarlanmıştır. Olabilir durumlarda çoğu durumda, sonucu içinde +/-1 ulp doğru yuvarlatılmış sonucun, ancak daha büyük bir yanlışlığı olduğu.

Birçok kayan nokta matematik kitaplığı işlevi farklı CPU mimarileri için farklı uygulamaları vardır. Örneğin, 32-bit x86 CRT 64-bit x64 değerinden farklı bir uygulama olabilir CRT. Ayrıca, bazı işlevler belirli bir CPU mimarisi için birden çok uygulamaları olabilir. En verimli uygulama CPU tarafından desteklenen komut kümelerini bağlı olarak çalışma zamanında dinamik olarak seçilir. Örneğin, 32-bit x86, CRT, bazı işlevler, hem x x87 sahip uygulama ve SSE2 uygulaması. SSE2 destekleyen bir CPU üzerinde çalışırken, daha hızlı SSE2 uygulaması kullanılır. SSE2, uygulama kullanılan daha yavaş x87 desteklemeyen bir CPU üzerinde çalışırken. Matematik kitaplığı işlevi, farklı uygulamalar farklı CPU yönergeleri ve farklı algoritmalar sonuçları üretmek için kullanılıyor olabileceğinden, İşlevler, CPU'lar arasında farklı sonuçlar üretebilir. Çoğu durumda, sonuçlar içinde +/-1 ulp yuvarlatılmış doğru sonucu olan, ancak gerçek sonuçların CPU'lar arasında değişebilir.

Microsoft C/C++ ve desteklenen Microsoft Visual C++ önceki 16-bit sürümleri **uzun çift** 80 bit duyarlık kayan nokta veri türü olarak yazın. Visual C++'ın sonraki sürümlerinde **uzun çift** veri türü olan bir 64-bit duyarlığa kayan nokta veri türü için aynı **çift** türü. Derleyici işler **uzun çift** ve **çift** olarak farklı türler, ancak **uzun çift** işlevleri aynı kendi **çift** ortaklarınıza. CRT sağlar **uzun çift** matematik işlevleri için ISO C99 sürümleri, kaynak kodu uyumluluğuyla, ancak diğer derleyiciler ikili gösterim değişebileceğini unutmayın.

## <a name="supported-math-and-floating-point-routines"></a>Desteklenen matematik ve kayan nokta rutinleri

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-|-|
[abs, labs, llabs, _abs64](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Bir tamsayı türü mutlak değerini hesaplar.
[acos, acosf, acosl](../c-runtime-library/reference/acos-acosf-acosl.md)|Ark kosinüsünü hesaplar.
[acosh, acoshf, acoshl](../c-runtime-library/reference/acosh-acoshf-acoshl.md)|Yay hiperbolik kosinüsünü hesaplar.
[asin, asinf, asinl](../c-runtime-library/reference/asin-asinf-asinl.md)|Ark sinüsünü hesaplar.
[asinh, asinhf, asinhl](../c-runtime-library/reference/asinh-asinhf-asinhl.md)|Yay hiperbolik sinüsünü hesaplar.
[atan, atanf, atanl, atan2, atan2f, atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Ark tanjantını hesaplar.
[atanh, atanhf, atanhl](../c-runtime-library/reference/atanh-atanhf-atanhl.md)|Ark hiperbolik tanjantı hesaplar.
[_atodbl, _atodbl_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Yerel ayara özgü bir dizeye dönüştürür bir **çift**
[atof, _atof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Bir dizeye dönüştürür bir **çift**
[_atoflt, _atoflt_l, _atoldbl, _atoldbl_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Yerel ayara özgü bir dizeye dönüştürür bir **float** veya **uzun çift**
[cbrt, cbrtf, cbrtl](../c-runtime-library/reference/cbrt-cbrtf-cbrtl.md)|Küp kökünü hesaplar.
[ceil, ceilf, ceill](../c-runtime-library/reference/ceil-ceilf-ceill.md)|Tavanını hesaplar.
[_chgsign, _chgsignf, _chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|Eklenebilir tersini hesaplar
[_clear87, _clearfp](../c-runtime-library/reference/clear87-clearfp.md)|Alır ve kayan nokta durum kaydı siler
[_control87, \__control87_2, _controlfp](../c-runtime-library/reference/control87-controlfp-control87-2.md)|Kayan nokta denetim sözcüğünü alır ve ayarlar
[_controlfp_s](../c-runtime-library/reference/controlfp-s.md)|Güvenli sürümünü **_controlfp**
[copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|Bir bağımsız değişkenin büyüklüğüne ve başka bir oturum sahip bir değer döndürür
[cos, cosf, cosl](../c-runtime-library/reference/cos-cosf-cosl.md)|Sinüsünü hesaplar.
[cosh, coshf, coshl](../c-runtime-library/reference/cosh-coshf-coshl.md)|Hiperbolik sinüsünü hesaplar.
[div ldiv, lldiv](../c-runtime-library/reference/div.md)|Bölümü ve iki tamsayı değerinin kalanını hesaplar
[_ecvt](../c-runtime-library/reference/ecvt.md), [ecvt](../c-runtime-library/reference/posix-ecvt.md)|Dönüştürür bir **çift** bir dizeye
[_ecvt_s](../c-runtime-library/reference/ecvt-s.md)|Güvenli sürümünü **_ecvt**
[erf, erff, erfl](../c-runtime-library/reference/erf-erff-erfl-erfc-erfcf-erfcl.md)|Hata işlevini hesaplar.
[erfc, erfcf, erfcl](../c-runtime-library/reference/erf-erff-erfl-erfc-erfcf-erfcl.md)|Tümleyici hata işlevini hesaplar.
[exp, expf, expl](../c-runtime-library/reference/exp-expf.md)|Üssünü hesaplar *e*<sup>x</sup>
[exp2, exp2f, exp2l](../c-runtime-library/reference/exp2-exp2f-exp2l.md)|Üstel 2 hesaplar<sup>x</sup>
[expm1, expm1f, expm1l](../c-runtime-library/reference/expm1-expm1f-expm1l.md)|Hesaplar *e*<sup>x</sup>-1
[fabs, fabsf, fabsl](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|Kayan nokta türü mutlak değerini hesaplar.
[_fcvt](../c-runtime-library/reference/fcvt.md), [fcvt](../c-runtime-library/reference/posix-fcvt.md)|Bir kayan noktalı sayı bir dizeye dönüştürür.
[_fcvt_s](../c-runtime-library/reference/fcvt-s.md)|Güvenli sürümünü **_fcvt**
[fdim, fdimf, fdiml](../c-runtime-library/reference/fdim-fdimf-fdiml.md)|İki değer arasındaki pozitif farkı belirler
[feclearexcept](../c-runtime-library/reference/feclearexcept1.md)|Kayan nokta özel durumlarını temizler belirtilen
[fegetenv](../c-runtime-library/reference/fegetenv1.md)|Geçerli bir kayan nokta ortamı depolar
[fegetexceptflag](../c-runtime-library/reference/fegetexceptflag2.md)|Belirtilen bir kayan nokta özel durumlarını alır
[fegetround](../c-runtime-library/reference/fegetround-fesetround2.md)|Kayan nokta yuvarlama modu alır
[feholdexcept](../c-runtime-library/reference/feholdexcept2.md)|Stop kayan nokta özel durum modu ayarlar
[feraiseexcept](../c-runtime-library/reference/feraiseexcept.md)|Belirtilen kayan nokta özel durumlarını oluşturur
[fesetenv](../c-runtime-library/reference/fesetenv1.md)|Geçerli bir kayan nokta ortamını ayarlar
[fesetexceptflag](../c-runtime-library/reference/fesetexceptflag2.md)|Belirtilen bir kayan nokta durumu bayraklarını ayarlar
[fesetround](../c-runtime-library/reference/fegetround-fesetround2.md)|Belirtilen kayan nokta yuvarlama modu ayarlar
[fetestexcept](../c-runtime-library/reference/fetestexcept1.md)|Hangi kayan nokta özel durum durumu bayrakları ayarlanmış belirler
[feupdateenv](../c-runtime-library/reference/feupdateenv.md)|Bir kayan nokta ortamı geri yükler, sonra önceki özel durum başlatır
[_finite, _finitef](../c-runtime-library/reference/finite-finitef.md)|Bir değer sınırlı olup olmadığını belirler
[floor, floorf, floorl](../c-runtime-library/reference/floor-floorf-floorl.md)|Tabanını hesaplar.
[fma, fmaf, fmal](../c-runtime-library/reference/fma-fmaf-fmal.md)|Fused Çarp hesaplar
[fmax, fmaxf, fmaxl](../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)|Bağımsız değişkenlerin sayısı üst sınırını hesaplar.
[fmin, fminf, fminl](../c-runtime-library/reference/fmin-fminf-fminl.md)|Minimum bağımsız hesaplar
[fmodf, fmodl fmod](../c-runtime-library/reference/fmod-fmodf.md)|Kayan nokta kalanını hesaplar.
[_fpclass, _fpclassf](../c-runtime-library/reference/fpclass-fpclassf.md)|Sınıflandırma kayan nokta değeri döndürür
[fpclassify](../c-runtime-library/reference/fpclassify.md)|Sınıflandırma kayan nokta değeri döndürür
[_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md)|Kayan nokta özel durumları için bir işleyici ayarlar
[_fpreset](../c-runtime-library/reference/fpreset.md)|Kayan nokta ortamı sıfırlar
[frexp, frexpf, frexpl](../c-runtime-library/reference/frexp.md)|Mantis ve kayan noktalı bir sayı alır.
[_gcvt](../c-runtime-library/reference/gcvt.md), [gcvt](../c-runtime-library/reference/posix-gcvt.md)|Bir kayan noktalı sayı bir dizeye dönüştürür.
[_gcvt_s](../c-runtime-library/reference/gcvt-s.md)|Güvenli sürümünü **_gcvt**
[_get_FMA3_enable, _set_FMA3_enable](../c-runtime-library/reference/get-fma3-enable-set-fma3-enable.md)|Alır veya üzerinde x64 FMA3 yönergelerinin kullanımını etkinleştir için bir bayrak ayarlar
[hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|Hipotenüsü hesaplar.
[ilogb, ilogbf, ilogbl](../c-runtime-library/reference/ilogb-ilogbf-ilogbl2.md)|Tamsayı 2 tabanında üssünü hesaplar.
[imaxabs](../c-runtime-library/reference/imaxabs.md)|Bir tamsayı türü mutlak değerini hesaplar.
[imaxdiv](../c-runtime-library/reference/imaxdiv.md)|Bölümü ve iki tamsayı değerinin kalanını hesaplar
[isnan, _isnan, _isnanf](../c-runtime-library/reference/isnan-isnan-isnanf.md)|Bir kayan nokta değeri NaN için test eder
[_j0, _j1, _jn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|Bessel işlevi hesaplar
[ldexp, ldexpf, ldexpl](../c-runtime-library/reference/ldexp.md)|Hesaplar x * 2<sup>n</sup>
[lgamma, lgammaf, lgammal](../c-runtime-library/reference/lgamma-lgammaf-lgammal.md)|Gama fonksiyonu mutlak değerini doğal logaritmasını hesaplar.
[llrint, llrintf, llrintl](../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)|Kayan nokta değerine yuvarlanır en yakın **uzun uzun** değeri
[llround, llroundf, llroundl](../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)|Kayan nokta değerine yuvarlanır en yakın **uzun uzun** değeri
[Günlük, logf, logl, log10, log10f, log10l](../c-runtime-library/reference/log-logf-log10-log10f.md)|Doğal ya da 10 tabanında logaritmasını hesaplar.
[log1p, log1pf, log1pl](../c-runtime-library/reference/log1p-log1pf-log1pl2.md)|1 + x doğal logaritmasını hesaplar.
[log2, log2f, log2l](../c-runtime-library/reference/log2-log2f-log2l.md)|2 tabanlı logaritmasını hesaplar.
[logb, logbf, logbl, _logb, _logbf](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|Üssü bir kayan nokta değeri döndürür
[lrint, lrintf, lrintl](../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)|Kayan nokta değerine yuvarlanır en yakın **uzun** değeri
[_lrotl, _lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|Sola veya sağa bir Integer değeri döndürür
[lround, lroundf, lroundl](../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)|Kayan nokta değerine yuvarlanır en yakın **uzun** değeri
[_matherr](../c-runtime-library/reference/matherr.md)|Varsayılan matematik hata işleyicisi
[__max](../c-runtime-library/reference/max.md)|İki değeri büyük döndüren makrosu
[__min](../c-runtime-library/reference/min.md)|İki değerin daha küçük döndüren makrosu
[modf, modff, modfl](../c-runtime-library/reference/modf-modff-modfl.md)|Bir kayan nokta değeri kesirli ve tamsayı bölümlere böler
[nan, nanf, nanl](../c-runtime-library/reference/nan-nanf-nanl.md)|Sessiz bir NaN değerini döndürür
[nearbyint, nearbyintf, nearbyintl](../c-runtime-library/reference/nearbyint-nearbyintf-nearbyintl1.md)|Yuvarlatılmış değerini döndürür
[nextafter nextafterf, nextafterl _nextafter, _nextafterf](../c-runtime-library/reference/nextafter-functions.md)|Gösterilebilir sıradaki kayan nokta değeri döndürür
[nexttoward, nexttowardf, nexttowardl](../c-runtime-library/reference/nextafter-functions.md)|Gösterilebilir sıradaki kayan nokta değeri döndürür
[pow, powf, powl](../c-runtime-library/reference/pow-powf-powl.md)|Değerini döndürür *x*<sup>*y*</sup>
[remainder, remainderf, remainderl](../c-runtime-library/reference/remainder-remainderf-remainderl.md)|Kayan nokta değerlerinin iki sayının geri kalanı hesaplar.
[remquo, remquof, remquol](../c-runtime-library/reference/remquo-remquof-remquol.md)|İki tamsayı değerinin kalanını hesaplar.
[rint, rintf, rintl](../c-runtime-library/reference/rint-rintf-rintl.md)|Bir kayan noktalı değere yuvarlar
[_rotl, _rotl64, _rotr, _rotr64](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|Tamsayı türlerinde BITS döndürür
[round, roundf, roundl](../c-runtime-library/reference/round-roundf-roundl.md)|Bir kayan noktalı değere yuvarlar
[_scalb, _scalbf](../c-runtime-library/reference/scalb.md)|2'in kuvveti olarak ölçek bağımsız değişkeni
[scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl](../c-runtime-library/reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md)|Bir kayan noktalı sayı bir tam sayı gücünü tarafından çarpar **flt_radıx**
[_set_controlfp](../c-runtime-library/reference/set-controlfp.md)|Kayan nokta denetim sözcüğünü ayarlar
[_set_SSE2_enable](../c-runtime-library/reference/set-sse2-enable.md)|Etkinleştirir veya SSE2 yönergelerini devre dışı bırakır
[sin, sinf, sinl](../c-runtime-library/reference/sin-sinf-sinl.md)|Sinüsünü hesaplar.
[sinh, sinhf, sinhl](../c-runtime-library/reference/sinh-sinhf-sinhl.md)|Hiperbolik sinüsünü hesaplar.
[sqrt, sqrtf, sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|Kare kökünü hesaplar.
[_status87, _statusfp, _statusfp2](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|Kayan nokta durumu sözcüğünü alır
[strtof, _strtof_l](../c-runtime-library/reference/strtof-strtof-l-wcstof-wcstof-l.md)|Bir dizeye dönüştürür bir **float**
[strtold, _strtold_l](../c-runtime-library/reference/strtold-strtold-l-wcstold-wcstold-l.md)|Bir dizeye dönüştürür bir **uzun** **çift**
[tan, tanf, tanl](../c-runtime-library/reference/tan-tanf-tanl.md)|Tanjantını hesaplar.
[tanh, tanhf, tanhl](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|Hiperbolik tanjantı hesaplar.
[tgamma, tgammaf, tgammal](../c-runtime-library/reference/tgamma-tgammaf-tgammal.md)|Gama fonksiyonu hesaplar
[trunc, truncf, truncl](../c-runtime-library/reference/trunc-truncf-truncl.md)|Kesirli bölümü keser
[_wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Geniş bir dizeye dönüştürür bir **çift**
[_y0, _y1, _yn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|Bessel işlevi hesaplar

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
