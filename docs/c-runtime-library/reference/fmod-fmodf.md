---
title: fmod, fmodf, fmodl
ms.date: 4/2/2020
api_name:
- fmod
- fmodf
- fmodl
- _o_fmod
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
- fmod
- _fmodl
- fmodf
helpviewer_keywords:
- calculating floating-point remainders
- fmodf function
- fmodl function
- fmod function
- floating-point numbers, calculating remainders
ms.assetid: 6962d369-d11f-40b1-a6d7-6f67239f8a23
ms.openlocfilehash: 0cf25e2029f06c2e02a24ca84926e1a8b8f30159
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346550"
---
# <a name="fmod-fmodf-fmodl"></a>fmod, fmodf, fmodl

Kayan nokta geri kalanını hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double fmod(
   double x,
   double y
);
float fmod(
   float x,
   float y
);  // C++ only
long double fmod(
   long double x,
   long double y
);  // C++ only
float fmodf(
   float x,
   float y
);
long double fmodl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Parametreler

*x*, *y*<br/>
Kayan nokta değerleri.

## <a name="return-value"></a>Dönüş Değeri

**fmod** *x* / *y*kayan nokta geri kalanını döndürür. *y* değeri 0.0 ise, **fmod** sessiz bir NaN döndürür. **Printf** ailesi tarafından sessiz bir NaN'ın temsili hakkında bilgi için [printf bölümüne](printf-printf-l-wprintf-wprintf-l.md)bakın.

## <a name="remarks"></a>Açıklamalar

**Fmod** fonksiyonu *x* / *y* kayan nokta kalan *f* hesaplar gibi *x* = *i* \* *y* + *f*, nerede *i* bir tamsayı, *f* *x*ile aynı işareti vardır , ve *f* mutlak değeri *y*mutlak değeri daha azdır .

C++ aşırı yüklemeye izin verir, böylece **float** ve uzun **long** **çift** değerleri alan ve döndüren **aşırı fmod** yüklerini arayabilirsiniz. Bir C programında, **fmod** her zaman iki **çift** bağımsız değişken alır ve bir **çift**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fmod**, **fmodf**, **fmodl**|\<math.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_fmod.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;

   z = fmod( w, x );
   printf( "The remainder of %.2f / %.2f is %f\n", w, x, z );
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[_CIfmod](../../c-runtime-library/cifmod.md)<br/>
