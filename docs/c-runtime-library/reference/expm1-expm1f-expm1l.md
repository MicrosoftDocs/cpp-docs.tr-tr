---
title: expm1, expm1f, expm1l
ms.date: 04/05/2018
apiname:
- expm1l
- expm1
- expm1f
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
- expm1l
- expm1
- expm1f
helpviewer_keywords:
- expm1f function
- expm1l function
- expm1 function
ms.assetid: 2a4dd2d9-370c-42b0-9067-0625efa272e0
ms.openlocfilehash: 5971f879ecef7d4fa1027849cc44d598e877b5f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441073"
---
# <a name="expm1-expm1f-expm1l"></a>expm1, expm1f, expm1l

Tabanında üssü eksi bir değerini hesaplar.

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
Kayan nokta üs değeri.

## <a name="return-value"></a>Dönüş Değeri

**Expm1** işlevler e temsil eden bir kayan nokta değeri döndürür<sup>x</sup> - 1, başarılı olursa. Taşma **expm1** döndürür **HUGE_VAL**, **expm1f** döndürür **HUGE_VALF**, **expm1l** döndürür **HUGE_VALL**, ve **errno** ayarlanır **ERANGE**. Dönüş kodları hakkında daha fazla bilgi için bkz. [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **expm1** alan ve getiren **float** ve **uzun** **çift** değerleri. C programında **expm1** her zaman alan ve döndüren bir **çift**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**expm1**, **expm1f**, **expm1l**|\<Math.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)<br/>
[pow, powf, powl](pow-powf-powl.md)<br/>
