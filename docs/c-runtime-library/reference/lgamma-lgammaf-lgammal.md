---
title: lgamma, lgammaf, lgammal | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- lgamma
- lgammaf
- lgammal
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
- lgamma
- lgammaf
- lgammal
- math/lgamma
- math/lgammaf
- math/lgammal
dev_langs:
- C++
helpviewer_keywords:
- lgamma function
- lgammal function
- lgammaf function
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4fb668e1c24d3f24331e0892002530192afdaeb6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma, lgammaf, lgammal

Mutlak değeri belirtilen değere Gama işlevinin doğal logaritmasını belirler.

## <a name="syntax"></a>Sözdizimi

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
İşlem için değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, mutlak değeri Gama işlevinin doğal logaritmasını Döndür *x*.

|Sorun|Döndür|
|-----------|------------|
|*x* NaN =|NaN|
|*x* ±0 =|+ SONSUZ|
|*x*= negatif tamsayı|+ SONSUZ|
|±INFINITY|+ SONSUZ|
|kutbu'na hata|+ HUGE_VAL + HUGE_VALF, veya + HUGE_VALL|
|taşma aralık hatası|±HUGE_VAL, ±HUGE_VALF veya ±HUGE_VALL|

Hataları raporlanır belirtilmiş [_matherr](matherr.md).

## <a name="remarks"></a>Açıklamalar

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **lgamma** alın ve dönüş **float** ve **uzun** **çift** türleri. Bir C programı **lgamma** her zaman alan ve döndüren bir **çift**.

X bir rasyonel sayı ise, bu işlevi (x - 1) çarpımını logaritmasını döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgi|
|--------------|--------------|------------------|
|**lgamma**, **lgammaf**, **lgammal**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[tgamma, tgammaf, tgammal](tgamma-tgammaf-tgammal.md)<br/>
