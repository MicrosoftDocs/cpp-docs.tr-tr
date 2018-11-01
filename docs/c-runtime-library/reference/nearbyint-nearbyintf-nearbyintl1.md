---
title: nearbyint, nearbyintf, nearbyintl
ms.date: 04/05/2018
apiname:
- nearbyint
- nearbyintf
- nerabyintl
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 4a36bddb28db9fb4c5809432dfaef9ca3ece4328
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668318"
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint, nearbyintf, nearbyintl

Belirtilen kayan nokta değeri bir tamsayıya yuvarlar ve bu değer bir kayan nokta biçiminde döndürür.

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

*x*<br/>
Yuvarlanacak değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa döndürür *x*, geçerli yuvarlama biçimi tarafından raporlandığı şekilde kullanarak en yakın tamsayıya yuvarlanır [fegetround](fegetround-fesetround2.md). Aksi halde, işlev aşağıdaki değerlerden birini döndürebilir:

|Sorun|döndürülecek|
|-----------|------------|
|*x* ±INFINITY =|±INFINITY, değiştirilmemiş|
|*x* ±0 =|±0, değiştirilmemiş|
|*x* NaN =|NaN|

Hataları aracılığıyla bildirilmez [_matherr](matherr.md); özellikle, bu işlev herhangi raporlamaz **FE_INEXACT** özel durumlar.

## <a name="remarks"></a>Açıklamalar

Bu işlev arasındaki birincil fark ve [azdır](rint-rintf-rintl.md) olduğundan bu işlevi kesin olmayan kayan nokta özel durum oluşturmaz.

En fazla kayan nokta değerlerini tam tam sayılar olduğundan, bu işlev hiçbir zaman kendisi tarafından overflow; Bunun yerine, çıkış işlevi sürümüne bağlı olarak kullanmanız gereken dönüş değeri taşması.

C++ sağlar aşırı yüklemesi, aşırı yüklemesini çağırabilirsiniz **nearbyint** alan ve getiren **float** veya **uzun** **çift** parametreleri. C programında **nearbyint** her zaman iki çift değer alır ve bir çift değer döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**nearbyint**, **nearbyintf**, **nearbyintl**|\<Math.h >|\<cmath > veya \<math.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[Matematik ve kayan nokta desteği](../floating-point-support.md)<br/>
