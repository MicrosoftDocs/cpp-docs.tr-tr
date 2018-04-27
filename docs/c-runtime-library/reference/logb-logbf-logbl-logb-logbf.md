---
title: logb, logbf, logbl, _logb, _logbf | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- logb
- _logb
- _logbl
- logbf
- logbl
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
- logb
- logbl
- _logb
- _logbf
- logbf
dev_langs:
- C++
helpviewer_keywords:
- _logbf function
- mantissas, floating-point variables
- logbf function
- _logb function
- exponent, floating-point numbers
- logbl function
- logb function
- floating-point functions
- floating-point functions, mantissa and exponent
- exponents and mantissas
ms.assetid: 780c4daa-6fe6-4fbc-9412-4c1ba1a1766f
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5f279d2b31ba9a40dd3d5c0e5d3c50e5a9a4b170
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="logb-logbf-logbl-logb-logbf"></a>logb, logbf, logbl, _logb, _logbf

Kayan nokta bağımsız değişkenin üs değeri ayıklar.

## <a name="syntax"></a>Sözdizimi

```C
double logb(
   double x
);
float logb(
   float x
); // C++ only
long double logb(
   long double x
); // C++ only
float logbf(
   float x
);
long double logbl(
   long double x
);
double _logb(
   double x
);
float _logbf(
   float x
);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**logb** taraflı olmayan üs değerini döndürür *x* bir kayan nokta değeri olarak gösterilen imzalı bir tamsayı olarak.

## <a name="remarks"></a>Açıklamalar

**Logb** işlevleri üstel kayan nokta bağımsız değişkeninin değerini ayıklamak *x*, gibi *x* sonsuz aralığıyla temsil. Varsa bağımsız değişkeni *x* olan normalleştirilmiş gibi normal dışı, işlem görür.

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **logb** alın ve dönüş **float** veya **uzun** **çift** değerleri. Bir C programı **logb** her zaman alan ve döndüren bir **çift**.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± QNAN, UL|Yok.|_DOMAIN|
|± 0|ZERODIVIDE|_SING|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_logb**|\<float.h >|
|**logb**, **logbf**, **logbl**, **_logbf**|\<Math.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
