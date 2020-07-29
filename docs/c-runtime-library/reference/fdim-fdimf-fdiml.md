---
title: fdim, fdimf, fdiml
ms.date: 04/05/2018
api_name:
- fdim
- fdimf
- fdiml
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
ms.openlocfilehash: 1a7bbeaf77c94f620a82f77fb1aad3c71c34f2ef
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221919"
---
# <a name="fdim-fdimf-fdiml"></a>fdim, fdimf, fdiml

Birinci ve ikinci değerler arasındaki pozitif farkı belirler.

## <a name="syntax"></a>Söz dizimi

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

*Iz*<br/>
İkinci değer.

## <a name="return-value"></a>Dönüş Değeri

*X* ve *y*arasındaki pozitif farkı döndürür:

|Döndürülen değer|Senaryo|
|------------------|--------------|
|x-y|x > y ise|
|0|x <= y ise|

Aksi takdirde, aşağıdaki hatalardan birini döndürebilir:

|Sorun|Döndürülmesini|
|-----------|------------|
|Taşma aralığı hatası|+ HUGE_VAL, + HUGE_VALF veya + HUGE_VALL|
|Yetersiz yer aralığı hatası|doğru değer (yuvarladıktan sonra)|
|*x* veya *y* Nan 'dir|NaN|

Hatalar [_matherr](matherr.md)belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, ve türlerini alıp döndüren **fdim** aşırı yüklerini çağırabilirsiniz **`float`** **`long double`** . C programında **fdim** her zaman alır ve döndürür **`double`** .

NaN işleme hariç, bu işlev ile eşdeğerdir `fmax(x - y, 0)` .

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**fdim**, **fdimf**, **fdiml**|\<math.h>|\<cmath>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
