---
title: wctomb, _wctomb_l
ms.date: 11/04/2016
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wctomb
helpviewer_keywords:
- string conversion, wide characters
- wide characters, converting
- _wctomb_l function
- wctomb function
- wctomb_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
ms.openlocfilehash: 6902ff925e49d894f70b0d7083b99388d5271d1d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500737"
---
# <a name="wctomb-_wctomb_l"></a>wctomb, _wctomb_l

Geniş bir karakteri karşılık gelen çok baytlı karaktere dönüştürün. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [wctomb_s, _wckaldırıldı _s_l](wctomb-s-wctomb-s-l.md).

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
Çok baytlı bir karakterin adresi.

*wchar*<br/>
Geniş bir karakter.

## <a name="return-value"></a>Dönüş Değeri

**Wctomb** geniş karakteri çok baytlı bir karaktere dönüştürdüğünde, geniş karakter içindeki bayt sayısını ( **MB_CUR_MAX**' dan büyük olmayan) döndürür. *Wchar* , geniş karakterli null karakterdir (L ' \ 0 '), **wctomb** 1 döndürür. Hedef işaretçi *mbchar* değeri **null**ise, **wctomb** 0 döndürür. Dönüştürme geçerli yerel ayarda mümkün değilse, **wctomb** -1 döndürür ve **errno** , **eilseq**olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**Wctomb** işlevi, *wchar* bağımsız değişkenini karşılık gelen çok baytlı karaktere dönüştürür ve sonucu *mbchar*üzerinde depolar. İşlevi herhangi bir programda herhangi bir noktadan çağırabilirsiniz. **wctomb** , herhangi bir yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_wckaldırıldı _l** , bunun yerine geçirilen yerel ayarı kullanması dışında **wctomb** ile aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

**wctomb** , parametrelerini doğrular. *Mbchar* **null**ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev-1 döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wctomb**|\<Stdlib. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu program wctomb işlevinin davranışını gösterir.

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
[Widechartoçok baytlı](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
