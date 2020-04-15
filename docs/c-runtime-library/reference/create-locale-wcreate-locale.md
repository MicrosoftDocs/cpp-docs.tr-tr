---
title: _create_locale, _wcreate_locale
ms.date: 4/2/2020
api_name:
- _create_locale
- __create_locale
- _wcreate_locale
- _o__create_locale
- _o__wcreate_locale
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- create_locale
- _create_locale
- __create_locale
helpviewer_keywords:
- locales, creating
- _create_locale function
- create_locale function
- __create_locale function
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
ms.openlocfilehash: 611eaf342776b9a0f57c4f55c52a841c3fd13fb5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348263"
---
# <a name="_create_locale-_wcreate_locale"></a>_create_locale, _wcreate_locale

Yerel bir nesne oluşturur.

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

Geçerli bir *yerel ayar* ve *kategori* verilirse, belirtilen yerel ayarlar **_locale_t** nesnesi olarak döndürür. Programın geçerli yerel ayarları değiştirilmez.

## <a name="remarks"></a>Açıklamalar

**_create_locale** işlevi, birçok CRT işlevinin **(_l** sonekli işlevler) yerele özgü sürümlerinde kullanılmak üzere belirli bölgeye özgü ayarları temsil eden bir nesne oluşturmanıza olanak tanır. Davranış, belirtilen yerel ayarlar ayarı geçerli ortama uygulamak yerine döndürülen **_locale_t** bir yapıya kaydedilse **de, ayaryerel'e**benzer. **_locale_t** yapısı artık ihtiyaç duyulmadığında [_free_locale](free-locale.md) kullanılarak serbest bırakılmalıdır.

**_wcreate_locale** **_create_locale**geniş karakterli bir versiyonudur; **_wcreate_locale** için *yerel* değişken geniş karakterli bir dizedir. **_wcreate_locale** ve **_create_locale** aynı şekilde davranan.

*Kategori* bağımsız değişkeni, etkilenen yerele özgü davranışın bölümlerini belirtir. *Kategori* için kullanılan bayraklar ve etkilediği programın bölümleri bu tabloda gösterildiği gibidir:

| *kategori* bayrağı | Etkiledi -ğini |
|-----------------|---------|
| **LC_ALL** |Tüm kategoriler, aşağıda listelenen. |
| **LC_COLLATE** |**Strcoll**, **_stricoll**, **wcscoll**, **_wcsicoll**, **strxfrm**, **_strncoll**, **_strnicoll**, **_wcsncoll**, **_wcsnicoll**, ve **wcsxfrm** fonksiyonları. |
| **LC_CTYPE** | Karakter işleme işlevleri **(isdigit**hariç , **isxdigit**, **mbstowcs**, ve **mbtowc**, etkilenmez). |
| **LC_MONETARY** | **Localeconv** işlevi tarafından döndürülen parasal biçimlendirme bilgileri. |
| **LC_NUMERIC** | Biçimlendirilmiş çıktı yordamları **(printf**gibi), veri dönüştürme yordamları ve **localeconv**tarafından döndürülen parasal olmayan biçimlendirme bilgileri için ondalık nokta karakteri. Ondalık nokta karakterine ek olarak, **LC_NUMERIC** binlerce ayırıcıyı ve [localeconv](localeconv.md)tarafından döndürülen gruplandırma denetim dizesini ayarlar. |
| **LC_TIME** | **Strftime** ve **wcsftime** fonksiyonları. |

Bu *işlev, kategori* ve *yerel parametreleri* doğrular. Kategori parametresi önceki tabloda verilen değerlerden biri değilse veya *yerel null* **ise,** işlev **NULL**döndürür.

*Yerel* değişken, yerel ile'yi belirten bir dize işaretçisidir. *Yerel* değişkenin biçimi hakkında bilgi için Bkz. [Yerel Adlar, Diller ve Ülke/Bölge Dizeleri.](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)

*Yerel* değişken, yerel ad, dil dizesi, dil dizesi ve ülke/bölge kodu, kod sayfası veya dil dizesi, ülke/bölge kodu ve kod sayfası alabilir. Kullanılabilir yerel adlar, diller, ülke/bölge kodları ve kod sayfaları kümesi, Windows NLS API tarafından desteklenen tüm bunları içerir. **_create_locale** tarafından desteklenen yerel adlar kümesi [Yerel Adlar, Diller ve Ülke/Bölge Dizeleri'nde](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)açıklanmıştır. **_create_locale** tarafından desteklenen dil ve ülke/bölge dizeleri kümesi [Dil Dizeleri](../../c-runtime-library/language-strings.md) ve [Ülke/Bölge Dizeleri](../../c-runtime-library/country-region-strings.md)olarak listelenir.

Yerel ayarlar hakkında daha fazla bilgi için [setlocale, _wsetlocale'](setlocale-wsetlocale.md)e bakın.

Bu işlevin önceki adı, **__create_locale** (iki satır altı çizilmiştir), amortismana uğramış.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_create_locale**|\<locale.h>|
|**_wcreate_locale**|\<locale.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Yerel Adlar, Diller ve Ülke/Bölge Dizeleri](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Dil Dizeleri](../../c-runtime-library/language-strings.md)<br/>
[Ülke/Bölge Dizeleri](../../c-runtime-library/country-region-strings.md)<br/>
[_free_locale](free-locale.md)<br/>
[_configthreadlocale](configthreadlocale.md)<br/>
[setlocale](../../preprocessor/setlocale.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
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
