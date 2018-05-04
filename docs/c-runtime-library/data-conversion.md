---
title: Veri dönüştürme | Microsoft Docs
ms.custom: ''
ms.date: 03/21/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- c.conversions
dev_langs:
- C++
helpviewer_keywords:
- data conversion routines [C++]
- converting data
ms.assetid: b15b5268-7467-49f1-bf95-5299b598f94c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a0260ebe37e0656f2078b247017d9f02ccc88474
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="data-conversion"></a>Veri Dönüştürme

Bu yordamlar verileri bir biçimden diğerine dönüştürün. Genellikle bu yordamlar, yazabilir dönüşümleri daha hızlı yürütün. İle başlayan her yordam bir *için* öneki makro ve bir işlevi olarak uygulanır. Bkz: [seçme arasında işlevler ve makrolar](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md) uygulaması seçme hakkında bilgi için.

## <a name="data-conversion-routines"></a>Veri dönüştürme yordamları

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[Abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Tamsayı mutlak değerini bulur|
|[atof, _atof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Dizeye dönüştürme **float**|
|[atoi, _atoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Dizeye dönüştürme **int**|
|[_atoi64, _atoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Dizeye dönüştürme **__int64** veya **uzun uzun**|
|[atol, _atol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Dizeye dönüştürme **uzun**|
|[c16rtomb, c32rtomb](../c-runtime-library/reference/c16rtomb-c32rtomb1.md)|UTF-16 veya UTF-32 karakter eşdeğer birden çok baytlı karakter dönüştürme|
|[_ecvt](../c-runtime-library/reference/ecvt.md), [_ecvt_s](../c-runtime-library/reference/ecvt-s.md)|Dönüştürme **çift** belirtilen uzunluk dizisi için|
|[_fcvt](../c-runtime-library/reference/fcvt.md), [_fcvt_s](../c-runtime-library/reference/fcvt-s.md)|Dönüştürme **çift** belirtilen sayıda basamağa ondalık noktası aşağıdaki dize|
|[_gcvt](../c-runtime-library/reference/gcvt.md), [_gcvt_s](../c-runtime-library/reference/gcvt-s.md)|Dönüştürme **çift** sayı dizeye; arabellekte dizeyi depolama|
|[_itoa, _ltoa, _ultoa, _i64toa, _ui64toa, _itow, _ltow, ultow, _i64tow, _ui64tow](../c-runtime-library/reference/itoa-itow.md), [_itoa_s, _ltoa_s, _ultoa_s, _i64toa_s, _ui64toa_s, _itow_s, _ltow_s, _ultow_s, _i64tow_s, _ui64tow_s](../c-runtime-library/reference/itoa-s-itow-s.md)|Tamsayı türleri dizeye dönüştürme|
|[Labs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Mutlak değerini bulmak **uzun** tamsayı|
|[llabs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Mutlak değerini bulmak **uzun uzun** tamsayı|
|[_mbbtombc, _mbbtombc_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)|1-bayt birden çok baytlı karakter karşılık gelen 2-bayt birden çok baytlı karakter dönüştürme|
|[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|Japonya endüstri standardı (JIS) karakter Japonya Microsoft (JMS) karakter dönüştürme|
|[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|JIS karakter JMS karakter dönüştürme|
|[_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|1-bayt hiragana kodu birden çok baytlı karakter dönüştürme|
|[_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|1-bayt katakana kodu birden çok baytlı karakter dönüştürme|
|[_mbctombb, _mbctombb_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)|2-bayt birden çok baytlı karakter karşılık gelen 1-bayt birden çok baytlı karakter dönüştürme|
|[mbrtoc16, mbrtoc32](../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)|Birden çok baytlı karakter eşdeğer UTF-16 veya UTF-32 karakter dönüştürme|
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Geniş karakterler karşılık gelen bir dizi için birden çok baytlı karakter dizisi Dönüştür|
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Birden çok baytlı karakter karşılık gelen geniş karakter dönüştürme|
|[strtod, _strtod_l, wcstod, _wcstod_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|Dizeye dönüştürme **çift**|
|[strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|Dizeye dönüştürme **uzun** tamsayı|
|[strtoul, _strtoul_l, wcstoul, _wcstoul_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|Dizeye dönüştürme **uzun imzasız** tamsayı|
|[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|Yerel ayarlara özgü bilgilere göre Harmanlanmış forma dize dönüştürme|
|[toascii, __toascii](../c-runtime-library/reference/toascii-toascii.md)|ASCII kodu karakter dönüştürme||
|[tolower, _tolower, towlower, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md), [_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Karakter test etme ve şu anda büyük harf, küçük harfe Dönüştür|
|[tolower, _tolower, towlower, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)|Koşulsuz olarak küçük harf karakter dönüştürme|[System::String::ToLower](https://msdn.microsoft.com/en-us/library/system.string.tolower.aspx)|
|[toupper, _toupper, towupper, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md), [_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Karakter test etme ve şu anda küçük harfler, büyük harfe Dönüştür|
|[toupper, _toupper, towupper, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|Koşulsuz olarak büyük harf karakter dönüştürme|
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Birden çok baytlı karakterler karşılık gelen bir dizi için geniş bir karakter dizisi Dönüştür|
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Geniş karakter karşılık gelen birden çok baytlı karakter dönüştürme|
|[_wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Joker karakter dizeye dönüştürme bir **çift**|
|[_wtoi, _wtoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Joker karakter dizeye dönüştürme **int**|
|[_wtoi64, _wtoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Joker karakter dizeye dönüştürme **__int64** veya **uzun uzun**|
|[_wtol, _wtol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Joker karakter dizeye dönüştürme **uzun**|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
