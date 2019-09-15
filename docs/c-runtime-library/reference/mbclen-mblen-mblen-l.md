---
title: _mbclen, mblen, _mblen_l, _mbclen_l
ms.date: 01/22/2019
api_name:
- _mbclen
- mblen
- _mblen_l
- _mbclen_l
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
ms.openlocfilehash: 96775f513b33eb407981480c17cb609dd85383f6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952572"
---
# <a name="_mbclen-mblen-_mblen_l-_mbclen_l"></a>_mbclen, mblen, _mblen_l, _mbclen_l

Uzunluğu alır ve çok baytlı bir karakterin geçerliliğini belirler.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Çok baytlı karakter bayt dizisinin adresi.

*biriktirme*<br/>
Denetlenecek bayt sayısı.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbclen** , *c* çok baytlı karakterinin 1 veya 2 bayt uzunluğunda olup olmadığına göre 1 veya 2 değerini döndürür. **_Mbclen**için hata döndürme yok. *Mbstr* **null**değilse **mblen** , çok baytlı karakterin bayt cinsinden uzunluğunu döndürür. *Mbstr* **null** ise veya geniş karakterli boş karakteri gösteriyorsa **mblen** 0 döndürür. *Mbstr* tarafından işaret edilen nesne ilk *sayı* karakterleri içinde geçerli bir çok baytlı karakter oluşturmazsa, **mblen** ,-1 döndürür.

## <a name="remarks"></a>Açıklamalar

**_Mbclen** işlevi, *c*çok baytlı karakterinin karakter cinsinden uzunluğunu döndürür. *C* , **_ismbblider**'e örtük bir çağrı tarafından belirlendiği şekilde çok baytlı bir karakterin ön bayta işaret etmez, **_mbclen** sonucu tahmin edilemez.

**mblen** , geçerli bir çok baytlı karakter ise ve kod sayfasıyla ilişkili çok baytlı karakter geçerliliğini belirlerse *mbstr* 'nin bayt cinsinden uzunluğunu döndürür. **mblen** sayısı, *mbstr*içinde bulunan ancak **MB_CUR_MAX** bayttan fazla değil, *Count* veya daha az bayt inceler.

Çıkış değeri yerel ayarın **LC_CTYPE** kategori ayarından etkilenir; daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md) . **_L** sonekine sahip olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_L** soneki sabit sürümleri aynı şekilde davranır, ancak bunun yerine geçirilen yerel ayar parametresini kullanırlar. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tclen**|Makroya veya satır içi işleve eşlenir|**_mbclen**|Makroya veya satır içi işleve eşlenir|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbclen**|\<mbstring. h >|
|**mblen**|\<Stdlib. h >|
|**_mblen_l**|\<Stdlib. h >|

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
