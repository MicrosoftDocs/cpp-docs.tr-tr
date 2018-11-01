---
title: logb, logbf, logbl, _logb, _logbf
ms.date: 04/05/2018
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
ms.openlocfilehash: 9f598eedaf30b1f2a1858129e648a117355d112e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466293"
---
# <a name="logb-logbf-logbl-logb-logbf"></a>logb, logbf, logbl, _logb, _logbf

Bir kayan nokta bağımsız değişkeninin üs değerini ayıklar.

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
Bir kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**logb** popülasyon üs değerini döndürür *x* bir kayan nokta değeri olarak temsil edilen imzalı bir tamsayı olarak.

## <a name="remarks"></a>Açıklamalar

**Logb** işlevlerin kayan nokta bağımsız değişkeni üs değerini ayıklamak *x*gibi *x* sonsuz aralık içerisinde temsil ediliyormuş. Bağımsız değişken *x* olduğundan, normalleştirilmiş alacağı normalleştirilmekten çıkarılmışsa, normalleştirilmişmiş.

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **logb** alan ve getiren **float** veya **uzun** **çift** değerleri. C programında **logb** her zaman alan ve döndüren bir **çift**.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± QNAN, ONRAKİNİ BUL|Yok.|_DOMAIN|
|± 0|ZERODIVIDE|_SING|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_logb**|\<float.h >|
|**logb**, **logbf**, **logbl**, **_logbf**|\<Math.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
