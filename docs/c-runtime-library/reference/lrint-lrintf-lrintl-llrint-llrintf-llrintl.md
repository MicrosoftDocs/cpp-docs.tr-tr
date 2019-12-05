---
title: lrint, lrintf, lrintl, llrint, llrintf, llrintl
ms.date: 04/05/2018
api_name:
- lrint
- lrintl
- lrintf
- llrint
- llrintf
- llrintl
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
- lrint
- lrintf
- lrintl
- llrint
- llrintf
- llrintl
- math/lrint
- math/lrintf
- math/lrintl
- math/llrint
- math/llrintf
- math/llrintl
helpviewer_keywords:
- lrint function
- lrintf function
- lrintl function
- llrint function
- llrintf function
- llrintl function
ms.assetid: 28ccd5b3-5e6f-434f-997d-a21d51b8ce7f
ms.openlocfilehash: c7831842eb4d3c1eef9c4c9e83bbddb557cec0e3
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857755"
---
# <a name="lrint-lrintf-lrintl-llrint-llrintf-llrintl"></a>lrint, lrintf, lrintl, llrint, llrintf, llrintl

Geçerli yuvarlama modunu ve yönünü kullanarak belirtilen kayan nokta değerini en yakın integral değere yuvarlar.

## <a name="syntax"></a>Sözdizimi

```C
long int lrint(
   double x
);

long int lrint(
   float x
); //C++ only

long int lrint(
   long double x
); //C++ only

long int lrintf(
   float x
);

long int lrintl(
   long double x
);

long long int llrint(
   double x
);

long long int llrint(
   float x
); //C++ only

long long int llrint(
   long double x
); //C++ only

long long int llrintf(
   float x
);

long long int llrintl(
   long double x
);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Yuvarlanacak değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa *x*'in yuvarlatılmış tamsayı değerini döndürür.

|Sorun|Return|
|-----------|------------|
|*x* , dönüş türü aralığının dışında<br /><br /> *x* = ±∞<br /><br /> *x* = Nan|**FE_INVALID** yükseltir ve sıfıra (0) döndürür.|

## <a name="remarks"></a>Açıklamalar

Aşırı C++ yüklemeye izin verdiğinden, **float** ve **Long** **Double** türlerine sahip **lrint** ve **llrint** aşırı yüklerini çağırabilirsiniz. C programında **lrint** ve **llrint** her zaman bir **Double**alır.

*X* , bir integral değerin kayan nokta eşdeğerini temsil ediyorsa, bu işlevler **FE_INEXACT**yükseltir.

**Microsoft 'a özgü**: sonuç, dönüş türü aralığının dışındaysa veya parametre bir NaN veya Infinity olduğunda, dönüş değeri uygulama tanımlı olur. Microsoft derleyicisi sıfır (0) değeri döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|**lrint**, **lrintf**, **lrintl**, **llrint**, **llrintf**, **llrintl**|\<Math. h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
