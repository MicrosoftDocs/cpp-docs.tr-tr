---
title: Verileri dönüştürme | Microsoft Docs
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
ms.openlocfilehash: 2475a7d4f6399f408dfd1d5903a1920baf97c6bd
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201744"
---
# <a name="data-conversion"></a>Veri Dönüştürme

Bu yordamların verileri bir biçimden diğerine dönüştürün. Genellikle bu yordamlar, yazdığınız dönüştürmeleri daha hızlı yürütün. İle başlayan her bir rutin bir *için* önek bir işlev ve makro olarak uygulanır. Bkz: [seçme arasında işlevlerle makrolar](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md) uygulaması seçme hakkında bilgi için.

## <a name="data-conversion-routines"></a>Veri dönüştürme rutinleri

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[Abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Tamsayının mutlak değerini bulur|
|[atof, _atof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Dizeye Dönüştür **float**|
|[atoi, _atoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Dizeye Dönüştür **int**|
|[_atoi64, _atoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Dizeye Dönüştür **__int64** veya **uzun uzun**|
|[atol, _atol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Dizeye Dönüştür **uzun**|
|[c16rtomb, c32rtomb](../c-runtime-library/reference/c16rtomb-c32rtomb1.md)|UTF-16 veya UTF-32 karakter eşdeğer çok baytlı karakter dönüştürme|
|[_ecvt](../c-runtime-library/reference/ecvt.md), [_ecvt_s](../c-runtime-library/reference/ecvt-s.md)|Dönüştürme **çift** belirtilen uzunlukta bir dize|
|[_fcvt](../c-runtime-library/reference/fcvt.md), [_fcvt_s](../c-runtime-library/reference/fcvt-s.md)|Dönüştürme **çift** belirtilen sayıda ondalık ayırıcıdan sonraki basamak dize|
|[_gcvt](../c-runtime-library/reference/gcvt.md), [_gcvt_s](../c-runtime-library/reference/gcvt-s.md)|Dönüştürme **çift** numarası için dize; dize arabelleğinde depolar|
|[_itoa, _ltoa, _ultoa, _i64toa, _ui64toa, _itow, _ltow, ultow, _i64tow, _ui64tow](../c-runtime-library/reference/itoa-itow.md), [_itoa_s, _ltoa_s, _ultoa_s, _i64toa_s, _ui64toa_s, _itow_s, _ltow_s, _ultow_s, _i64tow_s, _ui64tow_s](../c-runtime-library/reference/itoa-s-itow-s.md)|Tamsayı türleri dizeye Dönüştür|
|[Laboratuvarları](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Mutlak değerini bulmak **uzun** tamsayı|
|[llabs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Mutlak değerini bulmak **uzun uzun** tamsayı|
|[_mbbtombc, _mbbtombc_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)|1 baytlık çok baytlı karakteri karşılık gelen 2 baytlık çok baytlı karakter dönüştürme|
|[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|Japonya Microsoft (JMS) karakter Japon endüstri standardı (JIS) karakter dönüştürme|
|[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|JIS karakterine JMS karakter dönüştürme|
|[_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|Çok baytlı karakterin 1 baytlık hiragana koduna dönüştürün|
|[_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|1 baytlık katakana kodu çok baytlı karakter dönüştürme|
|[_mbctombb, _mbctombb_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)|2 baytlık çok baytlı karakteri karşılık gelen 1 baytlık çok baytlı karakter dönüştürme|
|[mbrtoc16, mbrtoc32](../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)|Çok baytlı karakter eşdeğer UTF-16 veya UTF-32 karakter dönüştürme|
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Dizi çok baytlı karakteri karşılık gelen geniş karakterler dizisi için Dönüştür|
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Karşılık gelen geniş karakter için çok baytlı karakter dönüştürme|
|[strtod, _strtod_l, wcstod, _wcstod_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|Dizeye Dönüştür **çift**|
|[strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|Dizeye Dönüştür **uzun** tamsayı|
|[strtoul, _strtoul_l, wcstoul, _wcstoul_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|Dizeye Dönüştür **işaretsiz uzun** tamsayı|
|[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|Yerel ayara özgü bilgilere göre Harmanlanmış form dize dönüştürün|
|[toascii, __toascii](../c-runtime-library/reference/toascii-toascii.md)|ASCII koduna karakter dönüştürme||
|[tolower, _tolower, towlower, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md), [_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Karakter test etme ve şu anda büyük harf ise küçük harfe Dönüştür|
|[tolower, _tolower, towlower, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)|Karakter koşulsuz olarak küçük harfe Dönüştür|[System::String::ToLower](https://msdn.microsoft.com/library/system.string.tolower.aspx)|
|[toupper, _toupper, towupper, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md), [_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Karakter test etme ve şu anda küçük ise büyük harfe Dönüştür|
|[toupper, _toupper, towupper, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|Karakter koşulsuz büyük harfe Dönüştür|
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Geniş karakter dizisi karşılık gelen çok baytlı karakter dizisine dönüştürme|
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Çok baytlı karaktere karşılık gelen geniş karakter dönüştürme|
|[_wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Geniş karakter dizesi dönüştürme bir **çift**|
|[_wtoi, _wtoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Geniş karakter dizesi dönüştürme **int**|
|[_wtoi64, _wtoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Geniş karakter dizesi dönüştürme **__int64** veya **uzun uzun**|
|[_wtol, _wtol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Geniş karakter dizesi dönüştürme **uzun**|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
