---
title: fpclassify
ms.date: 04/05/2018
api_name:
- fpclassify
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
api_type:
- HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
ms.openlocfilehash: e9b5aa1f7dc20cc920a51c2c36371eb907469875
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957061"
---
# <a name="fpclassify"></a>fpclassify

Bağımsız değişkenin kayan nokta sınıflandırmasını döndürür.

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
Sınanacak kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**fpsınıflandır** *x*bağımsız değişkeninin kayan nokta sınıfını gösteren bir tamsayı değeri döndürür. Bu tablo, \<Math. h > tanımlanmış **fpsınıflandır**tarafından döndürülen olası değerleri gösterir.

|Değer|Açıklama|
|-----------|-----------------|
|**FP_NAN**|Sessiz, sinyal veya belirsiz NaN|
|**FP_INFINITE**|Pozitif veya negatif sonsuzluk|
|**FP_NORMAL**|Pozitif veya negatif normalleştirilmiş sıfır olmayan bir değer|
|**FP_SUBNORMAL**|Pozitif veya negatif bir eşit değer|
|**FP_ZERO**|Pozitif veya negatif sıfır değeri|

## <a name="remarks"></a>Açıklamalar

C 'de, **fpsınıflandır** bir makrodur; ' C++de, **fpsınıflandır** , **float**, **Double**veya **Long** **Double**bağımsız değişken türleri kullanılarak aşırı yüklenmiş bir işlevdir. Her iki durumda da, döndürülen değer, herhangi bir ara gösterimde değil, bağımsız değişken ifadesinin etkin türüne bağlıdır. Örneğin, normal bir **Double** veya **Long** **Double** değeri bir **float**'e dönüştürüldüğünde sonsuz, denormal veya sıfır değeri olabilir.

## <a name="requirements"></a>Gereksinimler

|İşlev/makro|Gerekli üst bilgi (C)|Gerekli üst bilgiC++()|
|---------------------|---------------------------|-------------------------------|
|**fpclassify**|\<Math. h >|\<Math. h > veya \<cmath >|

**Fpsınıflandır** makrosu ve **fpsınıflandır** Işlevleri ISO C99 ve c++ 11 belirtimlerine uyar. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
