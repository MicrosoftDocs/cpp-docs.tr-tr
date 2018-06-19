---
title: fdim, fdimf, fdiml | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- fdim
- fdimf
- fdiml
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
- fdim
- fdimf
- fdiml
- math/fdim
- math/fdimf
- math/fdiml
dev_langs:
- C++
helpviewer_keywords:
- fdim function
- fdimf function
- fdiml function
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cdcad02c94717715fdda1b3a9d2e820fc16d0bf4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397512"
---
# <a name="fdim-fdimf-fdiml"></a>fdim, fdimf, fdiml

Pozitif değerler arasındaki farkın birinci ve ikinci belirler.

## <a name="syntax"></a>Sözdizimi

```C
double fdim(
   double x,
   double y
);

float fdim(
   float x,
   float y
); //C++ only

long double fdim(
   long double x,
   long double y
); //C++ only

float fdimf(
   float x,
   float y
);

long double fdiml(
   long double x,
   long double y
);

```

### <a name="parameters"></a>Parametreler

*x*<br/>
İlk değer.

*Y*<br/>
İkinci değer.

## <a name="return-value"></a>Dönüş Değeri

Pozitif birbirinden döndürür *x* ve *y*:

|Dönüş değeri|Senaryo|
|------------------|--------------|
|x-y|x > y|
|0|if x <= y|

Aksi takdirde, aşağıdaki hatalardan biri döndürebilir:

|Sorun|Döndür|
|-----------|------------|
|taşma aralık hatası|+ HUGE_VAL + HUGE_VALF, veya + HUGE_VALL|
|Underflow aralık hatası|(sonra yuvarlama) doğru değeri|
|*x* veya *y* NaN olup|NaN|

Hataları raporlanır belirtilmiş [_matherr](matherr.md).

## <a name="remarks"></a>Açıklamalar

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **fdim** alın ve dönüş **float** ve **uzun** **çift** türleri. Bir C programı **fdim** her zaman alan ve döndüren bir **çift**.

NaN işleme dışında bu işlev eşdeğerdir `fmax(x - y, 0)`.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgi|
|--------------|--------------|------------------|
|**fdim**, **fdimf**, **fdiml**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
