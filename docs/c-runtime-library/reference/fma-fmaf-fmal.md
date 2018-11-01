---
title: fma, fmaf, fmal
ms.date: 04/05/2018
apiname:
- fma
- fmaf
- fmal
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
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
ms.openlocfilehash: a3b540a72c6f2fc2264d6366111831fbe2a02a6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529954"
---
# <a name="fma-fmaf-fmal"></a>fma, fmaf, fmal

İki değerin birbirine çarpar, üçüncü değer ekler ve ardından sonucu Ara yuvarlama nedeniyle herhangi bir duyarlık kaybı yaşamadan yuvarlar.

## <a name="syntax"></a>Sözdizimi

```C
double fma(
   double x,
   double y,
   double z
);

float fma(
   float  x,
   float  y,
   float z
); //C++ only

long double fma(
   long double  x,
   long double  y,
   long double z
); //C++ only

float fmaf(
   float  x,
   float  y,
   float z
);

long double fmal(
   long double  x,
   long double  y,
   long double z
);

```

### <a name="parameters"></a>Parametreler

*x*<br/>
Çarpılacak ilk değer.

*Y*<br/>
Çarpılacak ikinci değer.

*z*<br/>
Eklenecek değer.

## <a name="return-value"></a>Dönüş Değeri

Döndürür `(x * y) + z`. Dönüş değeri geçerli yuvarlama biçimini kullanarak yuvarlanır.

Aksi halde aşağıdaki değerlerden birini döndürebilir:

|Sorun|döndürülecek|
|-----------|------------|
|*x* SONSUZ, = *y* = 0 veya<br /><br /> *x* = 0, *y* SONSUZ =|NaN|
|*x* veya *y* = tam ± SONSUZ, *z* SONSUZ ters işaretli =|NaN|
|*x* veya *y* NaN =|NaN|
|yok (*x* = 0, *y*belirsiz =) ve *z* NaN =<br /><br /> yok (*x*belirsiz = *y*= 0) ve *z* NaN =|NaN|
|Taşma aralık hatası|±HUGE_VAL, ±HUGE_VALF veya ±HUGE_VALL|
|Yetersiz aralık hatası|sonra yuvarlama doğru değeri.|

Hatalar rapor, belirtilen [_matherr](matherr.md).

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **fma** alan ve getiren **float** ve **uzun** **çift** türleri. C programında **fma** her zaman alan ve döndüren bir **çift**.

Bu işlev, sonsuz duyarlık için alınan ve daha sonra Nihai sonuç yuvarlanır gibi sorgulamanıza değeri hesaplar.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**FMA**, **fmaf**, **fmal**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
