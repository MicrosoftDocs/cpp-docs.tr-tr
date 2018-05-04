---
title: Yerel ayar | Microsoft Docs
ms.custom: ''
ms.date: 04/11/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.international
dev_langs:
- C++
helpviewer_keywords:
- localization, locale
- country information
- language information routines
- setlocale function
- locale routines
ms.assetid: 442f8112-9288-44d7-be3c-15d22652093a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 638d4fbe6fd4dfce1fb3eeb246ef85c5b60fada0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="locale"></a>Yerel Ayar

*Yerel ayar* programınızı özelleştirmek için kullanabileceğiniz ülke/bölge ve dil ayarları için başvuruyor. Bazı yerel ayara bağımlı kategorileri, tarihleri ve parasal değerleri için görüntü biçimlerini içerir. Daha fazla bilgi için bkz: [yerel ayar kategorileri](../c-runtime-library/locale-categories.md).

 Kullanım [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) değiştirmek veya bazılarını veya tümünü olmadan çalışır kullanırken geçerli program veya iş parçacığı yerel ayar bilgileri sorgulamak için işlevi **_l** soneki. İşlevleriyle **_l** soneki yalnızca bu belirli işlevi yürütülmesi sırasında kendi yerel ayar bilgileri için geçirilen yerel ayar parametresi kullanır. Bir işlev ile birlikte kullanmak için bir yerel ayar oluşturmak için bir **_l** soneki, kullanın [_create_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md). Bu yerel ayar boşaltmak için kullanmak [_free_locale](../c-runtime-library/reference/free-locale.md). Geçerli yerel ayarı almak için [_get_current_locale](../c-runtime-library/reference/get-current-locale.md).

 Kullanım [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) denetlemek için her bir iş parçacığı olup kendi yerel ya da aynı yerel bir programda tüm iş parçacıkları paylaşır. Daha fazla bilgi için bkz: [yerel ayarlar ve kod sayfaları](../text/locales-and-code-pages.md).

 Daha güvenli aşağıdaki tablodaki işlevlerin sürümleri, belirttiği **_Yanları** ("güvenli") soneki. Daha fazla bilgi için bkz: [CRT'deki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md).

## <a name="locale-dependent-routines"></a>Yerel ayara bağımlı yordamlar

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|**setlocale** kategori ayar bağımlılığı|
|-------------|---------|---------------------------------------------|
|[atof, _atof_l, _wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Kayan nokta değeri için karakter dönüştürme|**LC_NUMERIC**|
|[atoi, _atoi_l, _wtoi, _wtoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Karakter tamsayı değerine dönüştürme|**LC_NUMERIC**|
|[_atoi64, _atoi64_l, _wtoi64, _wtoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|64 bit tamsayı değeri için karakter dönüştürme|**LC_NUMERIC**|
|[atol, _atol_l, _wtol, _wtol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Karakter uzunluğunda değerine dönüştürme|**LC_NUMERIC**|
|[_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Karakter çift uzun değerine dönüştürme|**LC_NUMERIC**|
|[is yordamları](../c-runtime-library/is-isw-routines.md)|Belirli bir koşula göre tamsayı verilen sınayın.|**LC_CTYPE**|
|[isleadbyte, _isleadbyte_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|Test baytı için|**LC_CTYPE**|
|[localeconv](../c-runtime-library/reference/localeconv.md)|Sayısal sayıları biçimlendirmek için uygun değerleri okuma|`LC_MONETARY, LC_NUMERIC`|
|[MB_CUR_MAX](../c-runtime-library/mb-cur-max.md)|Geçerli yerel ayarı (STDLIB içinde tanımlanan makrosu tüm birden çok baytlı karakter bayt cinsinden en büyük uzunluğu. Y)|**LC_CTYPE**|
|[_mbccpy, _mbccpy_l](../c-runtime-library/reference/mbccpy-mbccpy-l.md),[_mbccpy_s, _mbccpy_s_l](../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md)|Bir çok baytlı karakter kopyalama|**LC_CTYPE**|
|[_mbclen, mblen, _mblen_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Birden çok baytlı karakter bayt sayısını döndürmek ve doğrulama|**LC_CTYPE**|
|[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|Çok baytlı karakter dizeleri: dize; her karakter doğrula dize uzunluğu Döndür|**LC_CTYPE**|
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md),[mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Geniş karakterler karşılık gelen bir dizi için birden çok baytlı karakter dizisi Dönüştür|**LC_CTYPE**|
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Birden çok baytlı karakter karşılık gelen geniş karakter dönüştürme|**LC_CTYPE**|
|[Printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) işlevleri|Biçimlendirilmiş çıkışı yazma|**Lc_numerıc** (sayı tabanını karakter çıkış belirler)|
|[scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) işlevleri|Giriş okuma biçimlendirilmiş|**Lc_numerıc** (sayı tabanını karakter tanıma belirler)|
|[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)|Program için yerel seçin|Geçerli değil|
|[strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|İki dize karakterlerini karşılaştırma|**LC_COLLATE**|
|[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)|Servis talebi dikkate almaksızın iki dizeleri karşılaştırma|**LC_CTYPE**|
|[_stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|İki dize (büyük küçük harfe duyarlı) karakterlerini karşılaştırma|**LC_COLLATE**|
|[_strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|İlk karşılaştırmak **n** iki dize karakterlerini|**LC_COLLATE**|
|[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)|Servis talebi dikkate almaksızın iki dize karakterlerini karşılaştırın.|**LC_CTYPE**|
|[_strnicoll, _wcsnicoll, _mbsnicoll, _strnicoll_l, _wcsnicoll_l, _mbsnicoll_l](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|İlk karşılaştırmak **n** karakter iki dizeleri (büyük küçük harfe duyarlı)|**LC_COLLATE**|
|[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|Biçim tarih ve saat değeri göre sağlanan **biçimi** bağımsız değişken|**LC_TIME**|
|[_strlwr, _wcslwr, _mbslwr, _strlwr_l, _wcslwr_l, _mbslwr_l](../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md),[_strlwr_s, _strlwr_s_l, _mbslwr_s, _mbslwr_s_l, _wcslwr_s, _wcslwr_s_l](../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)|Dize dönüştürme, yerinde, her büyük harf küçük harflere verilen|**LC_CTYPE**|
|[strtod, _strtod_l, wcstod, _wcstod_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|Karakter dizeye dönüştürme **çift** değeri|**Lc_numerıc** (sayı tabanını karakter tanıma belirler)|
|[strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|Karakter dizeye dönüştürme **uzun** değeri|**Lc_numerıc** (sayı tabanını karakter tanıma belirler)|
|[strtoul, _strtoul_l, wcstoul, _wcstoul_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|İmzasız long değeri için karakter dizesi Dönüştür|**Lc_numerıc** (sayı tabanını karakter tanıma belirler)|
|[_strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l, _wcsupr](../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md),[_strupr_s, _strupr_s_l, _mbsupr_s, _mbsupr_s_l, _wcsupr_s, _wcsupr_s_l](../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)|, Yerinde, her küçük harf dizesindeki büyük harfe Dönüştür|**LC_CTYPE**|
|[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|Yerel ayar göre Harmanlanmış forma dize dönüştürme|**LC_COLLATE**|
|[tolower, _tolower, towlower, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md),[_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Karşılık gelen küçük harf karakter verilen Dönüştür|**LC_CTYPE**|
|[toupper, _toupper, towupper, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md),[_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Karşılık gelen büyük harf karakter verilen Dönüştür|**LC_CTYPE**|
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md),[wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Birden çok baytlı karakterler karşılık gelen bir dizi için geniş bir karakter dizisi Dönüştür|**LC_CTYPE**|
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md),[wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Geniş karakter karşılık gelen birden çok baytlı karakter dönüştürme|**LC_CTYPE**|

> [!NOTE]
> Birden çok baytlı yordamları için birden çok baytlı kod sayfası kümesiyle yerel eşdeğer olmalıdır [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). [_setmbcp](../c-runtime-library/reference/setmbcp.md), bağımsız değişkeni ile **_MB_CP_LOCALE** aynı sayfa birden çok baytlı kod yapar **setlocale** kod sayfası.

## <a name="see-also"></a>Ayrıca Bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
 [Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
