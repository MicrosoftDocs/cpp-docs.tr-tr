---
title: _create_locale, _wcreate_locale
ms.date: 11/04/2016
api_name:
- _create_locale
- __create_locale
- _wcreate_locale
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
ms.openlocfilehash: a7098dc572ecdbefd891efc8443e977b01850fa4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938850"
---
# <a name="_create_locale-_wcreate_locale"></a>_create_locale, _wcreate_locale

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
Alan.

*ayarlar*<br/>
Yerel ayar tanımlayıcı.

## <a name="return-value"></a>Dönüş Değeri

Geçerli bir *yerel ayar* ve *Kategori* verilirse, belirtilen yerel ayar ayarlarını **_locale_t** nesnesi olarak döndürür. Programın geçerli yerel ayarları değiştirilmez.

## <a name="remarks"></a>Açıklamalar

**_Create_locale** işlevi, çok sayıda CRT işlevinin ( **_l** sonekine sahip işlevler) yerel ayara özgü sürümlerinde kullanılmak üzere belirli bölgeye özgü ayarları temsil eden bir nesne oluşturmanıza olanak sağlar. Bu davranış, belirtilen yerel ayar ayarlarını geçerli ortama uygulamak yerine **setlocale**'e benzerdir, ancak ayarlar döndürülen bir **_locale_t** yapısına kaydedilir. **_Locale_t** yapısı artık gerekli olmadığında [_free_locale](free-locale.md) kullanılarak serbest bırakılmalıdır.

**_wcreate_locale** , **_create_locale**öğesinin geniş karakterli bir sürümüdür. **_wcreate_locale** için *yerel ayar* bağımsız değişkeni geniş karakterli bir dizedir. **_wcreate_locale** ve **_create_locale** aynı şekilde aynı şekilde davranır.

*Kategori* bağımsız değişkeni, yerel ayara özgü davranışın etkilenme parçalarını belirtir. *Kategori* için kullanılan bayraklar ve bunların etkilediği programın bölümleri bu tabloda gösterilmiştir:

| *Kategori* bayrağı | Ekranlarını |
|-----------------|---------|
| **LC_ALL** |Aşağıda listelendiği gibi tüm kategoriler. |
| **LC_COLLATE** |**Strcoll**, **_stricoll**, **wcscoll**, **_wcsicoll**, **strxfrm**, **_strncoll**, **_strnicoll**, **_wcsncoll**, **_wcsnicoll**ve **wcsxfrm** işlevleri. |
| **LC_CTYPE** | Karakter işleme işlevleri (etkilenmeyen **IsDigit**, **ısxdigit**, **mbstowcs**ve **mbtowc**hariç). |
| **LC_MONETARY** | **Localeconv** işlevi tarafından döndürülen parasal biçimlendirme bilgileri. |
| **LC_NUMERIC** | Biçimlendirilmiş çıkış yordamları ( **printf**gibi) için, veri dönüştürme yordamları için ve **localeconv**tarafından döndürülen parasal olmayan biçimlendirme bilgileri için ondalık nokta karakteri. **LC_NUMERIC** , ondalık noktalı karaktere ek olarak, binlerce ayırıcıyı ve [localeconv](localeconv.md)tarafından döndürülen gruplama denetimi dizesini ayarlar. |
| **LC_TIME** | **Strftime** ve **wcsftime** işlevleri. |

Bu işlev *Kategori* ve *yerel ayar* parametrelerini doğrular. Kategori parametresi önceki tabloda verilen değerlerden biri değilse veya *yerel ayar* **null**ise, işlev **null**değerini döndürür.

*Yerel ayar* bağımsız değişkeni, yerel ayarı belirten bir dizeye yönelik bir işaretçidir. *Yerel ayar* bağımsız değişkeninin biçimi hakkında daha fazla bilgi için bkz. [yerel ayar adları, diller ve ülke/bölge dizeleri](../../c-runtime-library/locale-names-languages-and-country-region-strings.md).

*Yerel ayar* bağımsız değişkeni bir yerel ayar adı, bir dil dizesi, bir dil dizesi ve ülke/bölge kodu, kod sayfası veya dil dizesi, ülke/bölge kodu ve kod sayfası alabilir. Kullanılabilir yerel ayar adları, diller, ülke/bölge kodları ve kod sayfaları, karakter başına iki bayttan fazlasını gerektiren kod sayfaları dışında Windows NLS API 'SI tarafından desteklenen tüm dosyaları içerir (örneğin, UTF-7 ve UTF-8). UTF-7 veya UTF-8 gibi bir kod sayfası sağlarsanız, **_create_locale** başarısız olur ve **null**döndürür. **_Create_locale** tarafından desteklenen yerel ayar adları kümesi, [yerel ayar adları, diller ve ülke/bölge dizeleri](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)bölümünde açıklanmaktadır. **_Create_locale** tarafından desteklenen dil ve ülke/bölge dizeleri kümesi, [dil dizeleri](../../c-runtime-library/language-strings.md) ve [ülke/bölge dizeleri](../../c-runtime-library/country-region-strings.md)içinde listelenir.

Yerel ayarlar hakkında daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md).

Bu işlevin önceki adı, **__create_locale** (iki önde gelen alt çizgi ile) kullanım dışıdır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_create_locale**|\<locale. h >|
|**_wcreate_locale**|\<locale. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
