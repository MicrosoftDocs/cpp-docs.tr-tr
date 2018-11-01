---
title: trunc, truncf, truncl
ms.date: 04/05/2018
apiname:
- trunc
- truncf
- truncl
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
ms.openlocfilehash: 6e023b9d894ea1b40a0e056e73b7c32f1e3cbed7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519866"
---
# <a name="trunc-truncf-truncl"></a>trunc, truncf, truncl

Belirtilen kayan nokta değerine eşit veya daha az olan en yakın tamsayıya belirler.

## <a name="syntax"></a>Sözdizimi

```C
double trunc( double x );
float trunc( float x ); //C++ only
long double truncl( long double x );
```

```cpp
long double trunc( long double x ); //C++ only
float trunc( float x ); //C++ only
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Kesmek için değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bir tamsayı değerini döndürür *x*, yuvarlak sıfır.

Aksi takdirde, aşağıdakilerden birini döndürebilir:

|Sorun|döndürülecek|
|-----------|------------|
|*x* ±INFINITY =|x|
|*x* ±0 =|x|
|*x* NaN =|NaN|

Hatalar rapor, belirtilen [_matherr](matherr.md).

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **trunc** alan ve getiren **float** ve **uzun** **çift** türleri. C programında **trunc** her zaman alan ve döndüren bir **çift**.

En büyük kayan nokta değerlerine tam tam sayılar olduğundan, bu işlev, kendi taşma değil. Bununla birlikte, işlev bir tamsayı türü bir değer döndürerek taşma neden olabilir.

Aynı zamanda örtük olarak kayan nokta için integral dönüştürerek aşağı YUVARLA; Ancak, bunu yapmanız bu nedenle hedef türünde depolanan değerleri sınırlıdır.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**trunc**, **truncf**, **truncl**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[round, roundf, roundl](round-roundf-roundl.md)<br/>
