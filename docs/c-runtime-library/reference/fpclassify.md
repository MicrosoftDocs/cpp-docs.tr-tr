---
title: fpclassify
ms.date: 04/05/2018
apiname:
- fpclassify
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
apitype: HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
ms.openlocfilehash: 626e356cf61415e4f8212a8a12d90a72fe4576bf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613882"
---
# <a name="fpclassify"></a>fpclassify

Kayan nokta bağımsız değişken sınıflandırılmasını döndürür.

## <a name="syntax"></a>Sözdizimi

```C
int fpclassify(
   /* floating-point */ x
);

int fpclassify(
   float x
); // C++ only

int fpclassify(
   double x
); // C++ only

int fpclassify(
   long double x
); // C++ only

```

### <a name="parameters"></a>Parametreler

*x*<br/>
Test etmek için kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**fpclassify** bağımsız değişkenin kayan nokta sınıfı gösteren bir Integer değeri döndürür *x*. Bu tabloda, olası değerler tarafından döndürülen gösterilmektedir **fpclassify**içinde tanımlanmış \<math.h >.

|Değer|Açıklama|
|-----------|-----------------|
|**FP_NAN**|Bir sessiz, sinyal veya belirsiz NaN|
|**FP_INFINITE**|Bir pozitif veya negatif sonsuz|
|**FP_NORMAL**|Bir pozitif veya negatif normalleştirilmiş sıfır olmayan değer|
|**FP_SUBNORMAL**|Pozitif veya negatif bir normalleştirilmişlikten çıkarılmış değeri|
|**FP_ZERO**|Bir pozitif veya sıfır değeri negatif|

## <a name="remarks"></a>Açıklamalar

C'de, **fpclassify** bir makrodur; C++ ' ta **fpclassify** bağımsız değişken türlerini kullanarak aşırı yüklenmiş bir işlev **float**, **çift**, veya **uzun** **çift**. Her iki durumda da, döndürülen değer bağımsız değişken ifadesi etkili türüne ve değil tüm ara gösterimi bağlıdır. Örneğin, bir normal **çift** veya **uzun** **çift** değeri sonsuzluk duruma, denormal veya sıfır için dönüştürüldüğünde değeri bir **float**.

## <a name="requirements"></a>Gereksinimler

|İşlevi/makrosu|Gerekli başlık (C)|Gerekli başlık (C++)|
|---------------------|---------------------------|-------------------------------|
|**fpclassify**|\<Math.h >|\<Math.h > veya \<cmath >|

**Fpclassify** makrosu ve **fpclassify** işlevleri uygun ISO C99 ve C ++ 11 özellikleri. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
