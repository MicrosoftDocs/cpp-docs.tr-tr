---
title: 'Bessel Fonksiyonları: _j0, _j1, _jn, _y0, _y1, _yn'
ms.date: 4/2/2020
api_name:
- _j0
- _j1
- _jn
- _y0
- _y1
- _yn
- _o__j0
- _o__j1
- _o__jn
- _o__y0
- _o__y1
- _o__yn
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
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- c.bessel
- _j0
- _j1
- _jn
- _y0
- _y1
- _yn
helpviewer_keywords:
- Bessel functions
- _j0 function
- _j1 function
- _jn function
- _y0 function
- _y1 function
- _yn function
ms.assetid: a21a8bf1-df9d-4ba0-a8c2-e7ef71921d96
ms.openlocfilehash: cdf722c9c6f6055ac918d1bede59345a9ef8d90d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348656"
---
# <a name="bessel-functions-_j0-_j1-_jn-_y0-_y1-_yn"></a>Bessel Fonksiyonları: _j0, _j1, _jn, _y0, _y1, _yn

0, 1 veya n siparişlerinin birinci veya ikinci türünün Bessel işlevini hesaplar. Bessel fonksiyonları genellikle elektromanyetik dalga teorisinin matematiğinde kullanılır.

## <a name="syntax"></a>Sözdizimi

```C
double _j0(
   double x
);
double _j1(
   double x
);
double _jn(
   int n,
   double x
);
double _y0(
   double x
);
double _y1(
   double x
);
double _yn(
   int n,
   double x
);
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Kayan nokta değeri.

*n*<br/>
Bessel fonksiyonunun sonda sırası.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri *x'in*Bessel işlevini döndürür. *x* **_y0**negatif ise , **_y1**, veya **_yn** işlevleri, rutin **EDOM** **için errno** ayarlar , **stderr**bir **_DOMAIN** hata iletisi yazdırır , ve **_HUGE_VAL**döndürür. **_matherr**kullanarak hata işlemeyi değiştirebilirsiniz.

## <a name="remarks"></a>Açıklamalar

**_j0**, **_j1**ve **_jn** yordamları ilk tür Bessel işlevleri döndürün: siparişler 0, 1 ve n, sırasıyla.

|Girdi|SEH Özel Durumu|Matherr İstisnası|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|**Geçersiz**|**_DOMAIN**|

**_y0**, **_y1**ve **_yn** yordamları ikinci tür Bessel işlevleri ni döndürer: sırasıyla 0, 1 ve n siparişleri.

|Girdi|SEH Özel Durumu|Matherr İstisnası|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|**Geçersiz**|**_DOMAIN**|
|± 0|**SIFIR BÖL**|**_SING**|
|&#124;x&#124; < 0,0|**Geçersiz**|**_DOMAIN**|

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_j0**, **_j1**, **_jn**, **_y0**, **_y1**, **_yn**|\<cmath> (C++), \<math.h> (C, C++)|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_bessel1.c
#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.387;
   int n = 3, c;

   printf( "Bessel functions for x = %f:\n", x );
   printf( "   Kind   Order  Function     Result\n\n" );
   printf( "   First  0      _j0( x )     %f\n", _j0( x ) );
   printf( "   First  1      _j1( x )     %f\n", _j1( x ) );
   for( c = 2; c < 5; c++ )
      printf( "   First  %d      _jn( %d, x )  %f\n", c, c, _jn( c, x ) );
   printf( "   Second 0      _y0( x )     %f\n", _y0( x ) );
   printf( "   Second 1      _y1( x )     %f\n", _y1( x ) );
   for( c = 2; c < 5; c++ )
      printf( "   Second %d      _yn( %d, x )  %f\n", c, c, _yn( c, x ) );
}
```

```Output
Bessel functions for x = 2.387000:
   Kind   Order  Function     Result

   First  0      _j0( x )     0.009288
   First  1      _j1( x )     0.522941
   First  2      _jn( 2, x )  0.428870
   First  3      _jn( 3, x )  0.195734
   First  4      _jn( 4, x )  0.063131
   Second 0      _y0( x )     0.511681
   Second 1      _y1( x )     0.094374
   Second 2      _yn( 2, x )  -0.432608
   Second 3      _yn( 3, x )  -0.819314
   Second 4      _yn( 4, x )  -1.626833
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_matherr](matherr.md)<br/>
