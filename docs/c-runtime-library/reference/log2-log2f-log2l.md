---
title: log2, log2f, log2l | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16fb56b1a3aef56e201d469974c5de434a08aa41
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32399533"
---
# <a name="log2-log2f-log2l"></a>log2, log2f, log2l

Belirtilen değer ikili (2 tabanı) logaritmasını belirler.

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
Base-2 logaritmasını belirlemek için değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa döndürür log2 dönmek *x*.

Aksi takdirde, aşağıdaki değerlerden birini döndürebilir:

|Sorun|Döndür|
|-----------|------------|
|*x* < 0|NaN|
|*x* ±0 =|-SONSUZ|
|*x* = 1|+0|
|+ SONSUZ|+ SONSUZ|
|NaN|NaN|
|etki alanı hatası|NaN|
|kutbu'na hata|-HUGE_VAL, - HUGE_VALF, veya - HUGE_VALL|

Hataları raporlanır belirtilmiş [_matherr](matherr.md).

## <a name="remarks"></a>Açıklamalar

X bir tamsayı değilse, bu işlev temelde en önemli 1 biti sıfır tabanlı dizinini döndürür *x*.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgi|
|--------------|--------------|------------------|
|**log2**, **log2f**, **log2l**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
