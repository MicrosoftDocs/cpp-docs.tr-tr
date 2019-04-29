---
title: div, ldiv, lldiv
ms.date: 04/05/2018
apiname:
- div
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- div
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
ms.openlocfilehash: 0ee1b3b6a5d7b15470ffe1e667b4077d1f9581e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339266"
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

*numarası*<br/>
Pay.

*denom*<br/>
Payda.

## <a name="return-value"></a>Dönüş Değeri

**div** türünde bağımsız değişkenler kullanarak çağrılır **int** türünden bir yapıyı döndürür **div_t**, bölümü ve kalanı içerir. Dönüş değeri türü bağımsız değişkenler ile **uzun** olduğu **ldiv_t**ve dönüş değeri türü bağımsız değişkenler ile **uzun** **uzun** olan**lldiv_t**. **div_t**, **ldiv_t**, ve **lldiv_t** tanımlanan \<stdlib.h >.

## <a name="remarks"></a>Açıklamalar

**Div** işlev böler *numarası* tarafından *denom* ve böylece bölümü ve kalanı hesaplar. [Div_t](../../c-runtime-library/standard-types.md) yapısı kalanını içerir **quot**ve kalanı **rem**. Bölüm işareti matematiksel olarak aynıdır. Mutlak değeri matematiksel sayının mutlak değerinden daha küçük olan en büyük tamsayıdır. Payda 0 ise, program bir hata iletisi ile sona erer.

Aşırı Yüklemeleri **div** türünde bağımsız değişkenler ele **uzun** veya **uzun** **uzun** yalnızca C++ kodu için mevcuttur. Dönüş türleri [ldiv_t](../../c-runtime-library/standard-types.md) ve [lldiv_t](../../c-runtime-library/standard-types.md) üyeleri içeren **quot** ve **rem**, üyeleriileaynıanlamasahiptir**div_t**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**div**, **ldiv**, **lldiv**|\<stdlib.h >|

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

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
