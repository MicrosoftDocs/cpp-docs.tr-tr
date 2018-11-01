---
title: lrint, lrintf, lrintl, llrint, llrintf, llrintl
ms.date: 04/05/2018
apiname:
- lrint
- lrintl
- lrintf
- llrint
- llrintf
- llrintl
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
ms.openlocfilehash: a1fc404182d9d2a5cd6870fcb2cd1ff3e5f4da55
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500850"
---
# <a name="lrint-lrintf-lrintl-llrint-llrintf-llrintl"></a>lrint, lrintf, lrintl, llrint, llrintf, llrintl

Yönünü ve geçerli yuvarlama modu kullanarak belirtilen kayan nokta değeri en yakın tamsayı değerine yuvarlanır.

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

Başarılı olursa, yuvarlak tamsayı değerini döndürür *x*.

|Sorun|döndürülecek|
|-----------|------------|
|*x* dönüş türü aralığının dışında<br /><br /> *x* ±∞ =<br /><br /> *x* NaN =|Başlatır **FE_INVALID** ve sıfır (0) değerini döndürür.|

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **lrint** ve **llrint** Süren **float** ve **uzun**  **çift** türleri. C programında **lrint** ve **llrint** her zaman bir **çift**.

Varsa *x* bir tamsayı değeri, bu işlevler raise kayan nokta denk göstermiyor **FE_INEXACT**.

**Microsoft'a özgü**: sonucu dönüş türünün aralığı dışında olduğunda veya parametre bir NaN veya sonsuz olduğunda, uygulama tanımlı dönüş değeridir. Microsoft derleyicisi, sıfır (0) değeri döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**lrint**, **lrintf**, **lrintl**, **llrint**, **llrintf**, **llrintl**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
