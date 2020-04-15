---
title: fma, fmaf, fmal
ms.date: 4/2/2020
api_name:
- fma
- fmaf
- fmal
- _o_fma
- _o_fmaf
- _o_fmal
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
ms.openlocfilehash: 993ca4d57202b3789929161a964b3e41d48fd98f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346563"
---
# <a name="fma-fmaf-fmal"></a>fma, fmaf, fmal

İki değeri bir araya getirir, üçüncü bir değer ekler ve ara yuvarlama nedeniyle herhangi bir hassasiyet kaybetmeden sonucu yuvarlar.

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

*X*<br/>
İlk çarpan değer.

*Y*<br/>
Çarpımı gereken ikinci değer.

*Z*<br/>
Eklenecek değer.

## <a name="return-value"></a>Dönüş Değeri

`(x * y) + z` döndürür. İade değeri daha sonra geçerli yuvarlama biçimi kullanılarak yuvarlanır.

Aksi takdirde, aşağıdaki değerlerden birini döndürebilir:

|Sorun|Dönüş|
|-----------|------------|
|*x* = SONSUZLUK, *y* = 0 veya<br /><br /> *x* = 0, *y* = SONSUZLUK|NaN|
|*x* veya *y* = tam ± INFINITY, *z* = Ters işaretli SONSUZLUK|NaN|
|*x* veya *y* = NaN|NaN|
|değil (*x* = 0, *y*= belirsiz) ve *z* = NaN<br /><br /> değil (*x*=belirsiz, *y*=0) ve *z* = NaN|NaN|
|Taşma aralığı hatası|±HUGE_VAL, ±HUGE_VALF veya ±HUGE_VALL|
|Akış altı aralığı hatası|döndürülmeden sonra doğru değer.|

Hatalar [_matherr](matherr.md)belirtildiği gibi bildirilir.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, **float** ve **uzun** **çift** türleri alan ve döndüren **aşırı fma** yükleri arayabilirsiniz. Bir C programında, **fma** her zaman alır ve bir **çift**döndürür.

Bu işlev değeri sonsuz kesinlik için alınmış gibi hesaplar ve sonra nihai sonucu yuvarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgi|C++ üstbilgi|
|--------------|--------------|------------------|
|**fma**, **fmaf**, **fmal**|\<math.h>|\<cmath>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
