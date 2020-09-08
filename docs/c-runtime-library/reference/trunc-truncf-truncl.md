---
title: trunc, truncf, truncl
description: TRUNC, truncf, truncl; için API başvurusu belirtilen kayan nokta değerinden küçük veya buna eşit en yakın tamsayıyı belirleyen.
ms.date: 9/1/2020
api_name:
- trunc
- truncf
- truncl
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
- trunc
- truncf
- truncl
- math/trunc
- math/truncf
- math/truncl
helpviewer_keywords:
- trunc function
- truncf function
- truncl function
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
ms.openlocfilehash: f1f2fde95bb944aa461bb95a9ad30fac204552b9
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556638"
---
# <a name="trunc-truncf-truncl"></a>trunc, truncf, truncl

Belirtilen kayan noktalı değerden küçük veya buna eşit en yakın tamsayıyı belirler.

## <a name="syntax"></a>Söz dizimi

```C
double trunc( double x );
long double truncl( long double x );
#define trunc(X) // Requires C11 or higher

long double trunc( long double x ); //C++ only
float trunc( float x ); //C++ only
```

### <a name="parameters"></a>Parametreler

*sayı*\
Kesyapılacak değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, sıfıra yuvarlayarak *x*tamsayı değerini döndürür.

Aksi takdirde, aşağıdakilerden birini döndürebilir:

|Sorun|Döndürülmesini|
|-----------|------------|
|*x* = ± Infinity|x|
|*x* = ± 0|x|
|*x* = Nan|NaN|

Hatalar [_matherr](matherr.md)belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, ve türlerini alıp döndüren **TRUNC** 'nin aşırı yüklerini çağırabilirsiniz **`float`** **`long double`** . C programında, \<tgmath.h> Bu işlevi çağırmak için makroyu kullanmadığınız müddetçe, **TRUNC** her zaman bir alır ve döndürür **`double`** .

\<tgmath.h> `trunc()` Makroyu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

En büyük kayan nokta değerleri tam tamsayılar olduğundan, bu işlev kendi kendine taşmaz. Ancak, bir değeri tamsayı türüne döndürerek işlevin taşmasına neden olabilirsiniz.

Kayan noktadan tam sayıya örtülü olarak dönüştürme ile de aşağı doğru dönüştürebilirsiniz; Ancak, bunun yapılması hedef türünde depolanabilecek değerlerle sınırlıdır.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**TRUNC**, **truncf**, **truncl**|\<math.h>|\<cmath>|
|**TRUNC** makrosu | \<tgmath.h> ||

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[round, roundf, roundl](round-roundf-roundl.md)<br/>
