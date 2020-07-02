---
title: saat
ms.date: 11/04/2016
api_name:
- clock
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
- api-ms-win-crt-time-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- clock
helpviewer_keywords:
- processor time used, calculating
- time, calculating processor
- clock function
- processor time used
- calculating processor time used
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
ms.openlocfilehash: 660c97882151127cc6c1caa64bb27f5728f169fb
ms.sourcegitcommit: 8fd49f8ac20457710ceb5403ca46fc73cb3f95f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85737469"
---
# <a name="clock"></a>saat

Çağıran işlem tarafından kullanılan duvar saati saatini hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
clock_t clock( void );
```

## <a name="return-value"></a>Dönüş Değeri

İşlemin başlangıcında, saniye başına **CLOCKS_PER_SEC** birim cınsınden ölçülen CRT başlatmasından bu yana geçen süre. Geçen süre kullanılamıyorsa veya **clock_t** türü olarak kaydedilebilen en uzun pozitif süreyi aşarsa, işlev değeri döndürür `(clock_t)(-1)` .

## <a name="remarks"></a>Açıklamalar

**Clock** işlevi, işlem BAŞLANGıCı sırasında CRT başlatmadan bu yana ne kadar duvar saati saati geçtiğini söyler. Bu işlevin, dönüş değeri olarak net CPU süresini belirten ISO C 'ye kesinlikle uyumlu olmadığına unutmayın. CPU sürelerini almak için Win32 [GetProcessTimes](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getprocesstimes) işlevini kullanın. Geçen süreyi saniye cinsinden öğrenmek için, makro **CLOCKS_PER_SEC** **saat** işlevi tarafından döndürülen değeri bölün.

Yeterli zaman verildiğinde, **saat** tarafından döndürülen değer **clock_t**en büyük pozitif değeri aşabilir. İşlem daha uzun süre çalıştığında, **clock** `(clock_t)(-1)` ISO C99 Standard (7.23.2.1) ve ISO C11 standardı (7.27.2.1) tarafından belirtilen şekilde saat tarafından döndürülen değer her zaman olur. Microsoft **clock_t** **uzun**, imzalanmış 32 bitlik bir tamsayı ve **CLOCKS_PER_SEC** makro 1000 olarak tanımlanır. Bu, 2147483,647 saniyelik bir maksimum **saat** işlevi dönüş değeri veya yaklaşık 24,8 gün verir. Bu süreden daha uzun süredir çalışan işlemlerde **saatin** döndürdüğü değere güvenmeyin. Birkaç yıla ait işlem geçen süreleri kaydetmek için 64 bit [zaman](time-time32-time64.md) Işlevini veya Windows [QueryPerformanceCounter](/windows/win32/api/profileapi/nf-profileapi-queryperformancecounter) işlevini kullanabilirsiniz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**saat**|\<time.h>|

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

// Pauses for a specified number of clock cycles.
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
