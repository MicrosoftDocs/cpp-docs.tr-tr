---
title: log2, log2f, log2l
ms.date: 04/05/2018
api_name:
- log2
- log2l
- log2f
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
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
ms.openlocfilehash: bf1734ea2f96fa1c09b3b0d1f43b681fc31c8f9f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953165"
---
# <a name="log2-log2f-log2l"></a>log2, log2f, log2l

Belirtilen değerin ikili (taban 2) logaritmasını belirler.

## <a name="syntax"></a>Sözdizimi

```C
double log2(
   double x
);

float log2(
   float x
); //C++ only

long double log2(
   long double x
); //C++ only

float log2f(
   float x
);

long double log2l(
   long double x
);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Taban-2 logaritmasını belirleme değeri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda, return log2 *x*döndürür.

Aksi takdirde, aşağıdaki değerlerden birini döndürebilir:

|Sorun|döndürülmesini|
|-----------|------------|
|*x* < 0|NaN|
|*x* = ±0|-SONSUZLUK|
|*x* = 1|+0|
|\+ SONSUZLUK|\+ SONSUZLUK|
|NaN|NaN|
|etki alanı hatası|NaN|
|direk hatası|-HUGE_VAL,-HUGE_VALF veya-HUGE_VALL|

Hatalar [_matherr](matherr.md)içinde belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

X bir tamsayıdır, bu işlev temelde *x*'in en önemli 1 bitin sıfır tabanlı dizinini döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|**log2**, **log2f**, **log2l**|\<Math. h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
