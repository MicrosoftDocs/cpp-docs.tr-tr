---
title: nan, nanf, nanl
ms.date: 94/05/2018
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
ms.openlocfilehash: 22b0e14094a0b6f0f3571c4d7551552210177a22
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610268"
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
|**NaN**, **nanf**, **nanl**|\<Math.h >|\<cmath > veya \<math.h >|

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_finite, _finitef](finite-finitef.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
