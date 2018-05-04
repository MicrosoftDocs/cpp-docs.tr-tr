---
title: _fpreset | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fpreset
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
- _fpreset
- fpreset
dev_langs:
- C++
helpviewer_keywords:
- fpreset function
- floating-point numbers, resetting math package
- _fpreset function
ms.assetid: f31c6a04-b464-4f07-a7c4-42133360e328
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b550df3e43b56038ae6d1b2d6695c86d90c3499
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fpreset"></a>_fpreset

Kayan nokta paket sıfırlar.

## <a name="syntax"></a>Sözdizimi

```C
void _fpreset( void );
```

## <a name="remarks"></a>Açıklamalar

**_Fpreset** işlevi kayan nokta matematik paketini yeniden başlatır. **_fpreset** genellikle kullanılan **sinyal**, **sistem**, veya **_exec** veya **_spawn** işlevleri. Kayan nokta hata sinyalleri bir program yakalar varsa (**SIGFPE**) ile **sinyal**, harekete geçirerek, kayan nokta hataları güvenle kurtarabilirsiniz **_fpreset** ve kullanma**longjmp**.

Bu işlev ile derleme yapılırken kullanım dışıdır [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) çünkü ortak dil çalışma zamanı yalnızca varsayılan kayan nokta duyarlık destekler.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fpreset**|\<float.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fpreset.c
// This program uses signal to set up a
// routine for handling floating-point errors.

#include <stdio.h>
#include <signal.h>
#include <setjmp.h>
#include <stdlib.h>
#include <float.h>
#include <math.h>
#include <string.h>

jmp_buf mark;              // Address for long jump to jump to
int     fperr;             // Global error number

void __cdecl fphandler( int sig, int num );   // Prototypes
void fpcheck( void );

int main( void )
{
   double n1 = 5.0;
   double n2 = 0.0;
   double r;
   int jmpret;

   // Unmask all floating-point exceptions.
    _control87( 0, _MCW_EM );
   // Set up floating-point error handler. The compiler
   // will generate a warning because it expects
   // signal-handling functions to take only one argument.
   if( signal( SIGFPE, (void (__cdecl *)(int)) fphandler ) == SIG_ERR )
    {
       fprintf( stderr, "Couldn't set SIGFPE\n" );
       abort();
    }

   // Save stack environment for return in case of error. First
   // time through, jmpret is 0, so true conditional is executed.
   // If an error occurs, jmpret will be set to -1 and false
   // conditional will be executed.
   jmpret = setjmp( mark );
   if( jmpret == 0 )
   {
      printf( "Dividing %4.3g by %4.3g...\n", n1, n2 );
      r = n1 / n2;
      // This won't be reached if error occurs.
      printf( "\n\n%4.3g / %4.3g = %4.3g\n", n1, n2, r );

      r = n1 * n2;
      // This won't be reached if error occurs.
      printf( "\n\n%4.3g * %4.3g = %4.3g\n", n1, n2, r );
   }
   else
      fpcheck();
}
// fphandler handles SIGFPE (floating-point error) interrupt. Note
// that this prototype accepts two arguments and that the
// prototype for signal in the run-time library expects a signal
// handler to have only one argument.
//
// The second argument in this signal handler allows processing of
// _FPE_INVALID, _FPE_OVERFLOW, _FPE_UNDERFLOW, and
// _FPE_ZERODIVIDE, all of which are Microsoft-specific symbols
// that augment the information provided by SIGFPE. The compiler
// will generate a warning, which is harmless and expected.

void fphandler( int sig, int num )
{
   // Set global for outside check since we don't want
   // to do I/O in the handler.
   fperr = num;

   // Initialize floating-point package. */
   _fpreset();

   // Restore calling environment and jump back to setjmp. Return
   // -1 so that setjmp will return false for conditional test.
   longjmp( mark, -1 );
}

void fpcheck( void )
{
   char fpstr[30];
   switch( fperr )
   {
   case _FPE_INVALID:
       strcpy_s( fpstr, sizeof(fpstr), "Invalid number" );
       break;
   case _FPE_OVERFLOW:
       strcpy_s( fpstr, sizeof(fpstr), "Overflow" );

       break;
   case _FPE_UNDERFLOW:
       strcpy_s( fpstr, sizeof(fpstr), "Underflow" );
       break;
   case _FPE_ZERODIVIDE:
       strcpy_s( fpstr, sizeof(fpstr), "Divide by zero" );
       break;
   default:
       strcpy_s( fpstr, sizeof(fpstr), "Other floating point error" );
       break;
   }
   printf( "Error %d: %s\n", fperr, fpstr );
}
```

```Output
Dividing    5 by    0...
Error 131: Divide by zero
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[signal](signal.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
