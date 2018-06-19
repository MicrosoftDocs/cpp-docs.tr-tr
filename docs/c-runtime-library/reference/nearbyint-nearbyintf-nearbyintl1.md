---
title: nearbyint, nearbyintf, nearbyintl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2362a68bf73a370f2fdf8eaa5ecb18b0a08bfaad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403241"
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint, nearbyintf, nearbyintl

Belirtilen kayan nokta değeri tamsayıya yuvarlar ve bu değer bir kayan nokta biçiminde döndürür.

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

Başarılı olursa, döndürür *x*, tarafından bildirilen geçerli yuvarlama biçimini kullanarak en yakın tamsayıya yuvarlanır [fegetround](fegetround-fesetround2.md). Aksi takdirde işlevi aşağıdaki değerlerden birini döndürebilir:

|Sorun|Döndür|
|-----------|------------|
|*x* ±INFINITY =|Değiştirilmemiş ±INFINITY|
|*x* ±0 =|değiştirilmemiş ±0|
|*x* NaN =|NaN|

Hataları bildirilmedi aracılığıyla [_matherr](matherr.md); özellikle, bu işlev herhangi bildirmez **FE_INEXACT** özel durumları.

## <a name="remarks"></a>Açıklamalar

Bu işlev arasındaki birincil fark ve [azdır](rint-rintf-rintl.md) olduğundan bu işlevi kesin olmayan kayan nokta özel durumu oluşturmaz.

En fazla kayan nokta değerlerine tam tamsayılar olduğundan, bu işlev hiçbir zaman tek başına taşması; Bunun yerine, çıkışı işlevi sürümüne bağlı olarak, kullandığınız dönüş değeri taşma.

C++ verir aşırı yüklemesi, aşırı çağırması **nearbyint** alın ve dönüş **float** veya **uzun** **çift** parametreleri. Bir C programı **nearbyint** her zaman iki çift değerlerini alır ve bir double değeri döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgi|
|--------------|--------------|------------------|
|**nearbyint**, **nearbyintf**, **nearbyintl**|\<Math.h >|\<cmath > veya \<math.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[Matematik ve kayan nokta desteği](../floating-point-support.md)<br/>
