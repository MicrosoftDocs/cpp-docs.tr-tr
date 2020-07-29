---
title: ilogb, ilogbf, ilogbl2
ms.date: 04/05/2018
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
ms.openlocfilehash: 6feea7a242a066f669429944226f4ca6022505b6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232527"
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
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Belirtilen değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, *x* değerinin taban 2 üssünü değer olarak döndürün **`signed int`** .

Aksi takdirde, içinde tanımlanan aşağıdaki değerlerden birini döndürür \<math.h> :

|Girdi|Sonuç|
|-----------|------------|
|± 0|FP_ILOGB0|
|± inf, ± Nan, sonsuz|FP_ILOGBNAN|

Hatalar [_matherr](matherr.md)belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, ve türlerini alıp döndüren **IGB** 'nin aşırı yüklerini çağırabilirsiniz **`float`** **`long double`** . C **programında,** IBC her zaman alır ve döndürür **`double`** .

Bu işlevi çağırmak, eşdeğer **logb** işlevini çağırmaya benzer ve sonra dönüş değerini ' a dönüştürmektir **`int`** .

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üstbilgisi|
|-------------|--------------|------------------|
|ıalınan **GB**, **ılogbf**, **ılogbl**|\<math.h>|\<cmath>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[frexp](frexp.md)<br/>
[logb, logbf, logbl, _logb, _logbf](logb-logbf-logbl-logb-logbf.md)<br/>
