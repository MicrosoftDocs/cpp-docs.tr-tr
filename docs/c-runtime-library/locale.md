---
title: Yerel Ayar
ms.date: 04/11/2018
f1_keywords:
- c.international
helpviewer_keywords:
- localization, locale
- country information
- language information routines
- setlocale function
- locale routines
ms.assetid: 442f8112-9288-44d7-be3c-15d22652093a
ms.openlocfilehash: b5096d0b0f0990a89789993a12f383d060b91b3e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571489"
---
# <a name="locale"></a>Yerel Ayar

*Yerel ayar* programınızı özelleştirmek için kullanabileceğiniz ülke/bölge ve dil ayarları için ifade eder. Bazı yerel ayara bağımlı kategoriler, tarihleri ve parasal değerleri için görüntü biçimlerini içerir. Daha fazla bilgi için [yerel ayar kategorileri](../c-runtime-library/locale-categories.md).

Kullanım [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) değiştirmek veya bazı veya tüm işlevlerin kullanırken geçerli program ya da iş parçacığı yerel ayar bilgileri sorgulamak için işlev **_l** soneki. İşlevler ile **_l** soneki için kendi yerel ayar bilgilerinin o belirli işlevinin yalnızca yürütme sırasında geçirilen yerel ayar parametresini kullanır. Bir işlev ile birlikte kullanmak için bir yerel ayar oluşturmak için bir **_l** soneki, kullanın [_create_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md). Bu yerel ayar boşaltmak için kullanmak [_free_locale](../c-runtime-library/reference/free-locale.md). Geçerli yerel ayarı almak için kullanın [_get_current_locale](../c-runtime-library/reference/get-current-locale.md).

Kullanım [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) denetlemek için her bir iş parçacığı olup kendi yerel ayar veya bir programdaki tüm iş parçacıkları aynı yerel paylaşın. Daha fazla bilgi için [yerel ayarlar ve kod sayfaları](../text/locales-and-code-pages.md).

Aşağıdaki tabloda işlevlerin daha güvenli sürümleri mevcuttur, belirttiği **_Yanları** ("güvenli") soneki. Daha fazla bilgi için [CRT'deki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md).

## <a name="locale-dependent-routines"></a>Yerel ayara bağımlı yordamlar

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|**setlocale** kategori ayar bağımlılığı|
|-------------|---------|---------------------------------------------|
|[atof, _atof_l, _wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Karakter kayan nokta değerine dönüştürme|**LC_NUMERIC**|
|[atoi, _atoi_l, _wtoi, _wtoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Karakter tamsayı değerine dönüştürür.|**LC_NUMERIC**|
|[_atoi64, _atoi64_l, _wtoi64, _wtoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Karakter 64-bit tamsayı değerine dönüştürür.|**LC_NUMERIC**|
|[atol, _atol_l, _wtol, _wtol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Karakter uzunluğunda değerine dönüştürme|**LC_NUMERIC**|
|[_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Karakter çift uzun değerine dönüştürme|**LC_NUMERIC**|
|[is yordamları](../c-runtime-library/is-isw-routines.md)|Tamsayı belirli bir koşul için verilen test edin.|**LC_CTYPE**|
|[isleadbyte, _isleadbyte_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|Test için ön bayt|**LC_CTYPE**|
|[localeconv](../c-runtime-library/reference/localeconv.md)|Biçimlendirme sayısal miktarlar için uygun değerleri okuyun|`LC_MONETARY, LC_NUMERIC`|
|[MB_CUR_MAX](../c-runtime-library/mb-cur-max.md)|Geçerli yerel ayarı (makro içinde STDLIB tanımlanan içinde herhangi bir çok baytlı karakterin bayt cinsinden en fazla uzunluk. H)|**LC_CTYPE**|
|[_mbccpy, _mbccpy_l](../c-runtime-library/reference/mbccpy-mbccpy-l.md),[_mbccpy_s, _mbccpy_s_l](../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md)|Bir çok baytlı karakter kopyalayın|**LC_CTYPE**|
|[_mbclen, mblen, _mblen_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Doğrulama ve çok baytlı karakterdeki bayt sayısını döndürür|**LC_CTYPE**|
|[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|Çok baytlı karakter dizelerini:; dizesindeki her karakterle doğrula dize uzunluğunu döndürür|**LC_CTYPE**|
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md),[mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Dizi çok baytlı karakteri karşılık gelen geniş karakterler dizisi için Dönüştür|**LC_CTYPE**|
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Karşılık gelen geniş karakter için çok baytlı karakter dönüştürme|**LC_CTYPE**|
|[Printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) işlevleri|Biçimlendirilmiş çıkış yazma|**Lc_numerıc** (taban karakter çıkış belirler)|
|[scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) işlevleri|Giriş okuma biçimlendirilmiş|**Lc_numerıc** (taban karakter tanıma belirler)|
|[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)|Programın yerel ayar seçin|Geçerli değil|
|[strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|İki dizenin karakter karşılaştırma|**LC_COLLATE**|
|[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)|Çalışması dikkate almaksızın, iki dizeyi karşılaştırın|**LC_CTYPE**|
|[_stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|İki dize (büyük küçük harfe duyarlı) karakterlerini karşılaştırma|**LC_COLLATE**|
|[_strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|İlk karşılaştırma **n** iki dizenin karakter|**LC_COLLATE**|
|[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)|Servis talebi dikkate almaksızın, iki dizenin karakter karşılaştırın.|**LC_CTYPE**|
|[_strnicoll, _wcsnicoll, _mbsnicoll, _strnicoll_l, _wcsnicoll_l, _mbsnicoll_l](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|İlk karşılaştırma **n** karakterler iki dizenin (büyük küçük harfe duyarlı)|**LC_COLLATE**|
|[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|Biçim tarih ve saat değeri göre sağlanan **biçimi** bağımsız değişken|**LC_TIME**|
|[_strlwr, _wcslwr, _mbslwr, _strlwr_l, _wcslwr_l, _mbslwr_l](../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md),[_strlwr_s, _strlwr_s_l, _mbslwr_s, _mbslwr_s_l, _wcslwr_s, _wcslwr_s_l](../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)|Dönüştürme, bir yerde, her bir büyük harf, küçük harfe dizesi verilmiş|**LC_CTYPE**|
|[strtod, _strtod_l, wcstod, _wcstod_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|Karakter dizesi dönüştürme **çift** değeri|**Lc_numerıc** (taban karakter tanıma belirler)|
|[strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|Karakter dizesi dönüştürme **uzun** değeri|**Lc_numerıc** (taban karakter tanıma belirler)|
|[strtoul, _strtoul_l, wcstoul, _wcstoul_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|Karakter dizesi işaretsiz uzun değere Dönüştür|**Lc_numerıc** (taban karakter tanıma belirler)|
|[_strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l, _wcsupr](../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md),[_strupr_s, _strupr_s_l, _mbsupr_s, _mbsupr_s_l, _wcsupr_s, _wcsupr_s_l](../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)|Büyük harfe dizesindeki her küçük harfi yerinde Dönüştür|**LC_CTYPE**|
|[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|Yerel ayara göre Harmanlanmış form dize dönüştürün|**LC_COLLATE**|
|[tolower, _tolower, towlower, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md),[_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Belirli bir küçük harf karaktere karşılık gelen karakteri Dönüştür|**LC_CTYPE**|
|[toupper, _toupper, towupper, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md),[_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Karşılık gelen bir büyük harf karaktere verilen Dönüştür|**LC_CTYPE**|
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md),[wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Geniş karakter dizisi karşılık gelen çok baytlı karakter dizisine dönüştürme|**LC_CTYPE**|
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md),[wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Çok baytlı karaktere karşılık gelen geniş karakter dönüştürme|**LC_CTYPE**|

> [!NOTE]
> Çok baytlı rutinleri için çok baytlı kod sayfası ile yerel ayarlarını eşdeğer olmalıdır [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). [_setmbcp](../c-runtime-library/reference/setmbcp.md), bağımsız **_MB_CP_LOCALE** aynı sayfa çok baytlı kod yapar **setlocale** kod sayfası.

## <a name="see-also"></a>Ayrıca Bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
