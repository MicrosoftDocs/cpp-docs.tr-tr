---
title: _mbclen, mblen, _mblen_l, _mbclen_l
ms.date: 01/22/2019
apiname:
- _mbclen
- mblen
- _mblen_l
- _mbclen_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: b7888b0b8c87a632dcbb63f54ade11080c7a309a
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702966"
---
# <a name="mbclen-mblen-mblenl-mbclenl"></a>_mbclen, mblen, _mblen_l, _mbclen_l

Uzunluğu alır ve çok baytlı karakterin geçerliliğini belirler.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*c*<br/>
Çok baytlı karakter.

*mbstr*<br/>
Bir çok baytlı karakter baytı dizesi adresi.

*Sayısı*<br/>
Denetlenecek bayt sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbclen** döndürür 1 veya 2 olup olmadığına göre çok baytlı karakterin *c* 1 veya 2 bayt uzunluğunda. Herhangi bir hata için dönüş **_mbclen**. Varsa *mbstr* değil **NULL**, **mblen** çok baytlı karakterinin bayt cinsinden uzunluğunu döndürür. Varsa *mbstr* olduğu **NULL** veya geniş karakterli null karakterini gösteriyorsa **mblen** 0 döndürür. Nesne, *mbstr* noktalarına değil geçerli çok baytlı bir karakterin ilk form *sayısı* karakter **mblen** -1 döndürür.

## <a name="remarks"></a>Açıklamalar

**_Mbclen** işlevi çok baytlı karakterinin bayt cinsinden uzunluğunu döndürür *c*. Varsa *c* örtük çağrıyla tarafından belirlendiği çok baytlı karakterin ön baytını işaret etmiyor **_ismbblead**, sonucunu **_mbclen** tahmin edilemez.

**mblen** bayt cinsinden uzunluğunu döndürür *mbstr* geçerli çok baytlı karakterse ve kod sayfasıyla ilişkili çok baytlı karakter geçerliliğini belirler. **mblen** inceler *sayısı* veya içindeki daha az baytı *mbstr*, fazlasını **MB_CUR_MAX** bayt.

Çıkış değeri tarafından etkilenen **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** soneki, bu yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_L** sonekli sürümleri aynı davranır, ancak bunun yerine iletilmiş yerel ayar parametresini kullanırlar. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tclen**|Makro veya satır içi işleve eşlenir|**_mbclen**|Makro veya satır içi işleve eşlenir|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbclen**|\<Mbstring.h >|
|**mblen**|\<stdlib.h >|
|**_mblen_l**|\<stdlib.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
