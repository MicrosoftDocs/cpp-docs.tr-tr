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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
ms.openlocfilehash: 29a1a9e2003091944a4587036c62a49d76333080
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341716"
---
# <a name="log2-log2f-log2l"></a>log2, log2f, log2l

Belirtilen değerin ikili (base-2) logaritmasını belirler.

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

*X*<br/>
Taban-2 logaritmasını belirlemek için değer.

## <a name="return-value"></a>Dönüş Değeri

Başarı da, döner log2 *x*.

Aksi takdirde, aşağıdaki değerlerden birini döndürebilir:

|Sorun|Dönüş|
|-----------|------------|
|*x* < 0|NaN|
|*x* = ±0|-SONSUZLUK|
|*x* = 1|+0|
|+SONSUZLUK|+SONSUZLUK|
|NaN|NaN|
|etki alanı hatası|NaN|
|kutup hatası|-HUGE_VAL, -HUGE_VALF veya -HUGE_VALL|

Hatalar [_matherr](matherr.md)belirtildiği gibi bildirilir.

## <a name="remarks"></a>Açıklamalar

X bir tamsayı ise, bu işlev aslında en önemli 1 bit *x'in*sıfır tabanlı indeksini döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgi|C++ üstbilgi|
|--------------|--------------|------------------|
|**log2**, **log2f**, **log2l**|\<math.h>|\<cmath>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
