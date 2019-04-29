---
title: _clear87, _clearfp
ms.date: 04/05/2018
apiname:
- _clearfp
- _clear87
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 4148f85d82a4210033686455c73046081832e3c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340559"
---
# <a name="clear87-clearfp"></a>_clear87, _clearfp

Alır ve kayan nokta durumu sözcüğünü temizler.

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _clear87( void );
unsigned int _clearfp( void );
```

## <a name="return-value"></a>Dönüş Değeri

Döndürülen değerdeki bitler kayan nokta durumu çağırmadan önce belirtmek **_clear87** veya **_clearfp**. Tarafından döndürülen bitlerin tam tanımı için **_clear87**, bkz. Float.h. Çoğu matematik kitaplığı işlevi 8087/80287 durumu sözcüğünü beklenmeyen sonuçlarla değiştirir. Değerlerin **_clear87** ve **_status87** kayan nokta durum sözcüğünün bilinen durumları arasında daha az kayan nokta işlemleri gerçekleştirilir daha güvenilir hale gelir.

## <a name="remarks"></a>Açıklamalar

**_Clear87** işlevi kayan nokta durumu sözcüğünü özel durumu bayrakları temizler, meşgul bit 0 olarak ayarlar ve durum sözcüğü döndürür. Kayan nokta durumu sözcüğünü 8087/80287 durum sözcüğü ve kayan nokta yığın taşması veya yetersiz kalması gibi 8087/80287 özel durum işleyici tarafından saptanan diğer durumların birleşimidir.

**_clearfp** bir platformdan bağımsız, taşınabilir sürümü **_clear87** yordamı. Aynıdır **_clear87** Intel (x86) platformlarda ve x64 ve ARM platformları tarafından da desteklenir. Kayan nokta kodunuzun x64 ve ARM için taşınabilir olduğundan emin olmak için kullanın **_clearfp**. Yalnızca x86 hedefliyorsanız platformları kullanabilirsiniz **_clear87** veya **_clearfp**.

Bu işlevler ile derleme yaparken kullanım dışı bırakılmıştır [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) çünkü ortak dil çalışma zamanı yalnızca varsayılan kayan nokta duyarlığını destekler.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_clear87**|\<float.h >|
|**_clearfp**|\<float.h >|

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
