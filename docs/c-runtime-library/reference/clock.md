---
title: saat | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: clock
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
f1_keywords: clock
dev_langs: C++
helpviewer_keywords:
- processor time used, calculating
- time, calculating processor
- clock function
- processor time used
- calculating processor time used
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 32b0f1bdd4e7db4f870aa23919ab426335d3f446
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="clock"></a>saat
Arama işlemi tarafından kullanılan duvar saati süresi hesaplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
clock_t clock( void );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
Başlangıç CRT başlatma işleminin bu yana geçen süre ölçülen `CLOCKS_PER_SEC` saniye başına birim. Geçen süre kullanılamıyor veya olarak kayıtlı maksimum pozitif süreyi aştı bir `clock_t` türü, işlev değeri döndürür `(clock_t)(-1)`.   
  
## <a name="remarks"></a>Açıklamalar  
`clock` İşlevi söyler CRT başlatma işlemi başlangıcı sırasında bu yana ne kadar duvar saati süresi geçti. Bu işlev kesinlikle dönüş değeri olarak net CPU süresi belirtir ISO C uymuyor olduğunu unutmayın. CPU sürelerini almak için Win32 kullanın [GetProcessTimes](https://msdn.microsoft.com/library/windows/desktop/ms683223) işlevi. Saniye cinsinden geçen süreyi belirlemek için tarafından döndürülen değer bölmek `clock` makrosu işleviyle `CLOCKS_PER_SEC`.  
  
Yeterli zamanı olduğunda döndürülen değer tarafından `clock` en büyük pozitif değerini aşabilir `clock_t`. İşlemin çalıştırdığınızda uzun tarafından döndürülen değer `clock` her zaman `(clock_t)(-1)`, ISO C99 standart (7.23.2.1) ve ISO C11 standart (7.27.2.1) tarafından belirtildiği gibi. Microsoft uygulayan `clock_t` olarak bir `long`, imzalanmış bir 32 bit tamsayı ve `CLOCKS_PER_SEC` makrosu 1000 tanımlanır. Bu en verir `clock` işlev 2147483.647 saniye veya yaklaşık 24.8 gün dönüş değeri. Tarafından döndürülen değer kullanmayın `clock` bu süreyi daha uzun süre çalışan işlemleri içinde. 64-bit kullanabilirsiniz `time` işlevi veya Windows [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904) işlevi kayıt işlemi geçen saatler birçok yıldır.  

## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`clock`|\<time.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman Yönetimi](../../c-runtime-library/time-management.md)   
 [difftime, _difftime32, _difftime64](../../c-runtime-library/reference/difftime-difftime32-difftime64.md)   
 [_time64 _time32, saat](../../c-runtime-library/reference/time-time32-time64.md)