---
title: trunc, truncf, truncl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- trunc function
- truncf function
- truncl function
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67c179065a6b2c6fc10a4ba6ba87868c8306a2aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="trunc-truncf-truncl"></a>trunc, truncf, truncl

Küçük veya bu değere eşit belirtilen kayan nokta en yakın tamsayıya belirler.

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

Başarılı olursa, tamsayı değerini döndürür *x*, yuvarlak sıfır bulunun.

Aksi takdirde, aşağıdakilerden birini döndürebilir:

|Sorun|Döndür|
|-----------|------------|
|*x* ±INFINITY =|x|
|*x* ±0 =|x|
|*x* NaN =|NaN|

Hataları raporlanır belirtilmiş [_matherr](matherr.md).

## <a name="remarks"></a>Açıklamalar

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **trunc** alın ve dönüş **float** ve **uzun** **çift** türleri. Bir C programı **trunc** her zaman alan ve döndüren bir **çift**.

En büyük kayan nokta değerlerine tam tamsayılar olduğundan, bu işlev, kendi taşma değil. Ancak, işlevi tamsayı türde bir değer döndürerek taşmasına neden olabilir.

Ayrıca örtük olarak kayan nokta için tam sayı dönüştürerek yuvarlamak; Ancak, bunun nedenle hedef türü depolanan değerlerin sınırlıdır.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgi|
|--------------|--------------|------------------|
|**trunc**, **truncf**, **truncl**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[round, roundf, roundl](round-roundf-roundl.md)<br/>
