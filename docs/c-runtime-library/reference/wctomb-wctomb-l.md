---
title: wctomb, _wctomb_l
ms.date: 4/2/2020
api_name:
- _wctomb_l
- wctomb
- _o__wctomb_l
- _o_wctomb
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
- api-ms-win-crt-convert-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 162585ea866b4fb26cfaae3bc94345dadaba0baa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367409"
---
# <a name="wctomb-_wctomb_l"></a>wctomb, _wctomb_l

Geniş bir karakteri karşılık gelen çok bayt karaktere dönüştürün. Bu işlevlerin daha güvenli sürümleri mevcuttur; [wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md)bakın.

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

*Wchar*<br/>
Geniş bir karakter.

## <a name="return-value"></a>Dönüş Değeri

**Wctomb** geniş karakteri çok bayt karaktere dönüştürürse, geniş karakterdeki bayt sayısını **(MB_CUR_MAX'den**büyük olmayan) döndürür. *Wchar* geniş karakterli null karakter (L'\0') **ise, wctomb** 1 döndürür. Hedef işaretçi *mbchar* **NULL**ise, **wctomb** 0 döndürür. Geçerli yerel olarak dönüştürme mümkün değilse, **wctomb** -1 döndürür ve **errno** **EILSEQ**olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**Wctomb** işlevi *wchar* bağımsız değişkenini ilgili çok bayt karaktere dönüştürür ve sonucu *mbchar'da*depolar. İşlevi herhangi bir programdaki herhangi bir noktadan arayabilirsiniz. **wctomb** herhangi bir yerele bağımlı davranış için geçerli yerel kullanır; **_wctomb_l** **wctomb** ile aynıdır, ancak bunun yerine geçirilen yerelliği kullanır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

**wctomb** parametrelerini doğrular. *Mbchar* **NULL**ise, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlev -1 döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Wctomb**|\<stdlib.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

Bu program wctomb işlevinin davranışını göstermektedir.

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
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
