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
ms.openlocfilehash: fdafba039537358c9b6a1de21dc176ceea38b4fa
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954761"
---
# <a name="ilogb-ilogbf-ilogbl"></a>ilogb, ilogbf, ilogbl

Belirtilen değerin taraflı olmayan taban 2 üssünü temsil eden bir tamsayı alır.

## <a name="syntax"></a>Sözdizimi

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

Başarılı olursa, *x* 'in Base-2 üssünü işaretli bir **int** değeri olarak döndürün.

Aksi takdirde, \<Math. h > tanımlı aşağıdaki değerlerden birini döndürür:

|Giriş|Sonuç|
|-----------|------------|
|±0|FP_ILOGB0|
|± inf, ± Nan, sonsuz|FP_ILOGBNAN|

Hatalar [_matherr](matherr.md)içinde belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

Aşırı C++ yüklemeye izin verdiğinden, **float** ve **Long** **Double** türlerini alıp döndüren IOF **IGB** aşırı yüklerini çağırabilirsiniz. C **programında,** IBC her zaman bir **Double**alır ve döndürür.

Bu işlevi çağırmak, eşdeğer **logb** işlevini çağırmaya benzerdir ve sonra Return değerini **int**olarak verir.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++üst bilgi|
|-------------|--------------|------------------|
|ıalınan **GB**, **ılogbf**, **ılogbl**|\<Math. h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[frexp](frexp.md)<br/>
[logb, logbf, logbl, _logb, _logbf](logb-logbf-logbl-logb-logbf.md)<br/>
