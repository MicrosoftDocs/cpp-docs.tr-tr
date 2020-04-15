---
title: nan, nanf, nanl
ms.date: 4/2/2020
api_name:
- nanf
- nan
- nanl
- _o_nan
- _o_nanf
- _o_nanl
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- nan
- nanl
- nanf
helpviewer_keywords:
- nan function
- nanf function
- nanl function
ms.assetid: 790e9158-80ab-43e0-8f5a-096198553fd9
ms.openlocfilehash: d8f0db5020f274de27f7f1bbf3a76659eae568e4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338636"
---
# <a name="nan-nanf-nanl"></a>nan, nanf, nanl

Sessiz bir NaN değeri verir.

## <a name="syntax"></a>Sözdizimi

```C
double nan( const char* input );
float nanf( const char* input );
long double nanl( const char* input );
```

### <a name="parameters"></a>Parametreler

*Giriş*<br/>
Dize değeri.

## <a name="return-value"></a>Dönüş Değeri

**Nan** işlevleri sessiz bir NaN değeri döndürdü.

## <a name="remarks"></a>Açıklamalar

**Nan** işlevleri sessiz (sinyal vermeyen) NaN'a karşılık gelen kayan nokta değeri döndürer. *Giriş* değeri yoksayılır. Bir NaN'nin çıktı için nasıl temsil edildiği hakkında bilgi için [printf, _printf_l, wprintf, _wprintf_l'](printf-printf-l-wprintf-wprintf-l.md)e bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgi|C++ üstbilgi|
|--------------|--------------|------------------|
|**nan**, **nanf**, **nan**|\<math.h>|\<cmath> \<veya math.h>|

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
