---
title: erf, erff, erfl, erfc, erfcf, erfcl
ms.date: 04/05/2018
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
helpviewer_keywords:
- erfl function
- erff function
- erf function
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
ms.openlocfilehash: 5723286add75a57844f177b9df5d86eb15080229
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50450077"
---
# <a name="erf-erff-erfl-erfc-erfcf-erfcl"></a>erf, erff, erfl, erfc, erfcf, erfcl

Hata işlevini veya Tümleyici hata işlevini bir değeri hesaplar.

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
Bir kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**Erf** işlevleri Gauss cinsinden hata işlevini döndürür *x*. **Erfc** işlevleri Gauss cinsinden Tamamlayıcı hata işlevini döndürür *x*.

## <a name="remarks"></a>Açıklamalar

**Erf** işlevler hesapla Gauss hata işlevini *x*, olarak tanımlanır:

![X hata işlevini](media/crt_erf_formula.PNG "CRT_erf_formula")

Tamamlayıcı Gauss hata işlevi - 1 tanımlanan erf(x) olarak. **Erf** işlevleri 1.0 -1.0 aralığında bir değer döndürür. Döndürülen hata yok. **Erfc** İşlevler, 0 ila 2 aralığında bir değer döndürür. Varsa *x* için çok büyük **erfc**, **errno** değişkeni ayarlanır **ERANGE**.

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **erf** ve **erfc** alan ve getiren **float** ve **uzun** **çift** türleri. C programında **erf** ve **erfc** her zaman alan ve getiren bir **çift**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**erf**, **erff**, **erfl**, **erfc**, **erfcf**, **erfcl**|\<Math.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
