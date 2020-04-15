---
title: exp2, exp2f, exp2l
ms.date: 4/2/2020
api_name:
- exp2
- exp2f
- exp2l
- _o_exp2
- _o_exp2f
- _o_exp2l
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
- exp2
- math/exp2
- exp2f
- math/exp2f
- exp2l
- math/exp2l
helpviewer_keywords:
- exp2 function
- exp2f function
- exp2l function
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
ms.openlocfilehash: a5df1a216b4565f013a4c42b4ef4369b5b7f9b04
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347578"
---
# <a name="exp2-exp2f-exp2l"></a>exp2, exp2f, exp2l

Belirtilen değere yükseltilen 2'yi hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double exp2(
   double x
);

float exp2(
   float x
);  // C++ only

long double exp2(
   long double x
); // C++ only

float exp2f(
   float x
);

long double exp2l(
   long double x
);
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Üs değeri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, *x'in*baz-2 üslerini, yani 2<sup>x'i döndürür.</sup> Aksi takdirde, aşağıdaki değerlerden birini döndürür:

|Sorun|Dönüş|
|-----------|------------|
|*x* = ±0|1|
|*x* = -SONSUZLUK|+0|
|*x* = +SONSUZLUK|+SONSUZLUK|
|*x* = NaN|NaN|
|Taşma aralığı hatası|+HUGE_VAL, +HUGE_VALF veya +HUGE_VALL|
|Akış altı aralığı hatası|Doğru sonuç, yuvarlama sonra|

Hatalar [_matherr](matherr.md)belirtildiği gibi bildirilir.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, **float** ve **uzun çift** türleri alan ve döndüren aşırı **exp2** yüklerini arayabilirsiniz. Bir C programında, **exp2** her zaman alır ve bir **çift**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgi|C++ üstbilgi|
|-------------|--------------|------------------|
|**exp**, **expf**, **expl**|\<math.h>|\<cmath>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[exp, expf, expl](exp-expf.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
