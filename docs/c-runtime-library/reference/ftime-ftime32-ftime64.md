---
title: _ftime, _ftime32, _ftime64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ftime64
- _ftime
- _ftime32
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
- _ftime32
- _ftime
- _ftime64
- ftime64
- ftime
- ftime32
dev_langs:
- C++
helpviewer_keywords:
- ftime64 function
- _ftime64 function
- current time
- _ftime function
- ftime function
- _ftime32 function
- ftime32 function
- time, getting current
ms.assetid: 96bc464c-3bcd-41d5-a212-8bbd836b814a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80695a24dbbab8e5407fadb5f427085c924a9095
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="ftime-ftime32-ftime64"></a>_ftime, _ftime32, _ftime64
Geçerli saati alır. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _ftime(   
   struct _timeb *timeptr   
);  
void _ftime32(   
   struct __timeb32 *timeptr   
);  
void _ftime64(   
   struct __timeb64 *timeptr   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `timeptr`  
 İşaretçi bir `_timeb`,`__timeb32` veya `__timeb64` yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 `_ftime` İşlevi geçerli yerel saat alır ve gösterdiği yapısı depolar `timeptr`. `_timeb`, `__timeb32`, Ve `__timeb64` yapıları SYS\Timeb.h içinde tanımlanmıştır. Aşağıdaki tabloda listelenen dört alanları içerir.  
  
 `dstflag`  
 Günışığından şu an için yerel saat dilimi etkinse, sıfır olmayan. (Bkz [_tzset](../../c-runtime-library/reference/tzset.md) günışığından belirleme hakkında ayrıntılı açıklamalar için.)  
  
 `millitm`  
 Saniyenin milisaniye cinsinden verin.  
  
 `time`  
 Gece yarısından beri geçen saniye süre (00: 00:00), 1 Ocak 1970'den itibaren Eşgüdümlü Evrensel Saat (UTC).  
  
 `timezone`  
 Dakika cinsinden fark westward, UTC ve yerel saat arasında taşıma. Değeri `timezone` genel değişkeni değerinden ayarlamak `_timezone` (bkz: `_tzset`).  
  
 `_ftime64`, kullanan `__timeb64` yapısı, 23:59:59, 31 Aralık 3000 UTC; yukarı ifade için dosya oluşturma tarihleri sağlarken `_ftime32` yalnızca ile 23:59:59 18 Ocak 2038, UTC tarihleri temsil eder. Gece yarısından, 1 Ocak 1970'ten, bu işlevler için tarih aralığını alt sınırdır.  
  
 `_ftime` eşdeğer olan `_ftime64` ve `_timeb` 64-bit saati içerir. Bu durum geçerlidir sürece `_USE_32BIT_TIME_T` , bu durumda eski yürürlükte; davranıştır tanımlanır `_ftime` 32-bit zamanını kullanır ve `_timeb` 32-bit saati içerir.  
  
 `_ftime` parametreleri doğrular. Null işaretçi olarak aktarılırsa `timeptr`, açıklandığı gibi geçersiz parametre işleyicisi işlevi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, işlevi ayarlar `errno` için `EINVAL`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`_ftime`|\<sys/Types.h > ve \<sys/timeb.h >|  
|`_ftime32`|\<sys/Types.h > ve \<sys/timeb.h >|  
|`_ftime64`|\<sys/Types.h > ve \<sys/timeb.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_ftime.c  
// compile with: /W3  
// This program uses _ftime to obtain the current  
// time and then stores this time in timebuffer.  
  
#include <stdio.h>  
#include <sys/timeb.h>  
#include <time.h>  
  
int main( void )  
{  
   struct _timeb timebuffer;  
   char timeline[26];  
   errno_t err;  
   time_t time1;  
   unsigned short millitm1;  
   short timezone1;  
   short dstflag1;  
  
   _ftime( &timebuffer ); // C4996  
   // Note: _ftime is deprecated; consider using _ftime_s instead  
  
   time1 = timebuffer.time;  
   millitm1 = timebuffer.millitm;  
   timezone1 = timebuffer.timezone;  
   dstflag1 = timebuffer.dstflag;  
  
   printf( "Seconds since midnight, January 1, 1970 (UTC): %I64d\n",   
   time1);  
   printf( "Milliseconds: %d\n", millitm1);  
   printf( "Minutes between UTC and local time: %d\n", timezone1);  
   printf( "Daylight savings time flag (1 means Daylight time is in "  
           "effect): %d\n", dstflag1);   
  
   err = ctime_s( timeline, 26, & ( timebuffer.time ) );  
   if (err)  
   {  
       printf("Invalid argument to ctime_s. ");  
   }  
   printf( "The time is %.19s.%hu %s", timeline, timebuffer.millitm,  
           &timeline[20] );  
}  
```  
  
```Output  
Seconds since midnight, January 1, 1970 (UTC): 1051553334  
Milliseconds: 230  
Minutes between UTC and local time: 480  
Daylight savings time flag (1 means Daylight time is in effect): 1  
The time is Mon Apr 28 11:08:54.230 2003  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman Yönetimi](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [damgasını, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)