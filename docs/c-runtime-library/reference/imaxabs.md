---
title: imaxabs | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- imaxabs
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
- imaxabs
dev_langs:
- C++
helpviewer_keywords:
- imaxabs function
ms.assetid: de2566a3-1415-4e9a-91b5-7ac3a49ebf5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9476db108a4296811e1c88e820d12ddd24b1386
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="imaxabs"></a>imaxabs

Herhangi bir boyuttaki bir tamsayı mutlak değerini hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
intmax_t imaxabs(
   intmax_t n
);
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Tamsayı değeri.

## <a name="return-value"></a>Dönüş Değeri

**İmaxabs** işlevi bağımsız değişken mutlak değerini döndürür. Döndürülen hata yoktur.

> [!NOTE]
> Çünkü kullanarak temsil edilebilir negatif tamsayıların aralığını **intmax_t** aralığından daha büyük temsil edilebilir pozitif tamsayılar bağımsız değişken sağlamayı mümkündür **imaxabs** dönüştürülemiyor. Bağımsız değişken mutlak değerini başı gösterilemezse türü, davranışını **imaxabs** tanımlanmadı.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**imaxabs**|\<inttypes.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_imaxabs.c
// Build using: cl /W3 /Tc crt_imaxabs.c
// This example calls imaxabs to compute an
// absolute value, then displays the results.

#include <stdio.h>
#include <stdlib.h>
#include <inttypes.h>

int main(int argc, char *argv[])
{
   intmax_t x = LLONG_MIN + 2;

   printf("The absolute value of %lld is %lld\n", x, imaxabs(x));
}
```

```Output
The absolute value of -9223372036854775806 is 9223372036854775806
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
[_cabs](cabs.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
