---
title: exp2, exp2f, exp2l | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- exp2
- exp2f
- exp2l
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
- exp2
- math/exp2
- exp2f
- math/exp2f
- exp2l
- math/exp2l
dev_langs:
- C++
helpviewer_keywords:
- exp2 function
- exp2f function
- exp2l function
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aea847d367200635c8fecbd694f8a50be859b3ea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396728"
---
# <a name="exp2-exp2f-exp2l"></a>exp2, exp2f, exp2l

Belirtilen değere yükseltilmiş 2 hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double exp2(
   double x
);

float exp2(
   float x
);  // C++ only

long double exp2(
   long double x
); // C++ only

float exp2f(
   float x
);

long double exp2l(
   long double x
);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Üs değeri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, temel 2 üs döndürür *x*, diğer bir deyişle, 2<sup>x</sup>. Aksi takdirde, aşağıdaki değerlerden birini döndürür:

|Sorun|Döndür|
|-----------|------------|
|*x* ±0 =|1.|
|*x* = - SONSUZ|+0|
|*x* = + SONSUZ|+ SONSUZ|
|*x* NaN =|NaN|
|taşma aralık hatası|+ HUGE_VAL + HUGE_VALF, veya + HUGE_VALL|
|Underflow aralık hatası|Yuvarlama sonra doğru sonucu|

Hataları raporlanır belirtilmiş [_matherr](matherr.md).

## <a name="remarks"></a>Açıklamalar

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **exp2** alın ve dönüş **float** ve **uzun çift** türleri. Bir C programı **exp2** her zaman alan ve döndüren bir **çift**.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üstbilgi|
|-------------|--------------|------------------|
|**exp**, **expf**, **expl**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[exp, expf, expl](exp-expf.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
