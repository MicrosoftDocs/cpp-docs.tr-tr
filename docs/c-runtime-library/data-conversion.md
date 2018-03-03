---
title: "Veri dönüştürme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.conversions
dev_langs:
- C++
helpviewer_keywords:
- data conversion routines [C++]
- converting data
ms.assetid: b15b5268-7467-49f1-bf95-5299b598f94c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 11b28793e5e659e3135061e3a6fd410d9b1c9f3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="data-conversion"></a>Veri Dönüştürme
Bu yordamlar verileri bir biçimden diğerine dönüştürün. Genellikle bu yordamlar, yazabilir dönüşümleri daha hızlı yürütün. İle başlayan her yordam bir `to` öneki makro ve bir işlevi olarak uygulanır. Bkz: [seçme arasında işlevler ve makrolar](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md) uygulaması seçme hakkında bilgi için.  
  
### <a name="data-conversion-routines"></a>Veri dönüştürme yordamları  
  
|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|-------------|---------|  
|[Abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Tamsayı mutlak değerini bulur|  
|[atof, _atof_l, _wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Dizeye dönüştürme`float`|  
|[atoi, _atoi_l, _wtoi, _wtoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Dizeye dönüştürme`int`|  
|[_atoi64, _atoi64_l, _wtoi64, _wtoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Dizeye dönüştürme`__int64`|  
|[atol, _atol_l, _wtol, _wtol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Dizeye dönüştürme`long`|  
|[c16rtomb, c32rtomb](../c-runtime-library/reference/c16rtomb-c32rtomb1.md)|UTF-16 veya UTF-32 karakter eşdeğer birden çok baytlı karakter dönüştürme|  
|[_ecvt](../c-runtime-library/reference/ecvt.md), [_ecvt_s](../c-runtime-library/reference/ecvt-s.md)|Dönüştürme `double` belirtilen uzunluk dizisi için|  
|[_fcvt](../c-runtime-library/reference/fcvt.md), [_fcvt_s](../c-runtime-library/reference/fcvt-s.md)|Dönüştürme `double` belirtilen sayıda basamağa ondalık noktası aşağıdaki dize|  
|[_gcvt](../c-runtime-library/reference/gcvt.md), [_gcvt_s](../c-runtime-library/reference/gcvt-s.md)|Dönüştürme `double` sayı dizeye; arabellekte dizeyi depolama|  
|[_itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow](../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md), [_itoa_s, _i64toa_s, _ui64toa_s, _itow_s, _i64tow_s, _ui64tow_s](../c-runtime-library/reference/itoa-s-i64toa-s-ui64toa-s-itow-s-i64tow-s-ui64tow-s.md)|Dönüştürme `int` veya `__int64` dizeye|  
|[Labs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Mutlak değerini bulmak `long` tamsayı|  
|[llabs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Mutlak değerini bulmak `long long` tamsayı|  
|[_ltoa, _ltow](../c-runtime-library/reference/ltoa-ltow.md), [_ltoa_s, _ltow_s](../c-runtime-library/reference/ltoa-s-ltow-s.md)|Dönüştürme `long` dizeye|  
|[_mbbtombc, _mbbtombc_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)|1-bayt birden çok baytlı karakter karşılık gelen 2-bayt birden çok baytlı karakter dönüştürme|  
|[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|Japonya endüstri standardı (JIS) karakter Japonya Microsoft (JMS) karakter dönüştürme|  
|[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|JIS karakter JMS karakter dönüştürme|  
|[_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|1-bayt hiragana kodu birden çok baytlı karakter dönüştürme|  
|[_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|1-bayt katakana kodu birden çok baytlı karakter dönüştürme|  
|[_mbctombb, _mbctombb_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)|2-bayt birden çok baytlı karakter karşılık gelen 1-bayt birden çok baytlı karakter dönüştürme|  
|[mbrtoc16, mbrtoc32](../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)|Birden çok baytlı karakter eşdeğer UTF-16 veya UTF-32 karakter dönüştürme|  
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Geniş karakterler karşılık gelen bir dizi için birden çok baytlı karakter dizisi Dönüştür|  
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Birden çok baytlı karakter karşılık gelen geniş karakter dönüştürme|  
|[strtod, _strtod_l, wcstod, _wcstod_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|Dizeye dönüştürme`double`|  
|[strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|Dizeye dönüştürme `long` tamsayı|  
|[strtoul, _strtoul_l, wcstoul, _wcstoul_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|Dizeye dönüştürme `unsigned long` tamsayı|  
|[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|Yerel ayarlara özgü bilgilere göre Harmanlanmış forma dize dönüştürme|  
|[toascii, __toascii](../c-runtime-library/reference/toascii-toascii.md)|ASCII kodu karakter dönüştürme||  
|[tolower, _tolower, towlower, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md), [_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Karakter test etme ve şu anda büyük harf, küçük harfe Dönüştür|  
|[tolower, _tolower, towlower, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)|Koşulsuz olarak küçük harf karakter dönüştürme|[System::String::ToLower](https://msdn.microsoft.com/en-us/library/system.string.tolower.aspx)|  
|[toupper, _toupper, towupper, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md), [_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Karakter test etme ve şu anda küçük harfler, büyük harfe Dönüştür|  
|[toupper, _toupper, towupper, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|Koşulsuz olarak büyük harf karakter dönüştürme|  
|[_ultoa, _ultow](../c-runtime-library/reference/ultoa-ultow.md), [_ultoa_s, _ultow_s](../c-runtime-library/reference/ultoa-s-ultow-s.md)|Dönüştürme `unsigned long` dizeye|  
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Birden çok baytlı karakterler karşılık gelen bir dizi için geniş bir karakter dizisi Dönüştür|  
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Geniş karakter karşılık gelen birden çok baytlı karakter dönüştürme|  
|[atof, _atof_l, _wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Joker karakter dizeye dönüştürme bir`double`|   
|[atoi, _atoi_l, _wtoi, _wtoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Joker karakter dizeye dönüştürme`int`|  
|[_atoi64, _atoi64_l, _wtoi64, _wtoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Joker karakter dizeye dönüştürme`__int64`|  
|[atol, _atol_l, _wtol, _wtol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Joker karakter dizeye dönüştürme`long`|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kategorilere Göre Çalışma Zamanı Yordamları](../c-runtime-library/run-time-routines-by-category.md)