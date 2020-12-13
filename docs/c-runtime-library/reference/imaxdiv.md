---
description: 'Daha fazla bilgi edinin: ımaxdıv'
title: imaxdiv
ms.date: 04/05/2018
api_name:
- imaxdiv
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
- imaxdiv
helpviewer_keywords:
- imaxdiv function
ms.assetid: 7d90126f-fdc2-4986-9cdf-94e4c9123d26
ms.openlocfilehash: 3e1f417c1fb45b452b3cd07560bfec68d21fd1a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332768"
---
# <a name="imaxdiv"></a>imaxdiv

Her boyuttaki iki tamsayı değerinin tek bir işlem olarak bölümünü ve kalanını hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
imaxdiv_t imaxdiv(
   intmax_t numer,
   intmax_t denom
);
```

### <a name="parameters"></a>Parametreler

*numer*<br/>
Pay.

*denom*<br/>
Payda.

## <a name="return-value"></a>Dönüş Değeri

[intmax_t](../../c-runtime-library/standard-types.md) türündeki bağımsız değişkenlerle çağrılan **ımaxdiv** , bölüm ve geri kalanı içeren [imaxdiv_t](../../c-runtime-library/standard-types.md) türünde bir yapı döndürüyor.

## <a name="remarks"></a>Açıklamalar

**Imaxdiv** işlevi, *numer* ile Mase 'yi *böler ve bu* sayede bölümü ve kalanı hesaplar. **İmaxdiv_t** yapısı, bölüm, **intmax_t** **quot** ve geri kalanı **intmax_t** **REM**' u içerir. Bölüm işareti, matematik bölümü ile aynıdır. Mutlak değeri, matematik alanının mutlak değerinden daha küçük olan en büyük tamsayıdır. Payda 0 ise, program bir hata iletisiyle sonlanır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**imaxdiv**|\<inttypes.h>|

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

Oluşturulup komut satırı parametreleriyle birlikte çağrıldığında `9460730470000000 8766` , kod bu çıktıyı oluşturur:

```Output
The call to imaxdiv(9460730470000000, 8766)
results in a quotient of 1079252848505, and a remainder of 5170
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[div](div.md)<br/>
[ldiv, lldiv](./div.md)<br/>
