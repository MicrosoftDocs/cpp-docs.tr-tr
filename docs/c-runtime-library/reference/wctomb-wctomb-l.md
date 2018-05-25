---
title: wctomb, _wctomb_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wctomb_l
- wctomb
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wctomb
dev_langs:
- C++
helpviewer_keywords:
- string conversion, wide characters
- wide characters, converting
- _wctomb_l function
- wctomb function
- wctomb_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 972d8e3f1798a7498173c3d8b0677bb57231b990
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="wctomb-wctombl"></a>wctomb, _wctomb_l

Geniş karakter karşılık gelen birden çok baytlı karakter dönüştürün. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md).

## <a name="syntax"></a>Sözdizimi

```C
int wctomb(
   char *mbchar,
   wchar_t wchar
);
int _wctomb_l(
   char *mbchar,
   wchar_t wchar,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*mbchar*<br/>
Birden çok baytlı karakter adresi.

*wchar*<br/>
Geniş karakter.

## <a name="return-value"></a>Dönüş Değeri

Varsa **wctomb** geniş karakter dönüştürür isteğe bağlı olarak birden çok baytlı karakter bayt sayısını döndürür (hangi asla büyük **MB_CUR_MAX**) geniş karakter. Varsa *wchar* joker karakter null karakteri (M '\0'), **wctomb** 1 döndürür. Varsa hedef işaretçi *mbchar* olan **NULL**, **wctomb** 0 döndürür. Dönüştürme geçerli yerel ayarda mümkün değilse, **wctomb** -1 döndürür ve **errno** ayarlanır **EILSEQ**.

## <a name="remarks"></a>Açıklamalar

**Wctomb** işlev dönüştürür kendi *wchar* karşılık gelen birden çok baytlı karakter bağımsız değişkeni ve sonucunda depolar *mbchar*. Herhangi bir noktadan herhangi bir programda işlevini çağırın. **wctomb** geçerli yerel ayar için tüm yerel ayara bağımlı davranışı; kullanır **_wctomb_l** aynıdır **wctomb** yerine geçirilen yerel ayar kullanır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

**wctomb** parametrelerini doğrular. Varsa *mbchar* olan **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve işlev -1 döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wctomb**|\<stdlib.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu program wctomb işlevi davranışını gösterilmektedir.

```cpp
// crt_wctomb.cpp
// compile with: /W3
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int i;
   wchar_t wc = L'a';
   char *pmb = (char *)malloc( MB_CUR_MAX );

   printf( "Convert a wide character:\n" );
   i = wctomb( pmb, wc ); // C4996
   // Note: wctomb is deprecated; consider using wctomb_s
   printf( "   Characters converted: %u\n", i );
   printf( "   Multibyte character: %.1s\n\n", pmb );
}
```

```Output
Convert a wide character:
   Characters converted: 1
   Multibyte character: a
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)<br/>
