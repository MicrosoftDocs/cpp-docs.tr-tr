---
title: FMOD, fmodf, fmodl
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: a6fcb7feeae72ff15d7b1ed0d55c5abbb408135a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914964"
---
# <a name="fmod-fmodf-fmodl"></a>FMOD, fmodf, fmodl

Kayan nokta kalanını hesaplar.

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

**fmod** , *x* / *y*'nin kayan nokta kalanını döndürür. *Y* değeri 0,0 ise, **fmod** sessiz bir NaN döndürür. **Printf** ailesi tarafından sessiz bir NaN 'ın temsili hakkında bilgi için bkz. [printf](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Açıklamalar

**Fmod** işlevi *, x* / *y* \* *i* *y* *x* =  + *f*'nin kayan *nokta geri kalanını* hesaplar *, burada bir tamsayı,* *f* ise *x*ile aynı işarete sahiptir ve *f* 'nin mutlak değeri *y*'nin mutlak değerinden küçüktür.

C++ aşırı yüklemeye izin verdiğinden, **float** ve **Long** **Double** değerleri alıp döndüren **fmod** 'un aşırı yüklerini çağırabilirsiniz. C programında **fmod** her zaman iki **çift** bağımsız değişken alır ve bir **Double**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fmod**, **fmodf**, **fmodl**|\<Math. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
