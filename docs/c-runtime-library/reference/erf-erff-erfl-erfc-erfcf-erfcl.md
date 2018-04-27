---
title: erf, erff, erfl, erfc, erfcf, erfcl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- erff
- erfl
- erf
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
- erfl
- erf
- erff
dev_langs:
- C++
helpviewer_keywords:
- erfl function
- erff function
- erf function
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1703b4e352fee798a7b38dd16edf6158cd7f53ea
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="erf-erff-erfl-erfc-erfcf-erfcl"></a>erf, erff, erfl, erfc, erfcf, erfcl

Hata işlevini veya bir değer Tamamlayıcı hata işlevini hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double erf(
   double x
);
float erf(
   float x
); // C++ only
long double erf(
   long double x
); // C++ only
float erff(
   float x
);
long double erfl(
   long double x
);
double erfc(
   double x
);
float erfc(
   float x
); // C++ only
long double erfc(
   long double x
); // C++ only
float erfcf(
   float x
);
long double erfcl(
   long double x
);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**Erf** işlevleri Gauss cinsinden hata işlevinin dönüş *x*. **Erfc** işlevleri tamamlayıcı Gauss cinsinden hata işlevinin dönüş *x*.

## <a name="remarks"></a>Açıklamalar

**Erf** işlevler hesapla Gauss cinsinden hata işlevini *x*, olarak tanımlanan:

![X hata işlevinin](media/crt_erf_formula.PNG "CRT_erf_formula")

Tamamlayıcı Gauss cinsinden hata işlevi olarak 1 - tanımlı erf(x). **Erf** işlevler 1.0 -1.0 aralığında bir değer döndürür. Döndürülen hata yoktur. **Erfc** İşlevler, 0-2 aralığında bir değer döndürür. Varsa *x* için çok büyük **erfc**, **errno** değişken ayarlandığında **ERANGE**.

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **erf** ve **erfc** alın ve dönüş **float** ve **uzun** **çift** türleri. Bir C programı **erf** ve **erfc** her zaman alın ve dönüş bir **çift**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**erf**, **erff**, **erfl**, **erfc**, **erfcf**, **erfcl**|\<Math.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
