---
title: trunc, truncf, truncl
ms.date: 04/05/2018
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
ms.openlocfilehash: b0c615c91e562fa45f791d8cc20f39a830013aeb
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70946001"
---
# <a name="trunc-truncf-truncl"></a>trunc, truncf, truncl

Belirtilen kayan noktalı değerden küçük veya buna eşit en yakın tamsayıyı belirler.

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
Kesyapılacak değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, sıfıra yuvarlayarak *x*tamsayı değerini döndürür.

Aksi takdirde, aşağıdakilerden birini döndürebilir:

|Sorun|döndürülmesini|
|-----------|------------|
|*x* = ± Infinity|x|
|*x* =  ±0|x|
|*x* = Nan|NaN|

Hatalar [_matherr](matherr.md)içinde belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

Aşırı C++ yüklemeye izin verdiğinden, **float** ve **Long** **Double** türlerini alıp döndüren **TRUNC** 'nin aşırı yüklerini çağırabilirsiniz. C programında, **TRUNC** her zaman bir **Double**alır ve döndürür.

En büyük kayan nokta değerleri tam tamsayılar olduğundan, bu işlev kendi kendine taşmaz. Ancak, bir değeri tamsayı türüne döndürerek işlevin taşmasına neden olabilirsiniz.

Kayan noktadan tam sayıya örtülü olarak dönüştürme ile de aşağı doğru dönüştürebilirsiniz; Ancak, bunun yapılması hedef türünde depolanabilecek değerlerle sınırlıdır.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|**TRUNC**, **truncf**, **truncl**|\<Math. h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[round, roundf, roundl](round-roundf-roundl.md)<br/>
