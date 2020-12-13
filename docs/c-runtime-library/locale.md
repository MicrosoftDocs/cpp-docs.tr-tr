---
description: 'Daha fazla bilgi edinin: yerel ayar'
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
ms.openlocfilehash: 660a4fb0103de8c1ac06272c711e02fcd6d12289
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331068"
---
# <a name="locale"></a>Yerel Ayar

*Yerel ayar* , programınızı özelleştirmek için kullanabileceğiniz ülke/bölge ve dil ayarlarını gösterir. Bir yerel ayara bağımlı kategoriler, tarihlerin ve parasal değerlerin görüntüleme biçimlerini içerir. Daha fazla bilgi için bkz. [yerel ayar kategorileri](../c-runtime-library/locale-categories.md).

İşlevleri **_l** soneki olmadan kullanırken, geçerli programın veya iş parçacığı yerel ayar bilgilerinin bazılarını veya tümünü değiştirmek veya sorgulamak için [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) işlevini kullanın. **_L** sonekine sahip işlevler, yalnızca söz konusu işlevin yürütülmesi sırasında yerel ayar bilgileri için geçirilen yerel ayar parametresini kullanır. **_L** sonekine sahip bir işlevle kullanmak üzere bir yerel ayar oluşturmak için [_create_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)kullanın. Bu yerel ayarı serbest bırakmak için [_free_locale](../c-runtime-library/reference/free-locale.md)kullanın. Geçerli yerel ayarı almak için [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)kullanın.

Her bir iş parçacığının kendi yerel ayarına sahip olup olmadığını denetlemek için [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) kullanın veya bir programdaki tüm iş parçacıkları aynı yerel ayarı paylaşır. Daha fazla bilgi için bkz. [yerel ayarlar ve kod sayfaları](../text/locales-and-code-pages.md).

Aşağıdaki tablodaki işlevlerin daha güvenli sürümleri, **_s** ("güvenli") son eki tarafından gösterilir. Daha fazla bilgi için bkz. [CRT Içindeki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md).

## <a name="locale-dependent-routines"></a>Locale-Dependent yordamlar

|Yordam|Kullanın|**setlocale** kategori ayarı bağımlılığı|
|-------------|---------|---------------------------------------------|
|[atof, _atof_l, _wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Karakteri kayan noktalı değere Dönüştür|**LC_NUMERIC**|
|[atoi, _atoi_l, _wtoi, _wtoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Karakteri tamsayı değerine Dönüştür|**LC_NUMERIC**|
|[_atoi64, _atoi64_l, _wtoi64, _wtoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Karakteri 64-bit tamsayı değerine Dönüştür|**LC_NUMERIC**|
|[atol, _atol_l, _wtol, _wtol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Karakteri Long değere Dönüştür|**LC_NUMERIC**|
|[_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Karakteri çift uzun değere Dönüştür|**LC_NUMERIC**|
|[Bu yordamlar](../c-runtime-library/is-isw-routines.md)|Belirli bir koşul için test verilen tamsayı.|**LC_CTYPE**|
|[isleadbyte, _isleadbyte_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|Ön bayt için test|**LC_CTYPE**|
|[localeconv](../c-runtime-library/reference/localeconv.md)|Sayısal miktarları biçimlendirmek için uygun değerleri okuyun|`LC_MONETARY, LC_NUMERIC`|
|[MB_CUR_MAX](../c-runtime-library/mb-cur-max.md)|Geçerli yerel ayarda herhangi bir çok baytlı karakterin bayt cinsinden en fazla uzunluğu (STDLIB içinde tanımlanan makro. Olsun|**LC_CTYPE**|
|[_mbccpy, _mbccpy_l](../c-runtime-library/reference/mbccpy-mbccpy-l.md),[_mbccpy_s, _mbccpy_s_l](../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md)|Bir çok baytlı karakter Kopyala|**LC_CTYPE**|
|[_mbclen, mblen, _mblen_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Çok baytlı karakterdeki bayt sayısını doğrulayın ve döndürün|**LC_CTYPE**|
|[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|Çok baytlı karakter dizeleri için: dizedeki her karakteri doğrulama; dönüş dizesi uzunluğu|**LC_CTYPE**|
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md),[mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Çok baytlı karakterlerin dizisini karşılık gelen geniş karakter dizisine Dönüştür|**LC_CTYPE**|
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Çok baytlı karakteri karşılık gelen geniş karaktere Dönüştür|**LC_CTYPE**|
|[printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) işlevleri|Biçimlendirilen çıktıyı yaz|**LC_NUMERIC** (taban karakter çıkışını belirler)|
|[scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) işlevleri|Biçimli girişi oku|**LC_NUMERIC** (taban karakter tanımayı belirler)|
|[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)|Program için yerel ayar seçin|Geçerli değil|
|[strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|İki dizenin karakterlerini karşılaştırın|**LC_COLLATE**|
|[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)|Büyük/küçük harf olmadan iki dizeyi karşılaştırın|**LC_CTYPE**|
|[_stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|İki dizenin karakterlerini karşılaştırın (büyük/küçük harfe duyarsız)|**LC_COLLATE**|
|[_strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|İki dizenin ilk **n** karakterini karşılaştırın|**LC_COLLATE**|
|[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)|Büyük/küçük harfe bakılmaksızın iki dizenin karakterlerini karşılaştırın.|**LC_CTYPE**|
|[_strnicoll, _wcsnicoll, _mbsnicoll, _strnicoll_l, _wcsnicoll_l, _mbsnicoll_l](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|İki dizenin ilk **n** karakterini karşılaştırın (büyük/küçük harfe duyarsız)|**LC_COLLATE**|
|[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|Tarih ve saat değerini sağlanan **Biçim** bağımsız değişkenine göre Biçimlendir|**LC_TIME**|
|[_strlwr, _wcslwr, _mbslwr, _strlwr_l, _wcslwr_l, _mbslwr_l](../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md),[_strlwr_s, _strlwr_s_l, _mbslwr_s, _mbslwr_s_l,](../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md) _wcslwr_s, _wcslwr_s_l|Yerinde, belirli bir dizedeki büyük harfle küçük harfe Dönüştür|**LC_CTYPE**|
|[strtod, _strtod_l, wcstod, _wcstod_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|Karakter dizesini değere Dönüştür **`double`**|**LC_NUMERIC** (taban karakter tanımayı belirler)|
|[strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|Karakter dizesini değere Dönüştür **`long`**|**LC_NUMERIC** (taban karakter tanımayı belirler)|
|[strtoul, _strtoul_l, wcstoul, _wcstoul_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|Karakter dizesini işaretsiz Long değere Dönüştür|**LC_NUMERIC** (taban karakter tanımayı belirler)|
|[_strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l, _wcsupr](../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md),[_strupr_s, _strupr_s_l, _mbsupr_s, _mbsupr_s_l,](../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md) _wcsupr_s, _wcsupr_s_l|Dizedeki tüm küçük harfleri büyük harfe Dönüştür|**LC_CTYPE**|
|[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|Dizeyi yerel ayara göre harmanlanmış biçimde Dönüştür|**LC_COLLATE**|
|[ToLower, _tolower, kasada alt, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md),[_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Verilen karakteri karşılık gelen küçük harfli karaktere Dönüştür|**LC_CTYPE**|
|[ToUpper, _toupper, kasaüst, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md),[_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Verilen karakteri karşılık gelen büyük harfe Dönüştür|**LC_CTYPE**|
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md),[wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Geniş karakter sırasını, çok baytlı karakterlerin karşılık gelen dizisine Dönüştür|**LC_CTYPE**|
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md),[wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Geniş karakteri karşılık gelen çok baytlı karaktere Dönüştür|**LC_CTYPE**|

> [!NOTE]
> Çok baytlı yordamlar için çok baytlı kod sayfası, [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)ile yerel ayar kümesine eşdeğer olmalıdır. [_setmbcp](../c-runtime-library/reference/setmbcp.md), **_MB_CP_LOCALE** bağımsız değişkeni ile, çok baytlı kod sayfasını **setlocale** kod sayfasıyla aynı hale getirir.

## <a name="see-also"></a>Ayrıca bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
