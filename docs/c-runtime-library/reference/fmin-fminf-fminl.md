---
title: fmin, fminf, fminl | Microsoft Docs
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
- fmin
- fminf
- fminl
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
- fmin
- fminf
- fminl
- math/fmin
- math/fminf
- math/fminl
helpviewer_keywords:
- fmin function
- fminf function
- fminl function
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3de46ba0a8d550d961fd05527b49a68a1518c50a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="fmin-fminf-fminl"></a>fmin, fminf, fminl

Belirtilen iki değerin daha küçük belirler.

## <a name="syntax"></a>Sözdizimi

```C
double fmin(
   double x,
   double y
);

float fmin(
   float x,
   float y
); //C++ only

long double fmin(
   long double x,
   long double y
); //C++ only

float fminf(
   float x,
   float y
);

long double fminl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Karşılaştırılacak ilk değer.

*Y*<br/>
Karşılaştırılacak ikinci değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, döndürür küçük olanını *x* veya *y*.

|Giriş|Sonuç|
|-----------|------------|
|*x* NaN olup|*Y*|
|*y* NaN olup|*x*|
|*x* ve *y* NaN olan|NaN|

İşlev neden olmaz [_matherr](matherr.md) çağrılacak, kayan nokta özel durumlar neden veya değerini değiştirmek **errno**.

## <a name="remarks"></a>Açıklamalar

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **fmin** alın ve dönüş **float** ve **uzun** **çift** türleri. Bir C programı **fmin** her zaman alan ve döndüren bir **çift**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**fmin**, **fminf**, **fminl**|C: \<math.h ><br />C++: \<math.h > veya \<cmath >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)<br/>
