---
title: lrint, lrintf, lrintl, llrint, llrintf, llrintl
ms.date: 4/2/2020
api_name:
- lrint
- lrintl
- lrintf
- llrint
- llrintf
- llrintl
- _o_llrint
- _o_llrintf
- _o_llrintl
- _o_lrint
- _o_lrintf
- _o_lrintl
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
ms.openlocfilehash: 6283cffaa094af4484d48781b5bb92d0339d38d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341660"
---
# <a name="lrint-lrintf-lrintl-llrint-llrintf-llrintl"></a>lrint, lrintf, lrintl, llrint, llrintf, llrintl

Geçerli yuvarlama modunu ve yönünü kullanarak belirtilen kayan nokta değerini en yakın integral değerine yuvarlar.

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

*X*<br/>
yuvarlak değeri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, *x'in*yuvarlatılmış integral değerini döndürür.

|Sorun|Dönüş|
|-----------|------------|
|*x* dönüş türünün aralığının dışında<br /><br /> *x* = ±─<br /><br /> *x* = NaN|**FE_INVALID** yükseltir ve sıfır (0) döndürür.|

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, **float** ve **uzun** **çift** türleri alan aşırı **lrint** ve **llrint** yükleri arayabilirsiniz. C programında, **lrint** ve **llrint** her zaman **bir çift**alır.

*X* integral değerinin kayan nokta eşdeğerini temsil etmiyorsa, bu işlevler **FE_INEXACT**yükseltir.

**Microsoft'a özgü**: Sonuç, iade türünün aralığının dışında olduğunda veya parametre Bir NaN veya sonsuz olduğunda, iade değeri tanımlanır. Microsoft derleyicisi sıfır (0) değerini döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgi|C++ üstbilgi|
|--------------|--------------|------------------|
|**lrint**, **lrintf**, **lrintl**, **llrint ,** **llrintf**, **llrintl**|\<math.h>|\<cmath>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
