---
title: fdim, fdimf, fdiml
ms.date: 04/05/2018
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
helpviewer_keywords:
- fdim function
- fdimf function
- fdiml function
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
ms.openlocfilehash: 263635a32b21b01faa84405ab97bd5518f054ba5
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518183"
---
# <a name="fdim-fdimf-fdiml"></a>fdim, fdimf, fdiml

Birinci ve ikinci değer arasındaki pozitif farkı belirler.

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

Arasındaki pozitif farkı döndürür *x* ve *y*:

|Dönüş değeri|Senaryo|
|------------------|--------------|
|x-y|x > y|
|0|if x <= y|

Aksi takdirde, aşağıdaki hatalardan birini döndürebilir:

|Sorun|döndürülecek|
|-----------|------------|
|Taşma aralık hatası|+ HUGE_VAL + HUGE_VALF, veya + HUGE_VALL|
|Yetersiz aralık hatası|doğru değeri (sonra yuvarlama)|
|*x* veya *y* NaN olup|NaN|

Hatalar rapor, belirtilen [_matherr](matherr.md).

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **fdim** alan ve getiren **float** ve **uzun** **çift** türleri. C programında **fdim** her zaman alan ve döndüren bir **çift**.

Bu işlev NaN işleme dışında değerine eşdeğer olan `fmax(x - y, 0)`.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**fdim**, **fdimf**, **fdiml**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
