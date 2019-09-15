---
title: _clear87, _clearfp
ms.date: 04/05/2018
api_name:
- _clearfp
- _clear87
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- clearfp
- _clearfp
- _clear87
- clear87
helpviewer_keywords:
- clearing floating point status word
- clearfp function
- _clear87 function
- _clearfp function
- clear87 function
ms.assetid: 72d24a70-7688-4793-ae09-c96d33fcca52
ms.openlocfilehash: 4ca49895b881d9e307c1116681bc36f86b167c25
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942965"
---
# <a name="_clear87-_clearfp"></a>_clear87, _clearfp

Kayan nokta durum sözcüğünü alır ve temizler.

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _clear87( void );
unsigned int _clearfp( void );
```

## <a name="return-value"></a>Dönüş Değeri

Döndürülen değer içindeki bitler, **_clear87** veya **_clearfp**çağrısından önce kayan nokta durumunu gösterir. **_Clear87**tarafından döndürülen bitlerin tüm tanımları için bkz. float. h. Matematik kitaplığı işlevlerinin birçoğu, 8087/80287 durum sözcüğünü tahmin edilemeyen sonuçlarla değiştirir. Kayan nokta durum sözcüğünün bilinen durumları arasında daha az kayan nokta işlemi gerçekleştirildiğinde, **_clear87** ve **_status87** ' den döndürülen değerler daha güvenilir hale gelir.

## <a name="remarks"></a>Açıklamalar

**_Clear87** işlevi, kayan nokta durumu sözcükteki özel durum bayraklarını temizler, meşgul biti 0 olarak ayarlar ve durum sözcüğünü döndürür. Kayan nokta durum sözcüğü, 8087/80287 durum sözcüğünün ve kayan nokta yığın taşması ve yetersiz kalması gibi 8087/80287 özel durum işleyicisi tarafından algılanan diğer koşulların bir birleşimidir.

**_clearfp** , **_clear87** yordamının platformdan bağımsız, taşınabilir bir sürümüdür. Intel (x86) platformlarındaki **_clear87** ile aynıdır ve ayrıca x64 ve ARM platformları tarafından desteklenir. Kayan nokta kodunuzun x64 ve ARM 'e taşınabilir olduğundan emin olmak için **_clearfp**kullanın. Yalnızca x86 platformlarını hedefliyorsanız, **_clear87** ya da **_clearfp**' yi kullanabilirsiniz.

Ortak dil çalışma zamanı yalnızca varsayılan kayan nokta duyarlığını desteklediğinden, bu işlevler [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ile derlenirken kullanım dışıdır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_clear87**|\<float. h >|
|**_clearfp**|\<float. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_clear87.c
// compile with: /Od

// This program creates various floating-point
// problems, then uses _clear87 to report on these problems.
// Compile this program with Optimizations disabled (/Od).
// Otherwise the optimizer will remove the code associated with
// the unused floating-point values.
//

#include <stdio.h>
#include <float.h>

int main( void )
{
   double a = 1e-40, b;
   float x, y;

   printf( "Status: %.4x - clear\n", _clear87()  );

   // Store into y is inexact and underflows:
   y = a;
   printf( "Status: %.4x - inexact, underflow\n", _clear87() );

   // y is denormal:
   b = y;
   printf( "Status: %.4x - denormal\n", _clear87() );
}
```

```Output
Status: 0000 - clear
Status: 0003 - inexact, underflow
Status: 80000 - denormal
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
