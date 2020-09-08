---
title: abs, labs, llabs, _abs64
description: ABS, Labs, LLabs ve _abs64; için API başvurusu bir değerin mutlak değerini hesaplar.
ms.date: 04/05/2018
api_name:
- abs
- _abs64
- labs
- llabs
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
- api-ms-win-crt-utility-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- stdlib/_abs64
- math/abs
- _abs64
- abs
- labs
- math/labs
- llabs
- math/llabs
- cmath/abs
helpviewer_keywords:
- absolute values
- abs function
- abs64 function
- _abs64 function
- calculating absolute values
ms.assetid: 60f789d1-4a1e-49f5-9e4e-0bdb277ea26a
ms.openlocfilehash: 4527950e4f5577b9285d12309742accb64b9a24a
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556755"
---
# <a name="abs-labs-llabs-_abs64"></a>abs, labs, llabs, _abs64

Bağımsız değişkenin mutlak değerini hesaplar.

## <a name="syntax"></a>Söz dizimi

```C
int abs( int n );
long labs( long n );
long long llabs( long long n );
__int64 _abs64( __int64 n );
```

```cpp
long abs( long n );   // C++ only
long long abs( long long n );   // C++ only
double abs( double n );   // C++ only
long double abs( long double n );   // C++ only
float abs( float n );   // C++ only
```

### <a name="parameters"></a>Parametreler

*No*\
Sayısal değer.

## <a name="return-value"></a>Dönüş Değeri

**ABS**, **Labs**, **LLabs**ve **_abs64** işlevleri *n*parametresinin mutlak değerini döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden,,,, **abs** **`long`** **`long long`** **`float`** **`double`** ve değerlerini **`long double`** alan ve döndüren ABS aşırı yüklerini çağırabilirsiniz. Bu aşırı yüklemeler \<cmath> üst bilgide tanımlanmıştır. C programında, **ABS** her zaman alır ve döndürür **`int`** .

**Microsoft 'a özgü**: herhangi bir integral türü kullanılarak gösterilebilen negatif tamsayılar aralığı, bu türü kullanarak temsil edilebilir pozitif tamsayılar aralığından daha büyükse, bu işlevlere dönüştürülemeyen bir bağımsız değişken sağlamak mümkündür. Bağımsız değişkenin mutlak değeri, dönüş türü tarafından temsil edilemez, **ABS** işlevleri bağımsız değişken değerini değiştirmeden döndürür. Özellikle, döndürür, döndürür, döndürür `abs(INT_MIN)` `INT_MIN` `labs(LONG_MIN)` `LONG_MIN` `llabs(LLONG_MIN)` `LLONG_MIN` ve `_abs64(_I64_MIN)` döndürür `_I64_MIN` . Bu, **ABS** işlevlerinin pozitif bir değeri güvence altına almak için kullanılamayacağı anlamına gelir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgisi|Gerekli C++ üstbilgisi|
|-------------|-----------------------|---------------------------|
|**ABS**, **Labs**, **LLabs**|\<math.h> veya \<stdlib.h>|\<cmath>, \<cstdlib> , \<stdlib.h> veya \<math.h>|
|**_abs64**|\<stdlib.h>|\<cstdlib> veya \<stdlib.h>|

C++ ' da aşırı yüklenmiş **ABS** sürümlerini kullanmak için üstbilgiyi dahil etmeniz gerekir \<cmath> .

## <a name="example"></a>Örnek

Bu program, birkaç sayının mutlak değerlerini hesaplar ve görüntüler.

```C
// crt_abs.c
// Build: cl /W3 /TC crt_abs.c
// This program demonstrates the use of the abs function
// by computing and displaying the absolute values of
// several numbers.

#include <stdio.h>
#include <math.h>
#include <stdlib.h>
#include <limits.h>

int main( void )
{
    int ix = -4;
    long lx = -41567L;
    long long llx = -9876543210LL;
    __int64 wx = -1;

    // absolute 32 bit integer value
    printf_s("The absolute value of %d is %d\n", ix, abs(ix));

    // absolute long integer value
    printf_s("The absolute value of %ld is %ld\n", lx, labs(lx));

    // absolute long long integer value
    printf_s("The absolute value of %lld is %lld\n", llx, llabs(llx));

    // absolute 64 bit integer value
    printf_s("The absolute value of 0x%.16I64x is 0x%.16I64x\n", wx,
        _abs64(wx));

    // Integer error cases:
    printf_s("Microsoft implementation-specific results:\n");
    printf_s(" abs(INT_MIN) returns %d\n", abs(INT_MIN));
    printf_s(" labs(LONG_MIN) returns %ld\n", labs(LONG_MIN));
    printf_s(" llabs(LLONG_MIN) returns %lld\n", llabs(LLONG_MIN));
    printf_s(" _abs64(_I64_MIN) returns 0x%.16I64x\n", _abs64(_I64_MIN));
}
```

```Output
The absolute value of -4 is 4
The absolute value of -41567 is 41567
The absolute value of -9876543210 is 9876543210
The absolute value of 0xffffffffffffffff is 0x0000000000000001
Microsoft implementation-specific results:
abs(INT_MIN) returns -2147483648
labs(LONG_MIN) returns -2147483648
llabs(LLONG_MIN) returns -9223372036854775808
_abs64(_I64_MIN) returns 0x8000000000000000
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_cabs](cabs.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
[imaxabs](imaxabs.md)
