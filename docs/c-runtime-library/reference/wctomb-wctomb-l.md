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
ms.openlocfilehash: f10422d8efcebec62e77a495a6fb04c980da6060
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215167"
---
# <a name="wctomb-wctombl"></a>wctomb, _wctomb_l

Çok baytlı karaktere karşılık gelen bir geniş karakter dönüştürün. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md).

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
Bir geniş karakter.

## <a name="return-value"></a>Dönüş Değeri

Varsa **wctomb** geniş karakter dönüştürür isteğe bağlı olarak bir çok baytlı karakterin bayt sayısını döndürür (olan hiçbir zaman büyüktür **MB_CUR_MAX**) geniş karakter. Varsa *wchar* geniş karakterli null karakteri (L '\0') **wctomb** 1 döndürür. Hedef işaretçi *mbchar* olduğu **NULL**, **wctomb** 0 döndürür. Geçerli yerel ayarda dönüştürme mümkün değilse, **wctomb** -1 döndürür ve **errno** ayarlanır **EILSEQ**.

## <a name="remarks"></a>Açıklamalar

**Wctomb** işlev dönüştürür, *wchar* çok baytlı karaktere karşılık gelen bağımsız değişken ve sonucunda depolar *mbchar*. Herhangi bir programda herhangi bir noktasından işlevi çağırabilir. **wctomb** herhangi bir yerel ayara bağımlı davranış için; geçerli yerel ayarı kullanır **_wctomb_l** aynıdır **wctomb** bunun yerine iletilmiş yerel ayar kullanması hariç, aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

**wctomb** kendi parametrelerini doğrular. Varsa *mbchar* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev -1 döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wctomb**|\<stdlib.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu program wctomb işlevi davranışını gösterir.

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
[WideCharToMultiByte](/windows/desktop/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
