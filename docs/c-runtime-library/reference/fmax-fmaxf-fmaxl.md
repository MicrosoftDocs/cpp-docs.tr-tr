---
title: fmax, fmaxf, fmaxl
ms.date: 04/05/2018
apiname:
- fmax
- fmaxf
- fmaxl
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
ms.openlocfilehash: 371d53257427f2235048807968c82fec1b8bf699
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523708"
---
# <a name="fmax-fmaxf-fmaxl"></a>fmax, fmaxf, fmaxl

Belirtilen iki sayısal değerin daha büyük belirleyin.

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

*Y*<br/>
Karşılaştırılacak ikinci değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, büyük döndürür *x* veya *y*. Döndürülen değer, tam ve yuvarlama herhangi bir form üzerinde bağlı değildir.

Aksi halde aşağıdaki değerlerden birini döndürebilir:

|Sorun|döndürülecek|
|-----------|------------|
|*x* NaN =|*Y*|
|*y* NaN =|*x*|
|*x* ve *y* NaN =|NaN|

Bu işlev, belirtilen hata kullanmaz [_matherr](matherr.md).

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, alan ve kayan nokta ve uzun çift türleri getiren fmax yüklerini çağırabilirsiniz. C programında fmax her zaman alır ve bir double döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**fmax**, **fmaxf**, **fmaxl**|\<Math.h >|\<cmath > veya \<math.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fmin, fminf, fminl](fmin-fminf-fminl.md)<br/>
