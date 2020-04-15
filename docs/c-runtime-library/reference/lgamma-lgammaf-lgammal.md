---
title: lgamma, lgammaf, lgammal
ms.date: 4/2/2020
api_name:
- lgamma
- lgammaf
- lgammal
- _o_lgamma
- _o_lgammaf
- _o_lgammal
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
- lgamma
- lgammaf
- lgammal
- math/lgamma
- math/lgammaf
- math/lgammal
helpviewer_keywords:
- lgamma function
- lgammal function
- lgammaf function
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
ms.openlocfilehash: e2bdfbeac7b995be0b589156437a3ded39114adf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342158"
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma, lgammaf, lgammal

Belirtilen değerin gama fonksiyonunun mutlak değerinin doğal logaritmasını belirler.

## <a name="syntax"></a>Sözdizimi

```C
double lgamma( double x );
float lgammaf( float x );
long double lgammal( long double x );
```

```cpp
float lgamma( float x ); //C++ only
long double lgamma( long double x ); //C++ only
```

### <a name="parameters"></a>Parametreler

*X*<br/>
HesaplatMak için değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, *x*gama fonksiyonunun mutlak değerinin doğal logaritma döndürün.

|Sorun|Dönüş|
|-----------|------------|
|*x* = NaN|NaN|
|*x* = ±0|+SONSUZLUK|
|*x*= negatif toplam|+SONSUZLUK|
|±SONSUZLUK|+SONSUZLUK|
|kutup hatası|+HUGE_VAL, +HUGE_VALF veya +HUGE_VALL|
|taşma aralığı hatası|±HUGE_VAL, ±HUGE_VALF veya ±HUGE_VALL|

Hatalar [_matherr](matherr.md)belirtildiği gibi bildirilir.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, **float** ve **uzun** **çift** türleri alan ve döndüren aşırı **lgamma** yüklerini arayabilirsiniz. Bir C programında, **lgamma** her zaman alır ve bir **çift**döndürür.

X rasyonel bir sayı ise, bu fonksiyon faktöriyel (x - 1) logaritma döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgi|C++ üstbilgi|
|--------------|--------------|------------------|
|**lgamma**, **lgammaf**, **lgammal**|\<math.h>|\<cmath>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[tgamma, tgammaf, tgammal](tgamma-tgammaf-tgammal.md)<br/>
