---
title: saat | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- clock
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- clock
dev_langs:
- C++
helpviewer_keywords:
- processor time used, calculating
- time, calculating processor
- clock function
- processor time used
- calculating processor time used
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd4b399900802d110ff5746a0ccb2424ba40e6b5
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209872"
---
# <a name="clock"></a>saat

Çağırma işlemi tarafından kullanılan duvar saati zamanı hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
clock_t clock( void );
```

## <a name="return-value"></a>Dönüş Değeri

Başında CRT başlatma işleminin bu yana geçen süreyi cinsinden ölçülen **CLOCKS_PER_SEC** birimi / saniye. Geçen süreyi kullanılamıyor veya olarak kayıtlı pozitif en uzun süreyi aştı bir **clock_t** türü, işlev değeri döndürür `(clock_t)(-1)`.

## <a name="remarks"></a>Açıklamalar

**Saat** işlevi söyler CRT başlatma işlemi başlangıcı sırasında bu yana ne kadar duvar saati süresi geçti. Bu işlev kesinlikle net CPU süresi dönüş değeri olarak belirtir. ISO C uygun değil olduğunu unutmayın. CPU süreleri elde etmek için Win32 kullanın [GetProcessTimes](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getprocesstimes) işlevi. Tarafından döndürülen değeri, geçen süreyi saniye cinsinden belirlemek için bölme **saat** makro işleviyle **CLOCKS_PER_SEC**.

Yeterli zaman göz önünde bulundurulduğunda, döndürülen değer tarafından **saat** en büyük pozitif değerini aşabilir **clock_t**. İşlem çalıştırdığınızda uzun tarafından döndürülen değer **saat** her zaman `(clock_t)(-1)`ISO C99 standardında (7.23.2.1) ve ISO C11 standart (7.27.2.1) tarafından belirtilen. Microsoft uygulayan **clock_t** olarak bir **uzun**, imzalı bir 32 bit tamsayı ve **CLOCKS_PER_SEC** makrosu, 1000 tanımlanır. Bu en fazla verir **saat** işlev dönüş değeri 2147483.647 saniye veya yaklaşık 24.8 gün. Tarafından döndürülen değer güvenmeyin **saat** bu süreyi daha uzun süre çalışan işlemler de. 64 bit kullanabilirsiniz [zaman](time-time32-time64.md) işlevi ya da Windows [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904) yıllardır geçen sürelerinin kayıt işlemi için işlevi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**clock**|\<TIME.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_clock.c
// This sample uses clock() to 'sleep' for three
// seconds, then determines how long it takes
// to execute an empty loop 600000000 times.

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

// Pauses for a specified number of milliseconds.
void do_sleep( clock_t wait )
{
   clock_t goal;
   goal = wait + clock();
   while( goal > clock() )
      ;
}

const long num_loops = 600000000L;

int main( void )
{
   long    i = num_loops;
   clock_t start, finish;
   double  duration;

   // Delay for a specified time.
   printf( "Delay for three seconds\n" );
   do_sleep( (clock_t)3 * CLOCKS_PER_SEC );
   printf( "Done!\n" );

   // Measure the duration of an event.
   start = clock();
   while( i-- )
      ;
   finish = clock();
   duration = (double)(finish - start) / CLOCKS_PER_SEC;
   printf( "Time to do %ld empty loops is ", num_loops );
   printf( "%2.3f seconds\n", duration );
}
```

```Output
Delay for three seconds
Done!
Time to do 600000000 empty loops is 1.354 seconds
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[difftime, _difftime32, _difftime64](difftime-difftime32-difftime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
