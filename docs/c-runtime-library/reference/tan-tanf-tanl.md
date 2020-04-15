---
title: tan, tanf, tanl
ms.date: 4/2/2020
api_name:
- tan
- tanf
- tanl
- _o_tan
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
- tan
- tanf
- _tanl
- tanl
helpviewer_keywords:
- tanl function
- _tanl function
- tan function
- calculating tangents
- tangent
- tanf function
- trigonometric functions
ms.assetid: 36cc0ce8-9c80-4653-b354-ddb3b378b6bd
ms.openlocfilehash: 73a519614f17b6a8f8b26b5eae2172c87ea7f817
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362638"
---
# <a name="tan-tanf-tanl"></a>tan, tanf, tanl

Teğeti hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double tan( double x );
float tanf( float x );
long double tanl( long double x );
```

```cpp
float tan( float x );  // C++ only
long double tan( long double x );  // C++ only
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Radyanlarda açı.

## <a name="return-value"></a>Döndürülen değer

**Tan** fonksiyonları *x*teğet döndürün. *X* 263'ten büyük veya eşitse veya -263'ten daha az veya eşitse, sonuçta bir önem kaybı oluşur.

|Girdi|SEH Özel Durumu|**Matherr** Özel durum|
|-----------|-------------------|-------------------------|
|± QNAN,IND|yok|_DOMAIN|
|± INF|**Geçersiz**|_DOMAIN|

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, **float** veya uzun **long** **çift** değerleri alan ve **döndüren** aşırı tan yüklerini arayabilirsiniz. C **programında, tan** her zaman alır ve **çift**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üstbilgi (C)|Gerekli üstbilgi (C++)|
|-------------|---------------------|-|
|**tan**, **tanf**, **tanl**|\<math.h>|\<cmath> \<veya math.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_tan.c
// This program displays the tangent of pi / 4
// Compile by using: cl crt_tan.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x;

   x = tan( pi / 4 );
   printf( "tan( %f ) = %f\n", pi/4, x );
}
```

```Output
tan( 0.785398 ) = 1.000000
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[asin, asinf, asinl](asin-asinf-asinl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[_CItan](../../c-runtime-library/citan.md)<br/>
