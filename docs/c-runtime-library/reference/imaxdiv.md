---
title: imaxdiv | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- imaxdiv function
ms.assetid: 7d90126f-fdc2-4986-9cdf-94e4c9123d26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db2a57e9b91672d39fbce5eaee061043604a0998
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32399702"
---
# <a name="imaxdiv"></a>imaxdiv

Sayının ve herhangi bir boyuttaki iki tamsayı değerleri kalanını tek bir işlem olarak hesaplar.

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
Payda değeri.

## <a name="return-value"></a>Dönüş Değeri

**imaxdiv** türünde bir bağımsız değişkenlerle çağrıldı [intmax_t](../../c-runtime-library/standard-types.md) türü yapısını döndürür [imaxdiv_t](../../c-runtime-library/standard-types.md) sayının ve kalanı oluşur.

## <a name="remarks"></a>Açıklamalar

**İmaxdiv** işlev böler *numarası* tarafından *denom* ve böylece sayının ve kalanı hesaplar. **İmaxdiv_t** yapısı içeren sayının **intmax_t** **quot**ve kalan **intmax_t** **rem**. Sayının işaretini, matematiksel sayının aynıdır. Mutlak değerini matematiksel sayının mutlak değerini değerinden en büyük tamsayıdır. Paydanın 0 ise, program bir hata iletisi ile sona erer.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**imaxdiv**|\<inttypes.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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

Yerleşik ve komut satırı parametreleri ile adlı `9460730470000000 8766`, bu çıkış kodu oluşturur:

```Output
The call to imaxdiv(9460730470000000, 8766)
results in a quotient of 1079252848505, and a remainder of 5170
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[div](div.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
