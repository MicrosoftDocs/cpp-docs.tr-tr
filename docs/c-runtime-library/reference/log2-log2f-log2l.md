---
title: log2, log2f, log2l
ms.date: 4/2/2020
api_name:
- log2
- log2l
- log2f
- _o_log2
- _o_log2f
- _o_log2l
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
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
ms.openlocfilehash: 58da7790e6fbce915c16a02a1b0d972a6fe1049e
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911412"
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

*sayı*<br/>
Taban-2 logaritmasını belirleme değeri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda, return log2 *x*döndürür.

Aksi takdirde, aşağıdaki değerlerden birini döndürebilir:

|Sorun|Döndürülmesini|
|-----------|------------|
|*x* < 0|NaN|
|*x* = ± 0|-SONSUZLUK|
|*x* = 1|+ 0|
|+ SONSUZLUK|+ SONSUZLUK|
|NaN|NaN|
|etki alanı hatası|NaN|
|direk hatası|-HUGE_VAL,-HUGE_VALF veya-HUGE_VALL|

Hatalar [_matherr](matherr.md)belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

X bir tamsayıdır, bu işlev temelde *x*'in en önemli 1 bitin sıfır tabanlı dizinini döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**log2**, **log2f**, **log2l**|\<Math. h>|\<cmath>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
