---
title: fmax, fmaxf, fmaxl
ms.date: 04/05/2018
api_name:
- fmax
- fmaxf
- fmaxl
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
- fmax
- fmaxf
- fmaxl
- math/fmax
- math/fmaxf
- math/fmaxl
helpviewer_keywords:
- fmax function
- fmaxf function
- fmaxl function
ms.assetid: a773ccf7-495e-4a9a-8c6d-dfb53e341e35
ms.openlocfilehash: 27b495e9344ca7e2e3e061b19fee696ce2bdceb2
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957110"
---
# <a name="fmax-fmaxf-fmaxl"></a>fmax, fmaxf, fmaxl

Belirtilen iki sayısal değerin daha büyük olduğunu belirleme.

## <a name="syntax"></a>Sözdizimi

```C
double fmax(
   double x,
   double y
);

float fmax(
   float x,
   float y
); //C++ only

long double fmax(
   long double x,
   long double y
); //C++ only

float fmaxf(
   float x,
   float y
);

long double fmaxl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Karşılaştırılacak ilk değer.

*Iz*<br/>
Karşılaştırılacak ikinci değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, *x* veya *y*'nin büyük bir kısmını döndürür. Döndürülen değer kesin ve herhangi bir yuvarlama biçimine bağlı değildir.

Aksi takdirde, aşağıdaki değerlerden birini döndürebilir:

|Sorun|döndürülmesini|
|-----------|------------|
|*x* = Nan|*Iz*|
|*y* = Nan|*x*|
|*x* ve *y* = Nan|NaN|

Bu işlev, [_matherr](matherr.md)içinde belirtilen hataları kullanmaz.

## <a name="remarks"></a>Açıklamalar

Aşırı C++ yüklemeye izin verdiğinden, float ve Long Double türlerini alıp döndüren Fmax aşırı yüklerini çağırabilirsiniz. C programında Fmax her zaman bir Double alır ve döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|**Fmax**, **fmaxf**, **fmaxl**|\<Math. h >|\<cmath > veya \<Math. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fmin, fminf, fminl](fmin-fminf-fminl.md)<br/>
