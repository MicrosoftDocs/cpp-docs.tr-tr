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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 898544f5b191eb68e0ed6f17d7c3c7df849e8d11
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216862"
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint, nearbyintf, nearbyintl

Belirtilen kayan nokta değerini bir tamsayıya yuvarlar ve bu değeri kayan noktalı bir biçimde döndürür.

## <a name="syntax"></a>Söz dizimi

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

Başarılı olursa, [fegetround](fegetround-fesetround2.md)tarafından bildirilen geçerli yuvarlama biçimini kullanarak *x*döndürür ve en yakın tamsayıya yuvarlanır. Aksi takdirde, işlev aşağıdaki değerlerden birini döndürebilir:

|Sorun|Döndürülmesini|
|-----------|------------|
|*x* = ± Infinity|± INFINITY, değiştirilmemiş|
|*x* = ± 0|± 0, değiştirilmemiş|
|*x* = Nan|NaN|

Hatalar [_matherr](matherr.md)ile raporlanmaz; Özellikle, bu işlev **FE_INEXACT** özel durum bildirmiyor.

## <a name="remarks"></a>Açıklamalar

Bu işlev ve [rint](rint-rintf-rintl.md) arasındaki birincil fark, bu işlevin kayan nokta özel durumunu yükseltmediğinden emin değildir.

En büyük kayan nokta değerleri tam tamsayılar olduğundan, bu işlev kendi kendine hiçbir şekilde taşmayacaktır; Bunun yerine, çıktı, kullandığınız işlevin sürümüne bağlı olarak dönüş değerini taşrabilir.

C++ aşırı yüklemeye izin verdiğinden **, bir** **`float`** veya parametresi alıp döndürür **`long double`** . C **programında, her** zaman iki çift değer alır ve bir Double değeri döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|bir **tamsayı**, bir tam açıklama, bir **intf**, **yaklaştığında**|\<math.h>|\<cmath> veya \<math.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[Matematik ve kayan nokta desteği](../floating-point-support.md)<br/>
