---
title: _cabs
ms.date: 11/04/2016
api_name:
- _cabs
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _cabs
helpviewer_keywords:
- cabs function
- absolute values
- _cabs function
- calculating absolute values
ms.assetid: fea292ee-1a39-4a0a-b416-4a189346ff26
ms.openlocfilehash: ba24b10fb267c9b54ec4944704de988128b4b419
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443056"
---
# <a name="_cabs"></a>_cabs

Karmaşık bir sayının mutlak değerini hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double _cabs(
   struct _complex z
);
```

### <a name="parameters"></a>Parametreler

*kadar*<br/>
Karmaşık sayı.

## <a name="return-value"></a>Dönüş Değeri

**_cabs** , başarılı olursa bağımsız değişkeninin mutlak değerini döndürür. Taşma üzerinde, **_cabs** **HUGE_VAL** döndürür ve **errno** , **ERANGE**olarak ayarlar. Hata işlemeyi [_matherr](matherr.md)ile değiştirebilirsiniz.

## <a name="remarks"></a>Açıklamalar

**_Cabs** işlevi, bir karmaşık sayının mutlak değerini hesaplar, bu, [_complex](../../c-runtime-library/standard-types.md)türünde bir yapı olmalıdır. *Z* yapısı gerçek bir bileşen *x* ve sanal bileşen *y*' den oluşur. **_Cabs** çağrısı, `sqrt( z.x * z.x + z.y * z.y )`ifade ile eşdeğer bir değer üretir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_cabs**|\<Math. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_cabs.c
// Using _cabs, this program calculates
// the absolute value of a complex number.

#include <math.h>
#include <stdio.h>

int main( void )
{
   struct _complex number = { 3.0, 4.0 };
   double d;

   d = _cabs( number );
   printf( "The absolute value of %f + %fi is %f\n",
           number.x, number.y, d );
}
```

```Output
The absolute value of 3.000000 + 4.000000i is 5.000000
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)