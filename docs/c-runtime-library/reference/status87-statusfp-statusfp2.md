---
description: 'Hakkında daha fazla bilgi edinin: _status87, _statusfp, _statusfp2'
title: _status87, _statusfp, _statusfp2
ms.date: 04/05/2018
api_name:
- _statusfp2
- _statusfp
- _status87
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
ms.openlocfilehash: 98e99d01e7ad96e856de589e498bbd4ea794bdcb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97171146"
---
# <a name="_status87-_statusfp-_statusfp2"></a>_status87, _statusfp, _statusfp2

Kayan nokta durum sözcüğünü alır.

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _status87( void );
unsigned int _statusfp( void );
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)
```

### <a name="parameters"></a>Parametreler

*px86*<br/>
Bu adres, x87 kayan nokta birimi için durum sözcüğüyle doldurulur.

*pSSE2*<br/>
Bu adres, SSE2 kayan nokta birimi için durum sözcüğüyle doldurulur.

## <a name="return-value"></a>Dönüş Değeri

**_Status87** ve **_statusfp** için döndürülen değer içindeki bitler kayan nokta durumunu gösterir. FLOAT öğesine bakın. H **_statusfp** tarafından döndürülen bitlerin tanımına ilişkin dosya ekleme. Birçok matematik kitaplığı işlevi kayan nokta durum sözcüğünü tahmin edilemeyen sonuçlarla değiştirir. İyileştirme, **_status87**, **_statusfp** ve ilgili işlevlere yapılan çağrılar etrafında kayan nokta işlemlerini yeniden sıralayabilir, birleştirebilir ve ortadan kaldırabilir. Kayan nokta işlemlerini yeniden sıralayıp iyileştirmeleri engellemek için [/OD (Disable (Debug))](../../build/reference/od-disable-debug.md) derleyici seçeneğini veya [fenv_access](../../preprocessor/fenv-access.md) pragma yönergesini kullanın. Kayan nokta durum sözcüğünün bilinen durumları arasında daha az kayan nokta işlemi gerçekleştirilirse, **_clearfp** ve **_statusfp** ve ayrıca **_statusfp2** dönüş parametreleri değerleri daha güvenilirdir.

## <a name="remarks"></a>Açıklamalar

**_Statusfp** işlevi kayan nokta durum sözcüğünü alır. Durum sözcüğü, kayan nokta işlemci durumunun ve kayan nokta özel durum işleyicisi tarafından algılanan diğer koşulların bir birleşimidir — Örneğin, kayan nokta yığın taşması ve yetersiz. Maskesiz özel durumlar, sözcük sözcüğünün içeriği döndürülmeden önce denetlenir. Bu, çağıranın bekleyen özel durumların bilgilendirilmesi anlamına gelir. X86 platformlarında, **_statusfp** X87 ve SSE2 kayan nokta durumunun bir birleşimini döndürür. X64 platformlarında, döndürülen durum, SSE 'nin MXCSR durumuna göre belirlenir. ARM platformlarında **_statusfp** FPSCR kaydındaki durumu döndürür.

**_statusfp** , **_status87**'ın platformdan bağımsız, taşınabilir bir sürümüdür. Bu, Intel (x86) platformlarındaki **_status87** aynıdır ve ayrıca x64 ve ARM platformları tarafından desteklenir. Kayan nokta kodunuzun tüm mimarilere taşınabilir olmasını sağlamak için **_statusfp** kullanın. Yalnızca x86 platformlarını hedefliyorsanız, **_status87** ya da **_statusfp** kullanabilirsiniz.

Hem x87 hem de SSE2 kayan nokta işlemcisi olan yongalar (Pentium IV gibi) için **_statusfp2** önerilir. **_Statusfp2** için adresler, hem x87 hem de SSE2 kayan nokta işlemcisi için kayan nokta durum kelimesi kullanılarak doldurulur. X87 ve SSE2 kayan nokta işlemcileri destekleyen bir yonga için, **_statusfp** veya **_controlfp** kullanılıyorsa EM_AMBIGUOUS 1 olarak ayarlanır ve bu Işlem, x87 veya SSE2 kayan nokta durum sözcüğünü ifade ettiğinden eylem belirsizdir. **_Statusfp2** işlevi yalnızca x86 platformlarında desteklenir.

Ortak dil çalışma zamanı (CLR) yalnızca varsayılan kayan nokta duyarlığını desteklediğinden, bu işlevler [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) için yararlı değildir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_status87**, **_statusfp**, **_statusfp2**|\<float.h>|

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

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_control87, _controlfp, \_ _control87_2](control87-controlfp-control87-2.md)<br/>
