---
title: ilogb, ilogbf, ilogbl2
description: IGB, ılogbf ve ilogbl2; için API başvurusu belirtilen değerin taraflı olmayan taban 2 üssünü temsil eden bir tamsayı alan.
ms.date: 9/1/2020
api_name:
- ilogb
- ilogbf
- ilogbl
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
- ilogb
- ilogbf
- ilogbl
- math/ilogb
- math/ilogbf
- math/ilogbl
helpviewer_keywords:
- ilogb function
- ilogbf function
- ilogbl function
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
ms.openlocfilehash: b27c329cca1edb9d30bb6b9b641f94d174c9c406
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556378"
---
# <a name="ilogb-ilogbf-ilogbl"></a>ilogb, ilogbf, ilogbl

Belirtilen değerin taraflı olmayan taban 2 üssünü temsil eden bir tamsayı alır.

## <a name="syntax"></a>Söz dizimi

```C
int ilogb(
   double x
);

int ilogb(
   float x
); //C++ only

int ilogb(
   long double x
); //C++ only

int ilogbf(
   float x
);

int ilogbl(
   long double x
);

#define ilogbl(X) // Requires C11 or higher
```

### <a name="parameters"></a>Parametreler

*sayı*\
Belirtilen değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, *x* değerinin taban 2 üssünü değer olarak döndürün **`signed int`** .

Aksi takdirde, içinde tanımlanan aşağıdaki değerlerden birini döndürür \<math.h> :

|Giriş|Sonuç|
|-----------|------------|
|± 0|FP_ILOGB0|
|± inf, ± Nan, sonsuz|FP_ILOGBNAN|

Hatalar [_matherr](matherr.md)belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, ve türlerini alıp döndüren **IGB** 'nin aşırı yüklerini çağırabilirsiniz **`float`** **`long double`** . C programında, \<tgmath.h> Bu işlevi çağırmak için makroyu kullanmadığınız müddetçe, IBC her zaman alır **ilogb** ve döndürür **`double`** .

\<tgmath.h> `ilogb()` Makroyu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

Bu işlevi çağırmak, eşdeğer **logb** işlevini çağırmaya benzer ve sonra dönüş değerini ' a dönüştürmektir **`int`** .

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üstbilgisi|
|-------------|--------------|------------------|
|ıalınan **GB**, **ılogbf**, **ılogbl**|\<math.h>|\<cmath>|
|**IGB** makrosu | \<tgmath.h> ||

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[frexp](frexp.md)<br/>
[logb, logbf, logbl, _logb, _logbf](logb-logbf-logbl-logb-logbf.md)<br/>
