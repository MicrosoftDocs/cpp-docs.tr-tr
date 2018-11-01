---
title: imaxdiv
ms.date: 04/05/2018
apiname:
- imaxdiv
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
- imaxdiv
helpviewer_keywords:
- imaxdiv function
ms.assetid: 7d90126f-fdc2-4986-9cdf-94e4c9123d26
ms.openlocfilehash: 23067b2028fc11193fae707e25165fb0ce754515
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434464"
---
# <a name="imaxdiv"></a>imaxdiv

Sayının ve herhangi boyuttaki iki tamsayı değerinin kalanını tek bir işlem olarak hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
imaxdiv_t imaxdiv(
   intmax_t numer,
   intmax_t denom
);
```

### <a name="parameters"></a>Parametreler

*numarası*<br/>
Pay.

*denom*<br/>
Payda.

## <a name="return-value"></a>Dönüş Değeri

**imaxdiv** türünde bağımsız değişkenlerle çağrılır [intmax_t](../../c-runtime-library/standard-types.md) türünden bir yapıyı döndürür [imaxdiv_t](../../c-runtime-library/standard-types.md) bölümü ve kalanı içerir.

## <a name="remarks"></a>Açıklamalar

**İmaxdiv** işlev böler *numarası* tarafından *denom* ve böylece bölümü ve kalanı hesaplar. **İmaxdiv_t** yapısı kalanını içerir **intmax_t** **quot**ve kalanı **intmax_t** **rem**. Bölüm işareti matematiksel olarak aynıdır. Mutlak değeri matematiksel sayının mutlak değerinden daha küçük olan en büyük tamsayıdır. Payda 0 ise, program bir hata iletisi ile sona erer.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**imaxdiv**|\<inttypes.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_imaxdiv.c
// Build using: cl /W3 /Tc crt_imaxdiv.c
// This example takes two integers as command-line
// arguments and calls imaxdiv to divide the first
// argument by the second, then displays the results.

#include <stdio.h>
#include <stdlib.h>
#include <inttypes.h>

int main(int argc, char *argv[])
{
   intmax_t x,y;
   imaxdiv_t div_result;

   x = atoll(argv[1]);
   y = atoll(argv[2]);

   printf("The call to imaxdiv(%lld, %lld)\n", x, y);
   div_result = imaxdiv(x, y);
   printf("results in a quotient of %lld, and a remainder of %lld\n\n",
          div_result.quot, div_result.rem);
}
```

Yerleşik ve ardından komut satırı parametreleriyle çağrıldığında, `9460730470000000 8766`, kod aşağıdaki çıkışı üretir:

```Output
The call to imaxdiv(9460730470000000, 8766)
results in a quotient of 1079252848505, and a remainder of 5170
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[div](div.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
