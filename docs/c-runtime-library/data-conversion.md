---
title: Veri Dönüştürme
ms.date: 03/21/2018
f1_keywords:
- c.conversions
helpviewer_keywords:
- data conversion routines [C++]
- converting data
ms.assetid: b15b5268-7467-49f1-bf95-5299b598f94c
ms.openlocfilehash: 94e6a8182e12ecd74f9d2cd5dddaa84a1e3eb847
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218773"
---
# <a name="data-conversion"></a>Veri Dönüştürme

Bu yordamlar verileri bir formdan diğerine dönüştürür. Genellikle bu yordamlar, yazabilme dönüştürmelerinden daha hızlı yürütülür. Bir *to* önekiyle başlayan her yordam, bir işlev olarak ve bir makro olarak uygulanır. Uygulama seçme hakkında bilgi için bkz. [işlevler ve makrolar arasında seçim yapma](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md) .

## <a name="data-conversion-routines"></a>Veri dönüştürme yordamları

|Yordam|Kullanın|
|-------------|---------|
|[mutlak](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Tam tamsayının mutlak değerini bul|
|[atof, _atof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Dizeyi Dönüştür**`float`**|
|[atoı, _atoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Dizeyi Dönüştür**`int`**|
|[_atoi64, _atoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Dizeyi veya öğesine Dönüştür **`__int64`****`long long`**|
|[Atol, _atol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Dizeyi Dönüştür**`long`**|
|[c16rtomb, c32rtomb](../c-runtime-library/reference/c16rtomb-c32rtomb1.md)|UTF-16 veya UTF-32 karakterini eşdeğer çok baytlı karaktere Dönüştür|
|[_ecvt](../c-runtime-library/reference/ecvt.md), [_ecvt_s](../c-runtime-library/reference/ecvt-s.md)|**`double`** Belirtilen uzunluğun dizesine Dönüştür|
|[_fcvt](../c-runtime-library/reference/fcvt.md), [_fcvt_s](../c-runtime-library/reference/fcvt-s.md)|**`double`** Ondalık ayırıcıdan sonra belirtilen basamak sayısına sahip dizeye Dönüştür|
|[_gcvt](../c-runtime-library/reference/gcvt.md), [_gcvt_s](../c-runtime-library/reference/gcvt-s.md)|**`double`** Sayıyı dizeye Dönüştür; arabellekte depo dizesi|
|[_itoa, _ltoa, _ultoa, _i64toa, _ui64toa, _itow, _ltow, ultow, _i64tow, _ui64tow](../c-runtime-library/reference/itoa-itow.md), [_itoa_s, _ltoa_s, _ultoa_s, _i64toa_s, _ui64toa_s, _itow_s, _ltow_s, _ultow_s,](../c-runtime-library/reference/itoa-s-itow-s.md) _i64tow_s, _ui64tow_s|Tamsayı türlerini dizeye Dönüştür|
|[larda](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|**`long`** Tam tamsayının mutlak değerini bul|
|[LLabs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|**`long long`** Tam tamsayının mutlak değerini bul|
|[_mbbtombc, _mbbtombc_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)|1 baytlık çok baytlı karakteri karşılık gelen 2 baytlık çok baytlı karaktere Dönüştür|
|[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|Japonya endüstri standardı (JıS) karakterini Japonya Microsoft (JMS) karakterine Dönüştür|
|[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|JMS karakterini JıS karaktere Dönüştür|
|[_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|Çok baytlı karakteri 1 baytlık Hiragana koduna Dönüştür|
|[_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|Çok baytlı karakteri 1 baytlık Katakana koduna Dönüştür|
|[_mbctombb, _mbctombb_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)|2 baytlık çok baytlı karakteri karşılık gelen 1 baytlık çok baytlı karaktere Dönüştür|
|[mbrtoc16, mbrtoc32](../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)|Çok baytlı karakteri eşit UTF-16 veya UTF-32 karakterine Dönüştür|
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Çok baytlı karakterlerin dizisini karşılık gelen geniş karakter dizisine Dönüştür|
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Çok baytlı karakteri karşılık gelen geniş karaktere Dönüştür|
|[strtod, _strtod_l, wcstod, _wcstod_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|Dizeyi Dönüştür**`double`**|
|[strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|Dizeyi tamsayıya Dönüştür **`long`**|
|[strtoul, _strtoul_l, wcstoul, _wcstoul_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|Dizeyi tamsayıya Dönüştür **`unsigned long`**|
|[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|Dizeyi yerel ayara özgü bilgilere göre harmanlanmış biçimde Dönüştür|
|[toascii, __toascii](../c-runtime-library/reference/toascii-toascii.md)|Karakteri ASCII koduna Dönüştür|
|[ToLower, _tolower, kasada alt, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md), [_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Şu anda büyük harfle, test karakteri ve küçük harfe Dönüştür|
|[tolower, _tolower, towlower, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)|Karakteri küçük harfe, koşulsuz olarak Dönüştür|
|[ToUpper, _toupper, kasaüst, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md), [_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Şu anda küçük harfli olduğunda, test karakteri ve büyük harfe Dönüştür|
|[toupper, _toupper, towupper, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|Karakteri büyük harfe koşulsuz olarak Dönüştür|
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Geniş karakter sırasını, çok baytlı karakterlerin karşılık gelen dizisine Dönüştür|
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Geniş karakteri karşılık gelen çok baytlı karaktere Dönüştür|
|[_wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Geniş karakter dizesini öğesine Dönüştür**`double`**|
|[_wtoi, _wtoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Geniş karakterli dizeyi Dönüştür**`int`**|
|[_wtoi64, _wtoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Geniş karakter dizesini veya öğesine Dönüştür **`__int64`****`long long`**|
|[_wtol, _wtol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Geniş karakterli dizeyi Dönüştür**`long`**|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
