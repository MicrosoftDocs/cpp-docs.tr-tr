---
title: lgamma, lgammaf, lgammal
ms.date: 4/2/2020
api_name:
- lgamma
- lgammaf
- lgammal
- _o_lgamma
- _o_lgammaf
- _o_lgammal
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
- lgamma
- lgammaf
- lgammal
- math/lgamma
- math/lgammaf
- math/lgammal
helpviewer_keywords:
- lgamma function
- lgammal function
- lgammaf function
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
ms.openlocfilehash: d751a3487db1d7c0135d4a1ae87cb84d374825fa
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218656"
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma, lgammaf, lgammal

Belirtilen değerin gama işlevinin mutlak logaritmasına ilişkin doğal logaritmayı belirler.

## <a name="syntax"></a>Söz dizimi

```C
double lgamma( double x );
float lgammaf( float x );
long double lgammal( long double x );
```

```cpp
float lgamma( float x ); //C++ only
long double lgamma( long double x ); //C++ only
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Hesaplama değeri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, *x*'in gama işlevinin mutlak logaritmasını döndürün.

|Sorun|Döndürülmesini|
|-----------|------------|
|*x* = Nan|NaN|
|*x* = ± 0|+ SONSUZLUK|
|*x*= negatif tamsayı|+ SONSUZLUK|
|± INFINITY|+ SONSUZLUK|
|direk hatası|+ HUGE_VAL, + HUGE_VALF veya + HUGE_VALL|
|taşma aralığı hatası|± HUGE_VAL, ± HUGE_VALF veya ± HUGE_VALL|

Hatalar [_matherr](matherr.md)belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, ve türlerini alıp döndüren **lgamma** aşırı yüklerini çağırabilirsiniz **`float`** **`long double`** . C programında, **lgama** her zaman alır ve döndürür **`double`** .

X bir Rational Number ise, bu işlev (x-1) faktöriyelini logaritmasını döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**lgamma**, **lgamaf**, **lgammal**|\<math.h>|\<cmath>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[tgamma, tgammaf, tgammal](tgamma-tgammaf-tgammal.md)<br/>
