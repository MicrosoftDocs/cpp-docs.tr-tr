---
title: _status87, _statusfp, _statusfp2
ms.date: 04/05/2018
apiname:
- _statusfp2
- _statusfp
- _status87
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
- _statusfp2
- _statusfp
- statusfp2
- _status87
- status87
- statusfp
helpviewer_keywords:
- floating-point functions, getting status word
- floating-point numbers, status word
- status87 function
- status word, getting floating point
- statusfp function
- _statusfp function
- _statusfp2 function
- statusfp2 function
- _status87 function
- floating-point functions
- status word
ms.assetid: 7ef963fa-b1fb-429d-94d6-fbf282ab7432
ms.openlocfilehash: 271c28dd4e267e5b3b702858cc398689e3e35d6f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597537"
---
# <a name="status87-statusfp-statusfp2"></a>_status87, _statusfp, _statusfp2

Kayan nokta durumu sözcüğünü alır.

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _status87( void );
unsigned int _statusfp( void );
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)
```

### <a name="parameters"></a>Parametreler

*px86*<br/>
Bu adres x87 için durum sözcüğüyle doldurulur kayan nokta birimi.

*pSSE2*<br/>
Bu adres, SSE2 kayan nokta birimi için durum sözcüğüyle doldurulur.

## <a name="return-value"></a>Dönüş Değeri

İçin **_status87** ve **_statusfp**, döndürülen değerdeki bitler kayan nokta durumunu gösterir. FLOAT bakın. H içerme dosyası tarafından döndürülen bitlerin bir tanımı için **_statusfp**. Çoğu matematik kitaplığı işlevi kayan nokta durumu sözcüğünü beklenmeyen sonuçlarla değiştirir. İyileştirme yeniden sıralamak, birleştirmek ve çağrıları etrafında bir kayan nokta işlemlerini ortadan **_status87**, **_statusfp**ve ilgili işlevleri. Kullanım [/Od (devre dışı bırak (Hata Ayıkla))](../../build/reference/od-disable-debug.md) derleyici seçeneği veya [fenv_access](../../preprocessor/fenv-access.md) pragma yönergesi, kayan nokta işlemlerini yeniden sıralayabilir iyileştirmeleri önlemek için. Değerlerin **_clearfp** ve **_statusfp**ve ayrıca dönüş parametreleri **_statusfp2**, daha az kayan nokta işlemleri gerçekleştirdiyseniz daha güvenilirdir kayan nokta durum sözcüğünün bilinen durumları arasında.

## <a name="remarks"></a>Açıklamalar

**_Statusfp** işlevi kayan nokta durumu sözcüğünü alır. Durum sözcüğü kayan nokta işlemci durumu ve kayan nokta özel durum işleyici tarafından saptanan diğer durumların bir birleşimidir — Örneğin, kayan nokta yığın taşması veya yetersiz. Durum sözcüğü içeriğini döndürmeden önce maskelenmemiş özel durumlar denetlenir. Bu, çağırana, bekleyen özel durumlar bilgisinin verildiği anlamına gelir. X86 platformları **_statusfp** x87 ve SSE2 kayan nokta durumunun bir bileşimini döndürür. X64 platformlarında, döndürülen durum SSE'nin MXCSR durumu temel alır. ARM platformlarında, **_statusfp** FPSCR yazmacından durumu döndürür.

**_statusfp** bir platformdan bağımsız, taşınabilir sürümü **_status87**. Aynıdır **_status87** Intel (x86) platformlarda ve x64 ve ARM platformları tarafından da desteklenir. Kayan nokta kodunuzun tüm mimariler için taşınabilir olduğundan emin olmak için kullanın **_statusfp**. Yalnızca x86 hedefliyorsanız platformları kullanabilirsiniz **_status87** veya **_statusfp**.

Öneririz **_statusfp2** için hem x x87 hem de SSE2 kayan noktalı işlemci yongaları (örneğin, Pentium IV). İçin **_statusfp2**, adresleri x87 veya SSE2 kayan nokta işlemci için kayan nokta durumu sözcüğünü kullanarak doldurulur. X87 ve SSE2 kayan nokta işlemcileri destekleyen bir yonga için em_ambıguous 1 olarak ayarlanır **_statusfp** veya **_controlfp** kullanılır ve bu x87 veya SSE2 başvurabileceği eylemi belirsiz kayan nokta durumu sözcüğünü. **_Statusfp2** işlevi yalnızca x86 üzerinde desteklenen platformlar.

Bu işlevler için yararlı değildir [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) çünkü ortak dil çalışma zamanı (CLR) yalnızca varsayılan kayan nokta duyarlığını destekler.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_status87**, **_statusfp**, **_statusfp2**|\<float.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_statusfp.c
// Build by using: cl /W4 /Ox /nologo crt_statusfp.c
// This program creates various floating-point errors and
// then uses _statusfp to display messages that indicate these problems.

#include <stdio.h>
#include <float.h>
#pragma fenv_access(on)

double test( void )
{
   double a = 1e-40;
   float b;
   double c;

   printf("Status = 0x%.8x - clear\n", _statusfp());

   // Assignment into b is inexact & underflows:
   b = (float)(a + 1e-40);
   printf("Status = 0x%.8x - inexact, underflow\n", _statusfp());

   // c is denormal:
   c = b / 2.0;
   printf("Status = 0x%.8x - inexact, underflow, denormal\n",
            _statusfp());

   // Clear floating point status:
   _clearfp();
   return c;
}

int main(void)
{
   return (int)test();
}
```

```Output
Status = 0x00000000 - clear
Status = 0x00000003 - inexact, underflow
Status = 0x00080003 - inexact, underflow, denormal
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
