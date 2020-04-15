---
title: nearbyint, nearbyintf, nearbyintl
ms.date: 4/2/2020
api_name:
- nearbyint
- nearbyintf
- nearbyintl
- _o_nearbyint
- _o_nearbyintf
- _o_nearbyintl
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
- nearbyint
- nearbyintf
- nearbyintl
- math/nearbyint
- math/narbyintf
- math/narbyintl
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
ms.openlocfilehash: 92e3a744ef8069d45733c06b7a2681905c3eab55
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338582"
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint, nearbyintf, nearbyintl

Belirtilen kayan nokta değerini bir tamsayıya yuvarlar ve bu değeri kayan nokta biçiminde döndürür.

## <a name="syntax"></a>Sözdizimi

```C
double nearbyint( double x );
float nearbyintf( float x );
long double nearbyintl( long double x );
```

```cpp
float nearbyint( float x ); //C++ only
long double nearbyint( long double x ); //C++ only
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Yuvarlanacak değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, [fegetround](fegetround-fesetround2.md)tarafından bildirilen geçerli yuvarlama biçimini kullanarak, en yakın tümseci yuvarlatılmış *x*döndürür. Aksi takdirde, işlev aşağıdaki değerlerden birini döndürebilir:

|Sorun|Dönüş|
|-----------|------------|
|*x* = ±SONSUZLUK|±INFINITY, değiştirilmemiş|
|*x* = ±0|±0, değiştirilmemiş|
|*x* = NaN|NaN|

Hatalar [_matherr](matherr.md)yoluyla bildirilmemiştir; özellikle, bu işlev herhangi **bir FE_INEXACT** özel durum bildirmez.

## <a name="remarks"></a>Açıklamalar

Bu işlev ve [rint](rint-rintf-rintl.md) arasındaki birincil fark, bu işlevin tam olarak kayan nokta özel durum yükseltmemesidir.

Maksimum kayan nokta değerleri tam tamsayılar olduğundan, bu işlev asla tek başına taşmaz; bunun yerine, çıktı kullandığınız işlevin hangi sürümüne bağlı olarak iade değerini taşabilir.

C++ aşırı yüklemeye izin verir, böylece **float** veya **uzun** **çift** parametreleri alıp geri döndüren aşırı yakın **tarak** ları arayabilirsiniz. C programında, **yakındaki her** zaman iki çift değer alır ve bir çift değer döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgi|C++ üstbilgi|
|--------------|--------------|------------------|
|**nearbyint**, **nearbyintf**, **nearbyintl**|\<math.h>|\<cmath> \<veya math.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[Matematik ve kayan nokta desteği](../floating-point-support.md)<br/>
