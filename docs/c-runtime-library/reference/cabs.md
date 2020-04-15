---
title: _cabs
ms.date: 4/2/2020
api_name:
- _cabs
- _o__cabs
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
- _cabs
helpviewer_keywords:
- cabs function
- absolute values
- _cabs function
- calculating absolute values
ms.assetid: fea292ee-1a39-4a0a-b416-4a189346ff26
ms.openlocfilehash: e77e1811cb6f002c06e514b5f737b8a92ea84282
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333685"
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

*Z*<br/>
Karmaşık sayı.

## <a name="return-value"></a>Dönüş Değeri

**_cabs** başarılı olursa bağımsız değişkeninin mutlak değerini döndürür. Taşma, **_cabs** **HUGE_VAL** döndürür ve **ERANGE** **için errno** ayarlar. [hata işlemeyi _matherr](matherr.md)ile değiştirebilirsiniz.

## <a name="remarks"></a>Açıklamalar

**_cabs** işlevi, [karmaşık](../../c-runtime-library/standard-types.md)bir sayının mutlak değerini hesaplar, bu da _complex. Yapı *z* gerçek bir bileşen *x* ve hayali bir bileşen *y*oluşur. **_cabs** için yapılan bir çağrı, ifadenin `sqrt( z.x * z.x + z.y * z.y )`değerine eşdeğer bir değer üretir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_cabs**|\<math.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
