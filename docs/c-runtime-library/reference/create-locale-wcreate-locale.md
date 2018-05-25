---
title: _create_locale, _wcreate_locale | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _create_locale
- __create_locale
- _wcreate_locale
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- create_locale
- _create_locale
- __create_locale
dev_langs:
- C++
helpviewer_keywords:
- locales, creating
- _create_locale function
- create_locale function
- __create_locale function
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9be41a2d156a522c74349c3457295502ae6d4f43
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="createlocale-wcreatelocale"></a>_create_locale, _wcreate_locale

Yerel ayar nesnesi oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
_locale_t _create_locale(
   int category,
   const char *locale
);
_locale_t _wcreate_locale(
   int category,
   const wchar_t *locale
);
```

### <a name="parameters"></a>Parametreler

*Kategori*<br/>
Kategori.

*Yerel ayar*<br/>
Yerel ayar tanımlayıcı.

## <a name="return-value"></a>Dönüş Değeri

Geçerli bir *yerel ayar* ve *kategori* verilir, olarak belirtilen yerel ayar ayarlarına döndüren bir **_locale_t** nesnesi. Geçerli yerel ayar programının değiştirilmez.

## <a name="remarks"></a>Açıklamalar

**_Create_locale** işlevi yerel ayarlara özgü sürümlerinde, birçok CRT işlevleri kullanmak için belirli bölgeye özgü ayarları temsil eden bir nesne oluşturmanıza olanak sağlar (ile işlevleri **_l** soneki ). Benzer bir davranıştır **setlocale**, geçerli ortama belirtilen yerel ayarları uygulamak yerine kaydedilir ancak bu bir **_locale_t** döndürülen yapısı. **_Locale_t** yapısı serbest kullanarak [_free_locale](free-locale.md) zaman artık gerekli.

**_wcreate_locale** bir joker karakter sürümü **_create_locale**; *yerel ayar* bağımsız değişkeni **_wcreate_locale** bir joker karakter dizesidir. **_wcreate_locale** ve **_create_locale** Aksi takdirde aynı şekilde davranır.

*Kategori* bağımsız değişkeni etkilenen yerel ayarlara özgü davranış bölümlerini belirtir. İçin kullanılan bayraklarını *kategori* ve etkilediklerini program aşağıdaki tabloda gösterildiği gibi bölümlerdir.

|*Kategori* bayrağı|Etkiler|
|-|-|
**LC_ALL**|Aşağıda listelenen tüm kategoriler.
**LC_COLLATE**|**Strcoll**, **_stricoll**, **wcscoll**, **_wcsicoll**, **strxfrm**, **_ strncoll**, **_strnicoll**, **_wcsncoll**, **_wcsnicoll**, ve **wcsxfrm** işlevleri.
**LC_CTYPE**|Karakter işleme işlevleri (dışında **isdigit**, **isxdigit**, **mbstowcs**, ve **mbtowc**, hangi etkilenmez).
**LC_MONETARY**|Tarafından döndürülen biçimlendirme parasal bilgileri **localeconv** işlevi.
**LC_NUMERIC**|Karakter biçimlendirilmiş çıktı yordamları için ondalık (gibi **printf**), veri dönüştürme yordamları ve tarafından döndürülen parasal biçimlendirme bilgi **localeconv**. Ondalık nokta karakteri yanı sıra **lc_numerıc** kümeleri binlik ayırıcı ve gruplandırma denetimi tarafından döndürülen dize [localeconv](localeconv.md).
**LC_TIME**|**Strftime** ve **wcsftime** işlevleri.

Bu işlev doğrular *kategori* ve *yerel* parametreleri. Kategori parametre önceki tabloda verilen değerlerden biri değilse veya yoksa *yerel ayar* olan **NULL**, işlevi döndürür **NULL**.

*Yerel* bağımsız değişkeni bir işaretçidir yerel belirten bir dize. Biçimi hakkında bilgi için *yerel ayar* bağımsız değişkeni, bkz: [yerel ayar adları, diller ve ülke/bölge dizeleri](../../c-runtime-library/locale-names-languages-and-country-region-strings.md).

*Yerel* bağımsız değişkeni bir yerel ayar adı, bir dil dizesi, bir dil dize ve ülke/bölge kodu, bir kod sayfası veya bir dil dize, ülke/bölge kodu ve kod sayfası alabilir. Karakter başına iki bayttan fazla gerektiren kod sayfaları dışında Windows NLS API tarafından desteklenen tüm kullanılabilir yerel ayar adları, diller, ülke/bölge kodları ve kod sayfaları kümesini içerir — örneğin, UTF-7 ve UTF-8. UTF-7 veya UTF-8 ' gibi bir kod sayfası sağlarsanız, **_create_locale** başarısız ve dönüş **NULL**. Yerel ayar adları tarafından desteklenen kümesi **_create_locale** açıklanan [yerel ayar adları, diller ve ülke/bölge dizeleri](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Tarafından desteklenen dil ve ülke/bölge dizeleri kümesi **_create_locale** listelenen [dil dizeleri](../../c-runtime-library/language-strings.md) ve [ülke/bölge dizeleri](../../c-runtime-library/country-region-strings.md).

Yerel ayarlar hakkında daha fazla bilgi için bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md).

Bu işlev, önceki adını **__create_locale** (iki başında alt çizgi ile), kullanım dışı bırakıldı.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_create_locale**|\<Locale.h >|
|**_wcreate_locale**|\<Locale.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_create_locale.c
// Sets the current locale to "de-CH" using the
// setlocale function and demonstrates its effect on the strftime
// function.

#include <stdio.h>
#include <locale.h>
#include <time.h>

int main(void)
{
    time_t ltime;
    struct tm thetime;
    unsigned char str[100];
    _locale_t locale;

    // Create a locale object representing the German (Switzerland) locale
    locale = _create_locale(LC_ALL, "de-CH");
    time (&ltime);
    _gmtime64_s(&thetime, &ltime);

    // %#x is the long date representation, appropriate to
    // the current locale
    if (!_strftime_l((char *)str, 100, "%#x",
                     (const struct tm *)&thetime, locale))
    {
        printf("_strftime_l failed!\n");
    }
    else
    {
        printf("In de-CH locale, _strftime_l returns '%s'\n", str);
    }

    _free_locale(locale);

    // Create a locale object representing the default C locale
    locale = _create_locale(LC_ALL, "C");
    time(&ltime);
    _gmtime64_s(&thetime, &ltime);

    if (!_strftime_l((char *)str, 100, "%#x",
                     (const struct tm *)&thetime, locale))
    {
        printf("_strftime_l failed!\n");
    }
    else
    {
        printf("In 'C' locale, _strftime_l returns '%s'\n", str);
    }

    _free_locale(locale);
}
```

```Output
In de-CH locale, _strftime_l returns 'Samstag, 9. Februar 2002'
In 'C' locale, _strftime_l returns 'Saturday, February 09, 2002'
```

## <a name="see-also"></a>Ayrıca bkz.

[Yerel ayar adları, diller ve ülke/bölge dizeleri](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Dil Dizeleri](../../c-runtime-library/language-strings.md)<br/>
[Ülke/bölge dizeleri](../../c-runtime-library/country-region-strings.md)<br/>
[_free_locale](free-locale.md)<br/>
[_configthreadlocale](configthreadlocale.md)<br/>
[setlocale](../../preprocessor/setlocale.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
