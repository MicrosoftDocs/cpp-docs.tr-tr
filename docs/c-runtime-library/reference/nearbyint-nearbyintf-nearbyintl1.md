---
title: nearbyint, nearbyintf, nearbyintl
ms.date: 04/05/2018
api_name:
- nearbyint
- nearbyintf
- nearbyintl
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
ms.openlocfilehash: cd0a7d00c5019dd1e483d555df6db8d9770e61c1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951401"
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint, nearbyintf, nearbyintl

Belirtilen kayan nokta değerini bir tamsayıya yuvarlar ve bu değeri kayan noktalı bir biçimde döndürür.

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

Başarılı olursa, [fegetround](fegetround-fesetround2.md)tarafından bildirilen geçerli yuvarlama biçimini kullanarak *x*döndürür ve en yakın tamsayıya yuvarlanır. Aksi takdirde, işlev aşağıdaki değerlerden birini döndürebilir:

|Sorun|döndürülmesini|
|-----------|------------|
|*x* = ± Infinity|± INFINITY, değiştirilmemiş|
|*x* = ±0|± 0, değiştirilmemiş|
|*x* = Nan|NaN|

Hatalar [_matherr](matherr.md); aracılığıyla bildirilmedi Özellikle, bu işlev **FE_INEXACT** özel durumlarını raporlamaz.

## <a name="remarks"></a>Açıklamalar

Bu işlev ve [rint](rint-rintf-rintl.md) arasındaki birincil fark, bu işlevin kayan nokta özel durumunu yükseltmediğinden emin değildir.

En büyük kayan nokta değerleri tam tamsayılar olduğundan, bu işlev kendi kendine hiçbir şekilde taşmayacaktır; Bunun yerine, çıktı, kullandığınız işlevin sürümüne bağlı olarak dönüş değerini taşrabilir.

C++aşırı yüklemeye izin verir, bu sayede **float** veya **Long** **Double** parametreleri alan ve **döndüren bir daha** fazla. C **programında, her** zaman iki çift değer alır ve bir Double değeri döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|bir **tamsayı**, bir tam açıklama, bir **intf**, **yaklaştığında**|\<Math. h >|\<cmath > veya \<Math. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[Matematik ve kayan nokta desteği](../floating-point-support.md)<br/>
