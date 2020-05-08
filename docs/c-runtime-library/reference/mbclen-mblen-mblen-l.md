---
title: _mbclen, mblen, _mblen_l, _mbclen_l
description: Microsoft C çalışma zamanı kitaplığı (CRT) _mbclen, mblen, _mblen_l ve _mbclen_l işlevlerini açıklar.
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: b004babc9e7c82d25cd52ec036c3061c99b5f367
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914365"
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

*,*\
Çok baytlı karakter.

*mbstr*\
Çok baytlı karakter bayt dizisinin adresi.

*biriktirme*\
Denetlenecek bayt sayısı.

*ayarlar*\
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbclen** ve **_mbclen_l** 1 veya 2 çok *baytlı karakterin uzunluğuna*göre 1 veya 2 değerini döndürür. İşlevler, *c* 'nin çok baytlı olup OLMADıĞı, UTF-8 için her zaman 1 döndürür. **_Mbclen**için hata döndürülemiyor.

*Mbstr* **null**değilse, **mblen** ve **_mblen_l** çok baytlı karakterin uzunluğunu bayt olarak döndürür. **Mblen** ve **_mblen_l** işlevleri UTF-8 üzerinde doğru çalışır ve 1 ile 3 arasında bir değer döndürebilir. *Mbstr* **null** olduğunda (veya geniş karakterli null karakteri işaret ediyorsa), **mblen** ve **_mblen_l** 0 döndürür. *Mbstr* işaret eden nesne, ilk *sayı* karakterleri içinde geçerli bir çok baytlı karakter veya **mblen** ve **_mblen_l** Return-1 döndürür.

## <a name="remarks"></a>Açıklamalar

**_Mbclen** işlevi, *c*çok baytlı karakterin uzunluğunu bayt olarak döndürür. *C* , çok baytlı bir karakterin baş baytını işaret etmez ( [_ismbblead](ismbblead-ismbblead-l.md)örtük bir çağrı tarafından belirlendiği şekilde, **_mbclen** sonucu tahmin edilemez.

**mblen** , geçerli bir çok baytlı karakter ise *mbstr* 'nin bayt cinsinden uzunluğunu döndürür. Ayrıca kod sayfasıyla ilişkilendirilmiş çok baytlı karakter geçerliliğini belirler. **mblen** sayısı, *mbstr*içinde içerilen, ancak **MB_CUR_MAX** bayttan fazla değil bayt *sayısını* inceler.

Çıkış değeri yerel ayarın **LC_CTYPE** kategori ayarından etkilenir. **_L** soneki olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_L** sonekli sürümler aynı şekilde davranır, ancak bunun yerine geçirilen yerel ayar parametresini kullanırlar. Daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md) ve [locale](../../c-runtime-library/locale.md).

**_mbclen**, **_Mblen_l**ve **_mbclen_l** standart C kitaplığının bir parçası değil, Microsoft 'a özgüdür. Bunları, taşınabilir kod istediğiniz yerde kullanmanız önerilmez. Standart C uyumluluğu için bunun yerine **mblen** veya **mbrlen** kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tclen**|Makroya veya satır içi işleve eşlenir|**_mbclen**|Makroya veya satır içi işleve eşlenir|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbclen**|\<mbstring. h>|
|**mblen**|\<Stdlib. h>|
|**_mblen_l**|\<Stdlib. h>|

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

[Karakter sınıflandırması](../../c-runtime-library/character-classification.md)\
[Ayarlar](../../c-runtime-library/locale.md)\
[Çok baytlı karakter dizilerinin yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)\
[_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md)\
[mbrlen](mbrlen.md)\
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)
