---
title: div, ldiv, lldiv
description: Microsoft C çalışma zamanı kitaplığı div, ldiv ve lldiv işlevleri, bölümü ve iki tamsayı değerinin kalanını hesaplar.
ms.date: 11/21/2020
api_name:
- div
- ldiv
- lldiv
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
- ldiv
- lldiv
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.openlocfilehash: d87b2e3a84e389be8b14970a3aa611bb288cbec8
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440286"
---
# <a name="div-ldiv-lldiv"></a>`div`, `ldiv`, `lldiv`

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

*`numer`*\
Pay.

*`denom`*\
Payda.

## <a name="return-value"></a>Dönüş Değeri

**`div`** türündeki bağımsız değişkenler kullanılarak çağrılan **`int`** `div_t` , bölümü ve kalanı içeren bir türü yapısını döndürür. Türünün bağımsız değişkenlerine sahip dönüş değeri, **`long`** `ldiv_t` ve türündeki bağımsız değişkenlerle birlikte dönüş değeridir **`long long`** `lldiv_t` . `div_t`, `ldiv_t` Ve `lldiv_t` türleri içinde tanımlanmıştır \<stdlib.h> .

## <a name="remarks"></a>Açıklamalar

**`div`** İşlevi, *`numer`* *`denom`* bölümü ve kalanı hesaplar ve hesaplar. [`div_t`](../../c-runtime-library/standard-types.md)Yapı bölümü, `quot` ve kalanını içerir `rem` . Bölüm işareti, matematik bölümü işaretiyle aynıdır. Mutlak değeri, matematik alanının mutlak değerinden daha küçük olan en büyük tamsayıdır. Payda 0 ise, program bir hata iletisiyle sonlanır.

**`div`** Bu tür bağımsız değişkenleri alan **`long`** veya **`long long`** yalnızca C++ kodunda kullanılabilen aşırı yüklemeleri. Dönüş türleri [`ldiv_t`](../../c-runtime-library/standard-types.md) ve üyelerini [`lldiv_t`](../../c-runtime-library/standard-types.md) içerir ve `quot` `rem` üyeleri ile aynı anlamlara sahiptir `div_t` .

## <a name="requirements"></a>Gereksinimler

| Yordam | Gerekli başlık |
|--|--|
| **`div`**, **`ldiv`**, **`lldiv`** | \<stdlib.h> |

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

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)\
[`imaxdiv`](imaxdiv.md)
