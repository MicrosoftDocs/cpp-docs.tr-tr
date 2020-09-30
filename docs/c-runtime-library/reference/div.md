---
title: div, ldiv, lldiv
ms.date: 04/05/2018
api_name:
- div
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
- div
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
ms.openlocfilehash: e0c87ad44986363e871d68bccde757214f5e2c45
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509887"
---
# <a name="div-ldiv-lldiv"></a>div, ldiv, lldiv

Bölümü ve iki tamsayı değerinin kalanını hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
div_t div(
   int numer,
   int denom
);
ldiv_t ldiv(
   long numer,
   long denom
);
lldiv_t lldiv(
   long long numer,
   long long denom
);
```

```cpp
ldiv_t div(
   long numer,
   long denom
); /* C++ only */
lldiv_t div(
   long long numer,
   long long denom
); /* C++ only */
```

### <a name="parameters"></a>Parametreler

*numer*<br/>
Pay.

*denom*<br/>
Payda.

## <a name="return-value"></a>Dönüş Değeri

tür bağımsız değişkenleri kullanılarak çağrılan **div** , **`int`** bölüm ve geri kalanı içeren **div_t**türünde bir yapı döndürür. Türündeki bağımsız değişkenlerle birlikte dönüş değeri **`long`** **ldiv_t**, ve türündeki bağımsız değişkenlerle birlikte dönüş değeri **`long long`** **lldiv_t**. **div_t**, **ldiv_t**ve **lldiv_t** ' de tanımlanmıştır \<stdlib.h> .

## <a name="remarks"></a>Açıklamalar

**Div** işlevi, *numer* 'ı *denom* ile böler ve böylece bölümü ve kalanı hesaplar. [Div_t](../../c-runtime-library/standard-types.md) **yapısı, Bölüm**, **quot**ve geri kalanını içerir. Bölüm işareti, matematik bölümü ile aynıdır. Mutlak değeri, matematik alanının mutlak değerinden daha küçük olan en büyük tamsayıdır. Payda 0 ise, program bir hata iletisiyle sonlanır.

Or bağımsız değişkenlerini **div** alan **`long`** veya **`long long`** yalnızca C++ kodunda kullanılabilen div öğesinin aşırı yüklemeleri. [Ldiv_t](../../c-runtime-library/standard-types.md) ve [lldiv_t](../../c-runtime-library/standard-types.md) dönüş türleri, **div_t**üyeleriyle aynı anlamlara sahip olan **quot** ve **REM**üyelerini içerir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**div**, **ldiv**, **lldiv**|\<stdlib.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_div.c
// arguments: 876 13

// This example takes two integers as command-line
// arguments and displays the results of the integer
// division. This program accepts two arguments on the
// command line following the program name, then calls
// div to divide the first argument by the second.
// Finally, it prints the structure members quot and rem.
//

#include <stdlib.h>
#include <stdio.h>
#include <math.h>

int main( int argc, char *argv[] )
{
   int x,y;
   div_t div_result;

   x = atoi( argv[1] );
   y = atoi( argv[2] );

   printf( "x is %d, y is %d\n", x, y );
   div_result = div( x, y );
   printf( "The quotient is %d, and the remainder is %d\n",
           div_result.quot, div_result.rem );
}
```

```Output
x is 876, y is 13
The quotient is 67, and the remainder is 5
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv]()<br/>
[imaxdiv](imaxdiv.md)<br/>
