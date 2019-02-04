---
title: nan, nanf, nanl
ms.date: 01/31/2019
apiname:
- nanf
- nan
- nanl
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
- nan
- nanl
- nanf
helpviewer_keywords:
- nan function
- nanf function
- nanl function
ms.assetid: 790e9158-80ab-43e0-8f5a-096198553fd9
ms.openlocfilehash: df3985a28bc351bdf196c0a1561bd3e25b661c87
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703002"
---
# <a name="nan-nanf-nanl"></a>nan, nanf, nanl

Sessiz bir NaN değerini döndürür.

## <a name="syntax"></a>Sözdizimi

```C
double nan( const char* input );
float nanf( const char* input );
long double nanl( const char* input );
```

### <a name="parameters"></a>Parametreler

*Giriş*<br/>
Bir dize değeri.

## <a name="return-value"></a>Dönüş Değeri

**Nan** işlevleri sessiz bir NaN değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**Nan** işlevler (sinyali gönderiliyor) sessiz bir NaN karşılık gelen bir kayan nokta değeri döndürür. *Giriş* değer yoksayılır. Çıkış için bir NaN nasıl temsil edildiğini hakkında daha fazla bilgi için bkz: [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**nan**, **nanf**, **nanl**|\<Math.h >|\<cmath > veya \<math.h >|

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
