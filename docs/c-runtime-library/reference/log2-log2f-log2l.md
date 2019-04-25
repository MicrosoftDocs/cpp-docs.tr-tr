---
title: log2, log2f, log2l
ms.date: 04/05/2018
apiname:
- log2
- log2l
- log2f
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
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
ms.openlocfilehash: d70d074b13b0f24f1f040ef0e861e073e303ac7b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285945"
---
# <a name="log2-log2f-log2l"></a>log2, log2f, log2l

Belirtilen değer ikili (2 tabanında) logaritmasını belirler.

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
2 tabanında logaritmasını belirlemek için değer.

## <a name="return-value"></a>Dönüş Değeri

Başarı durumunda log2 döndürür dönüş *x*.

Aksi halde aşağıdaki değerlerden birini döndürebilir:

|Sorun|döndürülecek|
|-----------|------------|
|*x* < 0|NaN|
|*x* = ±0|-INFİNİTY|
|*x* = 1|+0|
|+ INFİNİTY|+ INFİNİTY|
|NaN|NaN|
|etki alanı hatası|NaN|
|kutup hata|-HUGE_VAL, - HUGE_VALF, veya - HUGE_VALL|

Hatalar rapor, belirtilen [_matherr](matherr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlev x bir tamsayı değilse, temelde en önemli 1 biti sıfır tabanlı dizinini döndürür. *x*.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**log2**, **log2f**, **log2l**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
