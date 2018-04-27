---
title: lrint, lrintf, lrintl, llrint, llrintf, llrintl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- lrint function
- lrintf function
- lrintl function
- llrint function
- llrintf function
- llrintl function
ms.assetid: 28ccd5b3-5e6f-434f-997d-a21d51b8ce7f
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 30056214b07624429c8b1b23237585e5b6f46266
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="lrint-lrintf-lrintl-llrint-llrintf-llrintl"></a>lrint, lrintf, lrintl, llrint, llrintf, llrintl

En yakın tam sayı değeri, belirtilen kayan noktalı değeri geçerli yuvarlama modu ve yön kullanarak yuvarlar.

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

Başarılı olursa, yuvarlatılmış tam sayı değerini döndürür *x*.

|Sorun|Döndür|
|-----------|------------|
|*x* dönüş türü aralık dışında<br /><br /> *x* ±∞ =<br /><br /> *x* NaN =|Başlatır **FE_INVALID** ve sıfır (0) döndürür.|

## <a name="remarks"></a>Açıklamalar

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **lrint** ve **llrint** Süren **float** ve **uzun**  **çift** türleri. Bir C programı **lrint** ve **llrint** her zaman bir **çift**.

Varsa *x* bu işlevler olursa bir tam sayı değeri kayan nokta denk göstermiyor **FE_INEXACT**.

**Microsoft özel**: sonucu dönüş türü aralık dışında olduğunda veya parametre NaN ya da sonsuz olduğunda döndürülen değer tanımlı uygulamasıdır. Microsoft derleyici sıfır (0) değerini döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgi|
|--------------|--------------|------------------|
|**lrint**, **lrintf**, **lrintl**, **llrint**, **llrintf**, **llrintl**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
