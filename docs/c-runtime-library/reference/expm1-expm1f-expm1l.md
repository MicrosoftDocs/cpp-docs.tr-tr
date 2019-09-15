---
title: expm1, expm1f, expm1l
ms.date: 04/05/2018
api_name:
- expm1l
- expm1
- expm1f
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- expm1l
- expm1
- expm1f
helpviewer_keywords:
- expm1f function
- expm1l function
- expm1 function
ms.assetid: 2a4dd2d9-370c-42b0-9067-0625efa272e0
ms.openlocfilehash: 77bd44975e97cc646f7d2fd100d86b6661b8c2e9
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941540"
---
# <a name="expm1-expm1f-expm1l"></a>expm1, expm1f, expm1l

Değerin taban-e üssünü hesaplar, eksi bir değer.

## <a name="syntax"></a>Sözdizimi

```C
double expm1(
   double x
);
float expm1(
   float x
);  // C++ only
long double expm1(
   long double x
);  // C++ only
float expm1f(
   float x
);
long double expm1l(
   long double x
);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Kayan nokta üstel değeri.

## <a name="return-value"></a>Dönüş Değeri

**Expm1** işlevleri, başarılı olursa e<sup>x</sup> -1 ' i temsil eden bir kayan nokta değeri döndürür. Taşma üzerinde **Expm1** **HUGE_VAL**döndürür, **expm1f** , **HUGE_VALF**döndürür, **expm1l** **HUGE_VALL**döndürür ve **errno** , **ERANGE**olarak ayarlanır. Dönüş kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Aşırı C++ yüklemeye izin verdiğinden, **float** ve **Long** **Double** değerleri alıp döndüren **expm1** aşırı yüklerini çağırabilirsiniz. C programında, **expm1** her zaman bir **Double**alır ve döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**expm1**, **expm1f**, **expm1l**|\<Math. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)<br/>
[pow, powf, powl](pow-powf-powl.md)<br/>
