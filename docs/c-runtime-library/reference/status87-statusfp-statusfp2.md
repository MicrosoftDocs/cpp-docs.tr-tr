---
title: _status87, _statusfp, _statusfp2 | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69297d7ff1e3ec40cfe4fc22dec86c356d1697d4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="status87-statusfp-statusfp2"></a>_status87, _statusfp, _statusfp2

Kayan nokta durum sözcüğünü alır.

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _status87( void );
unsigned int _statusfp( void );
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)
```

### <a name="parameters"></a>Parametreler

*px86*<br/>
Bu adres x87 durum sözcüğünü doldurulup kayan nokta birim.

*pSSE2*<br/>
Bu adres SSE2 kayan nokta birimi için durum word ile doldurulur.

## <a name="return-value"></a>Dönüş Değeri

İçin **_status87** ve **_statusfp**, döndürülen değer bitleri kayan nokta durumunu gösterir. FLOAT bakın. H içerme dosyası tarafından döndürülen BITS tanımı için **_statusfp**. Birçok matematik kitaplık işlevleri kayan nokta durum sözcüğünü öngörülemeyen sonuçlara ile değiştirin. En iyi duruma getirme yeniden sıralamak, birleştirmek ve kayan nokta işlemleri çağrıları geçici ortadan **_status87**, **_statusfp**ve ilgili işlevleri. Kullanım [/Od (devre dışı bırak (Hata Ayıkla))](../../build/reference/od-disable-debug.md) derleyici seçeneği veya [fenv_access](../../preprocessor/fenv-access.md) kayan nokta işlemlerini yeniden sıralamak en iyi duruma getirme önlemek için pragma yönergesi. Değerlerin **_clearfp** ve **_statusfp**ve ayrıca dönüş parametrelerinin **_statusfp2**, daha az kayan nokta işlemleri gerçekleştirdiyseniz daha güvenilir değil kayan nokta durum sözcüğünü bilinen durumlar arasında.

## <a name="remarks"></a>Açıklamalar

**_Statusfp** işlevi kayan nokta durum sözcüğünü alır. Durum sözcüğünü kayan nokta işlemci durumu ve kayan nokta özel durum işleyici tarafından algılanan başka koşullar bir birleşimidir — Örneğin, kayan nokta yığın taşması ve yetersiz. Durum sözcüğünü içeriğini döndürmeden önce maskelenmemiş özel durumlar için denetlenir. Bu özel durumlar olan arayan, bilgilendirilir anlamına gelir. X86 üzerinde platformları, **_statusfp** x87 ve SSE2 kayan nokta durum birleşimini döndürür. X64 üzerinde platformları, döndürülen durum SSE'ın MXCSR durumuna dayanır. ARM platformlarda **_statusfp** FPSCR kasadan durumu döndürür.

**_statusfp** bir platformdan bağımsız, taşınabilir sürümü **_status87**. Aynı **_status87** Intel (x86) platformlarda ve ayrıca x64 ve ARM platformlar tarafından desteklenir. Kayan nokta kodunuzu tüm mimarileri taşınabilir olduğundan emin olmak için kullanmak **_statusfp**. X86 yalnızca hedefliyorsanız platformları, kullanabilirsiniz **_status87** veya **_statusfp**.

Öneririz **_statusfp2** bir x87 ve SSE2 kayan nokta işlemci yongaları (örneğin, Pentium IV) için. İçin **_statusfp2**, adresleri x87 veya SSE2 kayan nokta işlemci için kayan nokta durum sözcüğünü kullanarak doldurulur. X87 ve SSE2 kayan nokta işlemcileri destekleyen bir yonga EM_AMBIGUOUS 1 ise ayarlanır **_statusfp** veya **_controlfp** kullanılır ve x87 veya SSE2 başvurduğundan eylemi belirsiz kayan nokta durum sözcüğünü. **_Statusfp2** işlevi yalnızca x86 üzerinde desteklenen platformlar.

Bu işlevler için yararlı değildir [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) çünkü ortak dil çalışma zamanı (CLR) yalnızca varsayılan kayan nokta duyarlık destekler.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_status87**, **_statusfp**, **_statusfp2**|\<float.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
