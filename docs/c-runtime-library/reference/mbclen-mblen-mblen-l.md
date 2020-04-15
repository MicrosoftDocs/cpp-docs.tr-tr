---
title: _mbclen, mblen, _mblen_l, _mbclen_l
description: Microsoft C Runtime Kitaplığı (CRT) _mbclen, mblen, _mblen_l ve _mbclen_l işlevlerini açıklar.
ms.date: 4/2/2020
api_name:
- _mbclen
- mblen
- _mblen_l
- _mbclen_l
- _o__mbclen
- _o__mbclen_l
- _o__mblen_l
- _o_mblen
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mblen
- ftclen
- _mbclen
- _mbclen_l
- tclen
- _ftclen
- _tclen
- mbclen
helpviewer_keywords:
- tclen function
- _mblen_l function
- _tclen function
- mblen_l function
- _mbclen function
- _mbclen_l function
- mbclen function
- mblen function
ms.assetid: d5eb92a0-b7a3-464a-aaf7-9890a8e3ed70
ms.openlocfilehash: 76e8771898d8baa65f275304a9aefdcaeeb5b3bd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341117"
---
# <a name="_mbclen-mblen-_mblen_l-_mbclen_l"></a>_mbclen, mblen, _mblen_l, _mbclen_l

Uzunluğu alır ve çok bayt lı bir karakterin geçerliliğini belirler.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
size_t _mbclen(
   const unsigned char *c
);
size_t _mbclen_l(
   unsigned char const* c,
   _locale_t locale
);
int mblen(
   const char *mbstr,
   size_t count
);
int _mblen_l(
   const char *mbstr,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*C*\
Çok bayt karakter.

*mbstr*\
Çok bayt lık bir dizinin adresi.

*Sayısı*\
Kontrol etmek için bayt sayısı.

*Yerel ayar*\
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

**_mbclen** ve **_mbclen_l** 1 veya 2, multibayt karakter *c*uzunluğuna göre dönmek . C multibayt *olsun* ya da olmasın, işlevler her zaman UTF-8 için 1 döndürür. **_mbclen**için hata iadesi yok.

*Mbstr* **NULL**değilse , **mblen** ve **_mblen_l** çok bayt karakterin uzunluğunu, baytolarak döndürer. **Mblen** ve **_mblen_l** fonksiyonları UTF-8'de doğru çalışır ve 1 ile 3 arasında bir değer döndürebilir. *Mbstr* **NULL** olduğunda (veya geniş karakterli null karakterini işaret ettiğinde), **mblen** ve **_mblen_l** return 0. *Mbstr'un* işaret ettiği nesne, ilk *sayım* karakterleri içinde geçerli bir çok bayt karakteri oluşturmalı veya **mblen** ve **_mblen_l** return -1 olmalıdır.

## <a name="remarks"></a>Açıklamalar

**_mbclen** işlevi, çok bayt karakter *c'* nin uzunluğunu baytolarak döndürür. *C,* çok baytlık bir karakterin kurşun baytını işaret etmiyorsa [(_ismbblead](ismbblead-ismbblead-l.md)için örtülü bir çağrıyla belirlendiği gibi, **_mbclen** sonucu tahmin edilemez.

**mblen,** geçerli bir çok bayt karakterse, *mbstr* baytlarındaki uzunluğu döndürür. Ayrıca, kod sayfasıyla ilişkili çok bayt karakter geçerliliğini de belirler. **mblen,** *mbstr'de*bulunan *sayı* veya daha az baytı inceler, ancak **MB_CUR_MAX** bayttan fazla değil.

Çıktı değeri, yerel LC_CTYPE **kategori** ayarından etkilenir. Bu işlevlerin **_l** soneki olmayan sürümleri, bu yerel eki bağımlı davranış için geçerli yerel alanı kullanır. **_l** suffixed sürümleri aynı şekilde, ancak bunun yerine geçirilen yerel parametre kullanın. Daha fazla bilgi için [setlocale](setlocale-wsetlocale.md) ve [Yerel'e](../../c-runtime-library/locale.md)bakın.

**_mbclen**, **_mblen_l**ve **_mbclen_l,** Standart C kitaplığınbir parçası değildir Microsoft'a özgüdir. Bunları taşınabilir kodu istediğiniz yerde kullanmanızı önermiyoruz. Standart C uyumluluğu için bunun yerine **mblen** veya **mbrlen** kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tclen**|Makro veya satır çizgisi işlevine eşler|**_mbclen**|Makro veya satır çizgisi işlevine eşler|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbclen**|\<mbstring.h>|
|**mblen**|\<stdlib.h>|
|**_mblen_l**|\<stdlib.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_mblen.c
/* illustrates the behavior of the mblen function
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
    int      i;
    char    *pmbc = (char *)malloc( sizeof( char ) );
    wchar_t  wc   = L'a';

    printf( "Convert wide character to multibyte character:\n" );
    wctomb_s( &i, pmbc, sizeof(char), wc );
    printf( "   Characters converted: %u\n", i );
    printf( "   Multibyte character: %x\n\n", *pmbc );

    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of multibyte character %x: %u\n", *pmbc, i );

    pmbc = NULL;
    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of NULL multibyte character %x: %u\n", pmbc, i );
}
```

```Output
Convert wide character to multibyte character:
   Characters converted: 1
   Multibyte character: 61

Length in bytes of multibyte character 61: 1
Length in bytes of NULL multibyte character 0: 0
```

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflandırması](../../c-runtime-library/character-classification.md)\
[Yerel ayar](../../c-runtime-library/locale.md)\
[Çok bayt-karakter dizilerinin yorumlanması](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)\
[_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md)\
[mbrlen](mbrlen.md)\
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)
