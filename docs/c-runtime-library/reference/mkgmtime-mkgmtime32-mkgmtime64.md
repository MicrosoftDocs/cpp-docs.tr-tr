---
title: _mkgmtime, _mkgmtime32, _mkgmtime64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _mkgmtime32
- _mkgmtime64
- _mkgmtime
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
- _mkgmtime64
- mkgmtime32
- _mkgmtime32
- mkgmtime
- mkgmtime64
- _mkgmtime
dev_langs:
- C++
helpviewer_keywords:
- mkgmtime32 function
- time functions
- mkgmtime function
- _mkgmtime function
- converting times
- mkgmtime64 function
- _mkgmtime64 function
- _mkgmtime32 function
- time, converting
ms.assetid: b4ca2b67-e198-4f43-b3e2-e8ad6bd01867
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7eec9b123c47b13c73836fd41a2c490951e4fecd
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="mkgmtime-mkgmtime32-mkgmtime64"></a>_mkgmtime, _mkgmtime32, _mkgmtime64
Tarafından temsil edilen bir UTC saati dönüştüren bir `tm struct` UTC saati için temsil ettiği bir `time_t` türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      time_t _mkgmtime(  
   struct tm* timeptr  
);  
__time32_t _mkgmtime32(  
   struct tm* timeptr  
);  
__time64_t _mkgmtime64(  
   struct tm* timeptr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `timeptr`  
 UTC saati olarak gösteren bir işaretçi bir `struct tm` dönüştürülemiyor.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Türünde bir miktar `__time32_t` veya `__time64_t` saniye sayısını temsil eden geçen yarısından, 1 Ocak 1970'den itibaren Eşgüdümlü Evrensel Saat (UTC). Tarih aralık dışında ise (Açıklamalar bölümüne bakın) veya giriş geçerli bir saat yorumlanamayan, dönüş değeri -1'dir.  
  
## <a name="remarks"></a>Açıklamalar  
 `_mkgmtime32` Ve `_mkgmtime64` işlevleri dönüştürmek için UTC saati bir `__time32_t` veya `__time64_t` UTC saatini temsil eden tür. UTC saati yerel saate dönüştürmek için `mktime`, `_mktime32`, ve `_mktime64` yerine.  
  
 `_mkgmtime` değerlendiren bir satır içi işlev `_mkgmtime64`, ve `time_t` eşdeğerdir `__time64_t`. Yorumlamaya derleyici zorlamak gerekiyorsa `time_t` eski 32 bit olarak `time_t`, tanımlayabileceğiniz `_USE_32BIT_TIME_T`. Uygulamanızı 18 Ocak 2038 sonra başarısız olabilir çünkü bu önerilmez (en fazla 32-bit aralığını `time_t`), ve 64 bit platformlarda hiç verilmez.  
  
 İle değiştirilmiş olarak yapısı geçirilen süre aşağıdaki gibi aynı şekilde değiştirilecek `_mktime` işlevleri: `tm_wday` ve `tm_yday` alanların değerlerine dayalı yeni değerlere ayarlanır `tm_mday` ve `tm_year`. Belirtirken bir `tm` yapısı zaman, Ayarla `tm_isdst` alanı:  
  
-   Standart Saati geçerli olduğunu belirtmek için bir sıfır (0).  
  
-   Yaz Saati geçerli olduğunu göstermek için 0'dan büyük bir değer.  
  
-   Bir değer sıfırdan C çalışma zamanı kitaplığı kodu sağlamak için standart saati gün ışığından yararlanma saati etkin olup işlem.  
  
 C çalışma zamanı kitaplığı TZ ortam değişkeninin doğru günışığından belirlemek için kullanır. TZ ayarlanmamışsa, işletim sistemi doğru bölgesel gün ışığından yararlanma saati davranışı elde etmek üzere sorgulanır. `tm_isdst` gerekli bir alandır. Ayarlı değil, kendi değeri tanımsız ise ve dönüş değerini `mktime` tahmin edilemez.  
  
 Aralığı `_mkgmtime32` işlevi, gece yarısıdır, 1 Ocak 1970'ten, 23:59:59 18 Ocak 2038, UTC UTC'ye. Aralığı `_mkgmtime64` gece, 1 Ocak 1970 UTC 23:59:59 arasında 31 Aralık 3000 UTC değil. Bir aralık dışı tarih -1 dönüş değeri sonuçlanır. Aralığı `_mkgmtime` bağlıdır `_USE_32BIT_TIME_T` tanımlanır. (Varsayılan) tanımlı değil ise, aralığı `_mkgmtime64`; Aksi halde, 32-bit aralığı için sınırlı bir aralığı `_mkgmtime32`.  
  
 Unutmayın `gmtime` ve `localtime` dönüştürme için tek bir statik olarak ayrılan arabellek kullanın. Bu arabelleğin sağlarsanız `mkgmtime`, önceki içeriği yok.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_mkgmtime.c  
#include <stdio.h>  
#include <time.h>  
  
int main()  
{  
    struct tm t1, t2;  
    time_t now, mytime, gmtime;  
    char buff[30];  
  
    time( & now );  
  
    _localtime64_s( &t1, &now );  
    _gmtime64_s( &t2, &now );  
  
    mytime = mktime(&t1);  
    gmtime = _mkgmtime(&t2);  
  
    printf("Seconds since midnight, January 1, 1970\n");  
    printf("My time: %I64d\nGM time (UTC): %I64d\n\n", mytime, gmtime);  
  
    /* Use asctime_s to display these times. */  
  
    _localtime64_s( &t1, &mytime );  
    asctime_s( buff, sizeof(buff), &t1 );  
    printf( "Local Time: %s\n", buff );  
  
    _gmtime64_s( &t2, &gmtime );  
    asctime_s( buff, sizeof(buff), &t2 );  
    printf( "Greenwich Mean Time: %s\n", buff );  
  
}  
```  
  
## <a name="sample-output"></a>Örnek Çıktı  
  
```  
Seconds since midnight, January 1, 1970  
My time: 1171588492  
GM time (UTC): 1171588492  
  
Local Time: Thu Feb 15 17:14:52 2007  
  
Greenwich Mean Time: Fri Feb 16 01:14:52 2007  
```  
  
 Aşağıdaki örnek, tamamlanmamış yapısı haftanın günü ve yılın günü hesaplanan değerlerle nasıl doldurulmuş gösterir.  
  
```  
// crt_mkgmtime2.c  
#include <stdio.h>  
#include <time.h>  
#include <memory.h>  
  
int main()  
{  
    struct tm t1, t2;  
    time_t gmtime;  
    char buff[30];  
  
    memset(&t1, 0, sizeof(struct tm));  
    memset(&t2, 0, sizeof(struct tm));  
  
    t1.tm_mon = 1;  
    t1.tm_isdst = 0;  
    t1.tm_year = 103;  
    t1.tm_mday = 12;  
  
    // The day of the week and year will be incorrect in the output here.  
    asctime_s( buff, sizeof(buff), &t1);  
    printf("Before calling _mkgmtime, t1 = %s t.tm_yday = %d\n",  
            buff, t1.tm_yday );  
  
    gmtime = _mkgmtime(&t1);  
  
    // The correct day of the week and year were determined.  
    asctime_s( buff, sizeof(buff), &t1);  
    printf("After calling _mkgmtime, t1 = %s t.tm_yday = %d\n",  
            buff, t1.tm_yday );  
  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003  
 t.tm_yday = 0  
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003  
 t.tm_yday = 42  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman Yönetimi](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)