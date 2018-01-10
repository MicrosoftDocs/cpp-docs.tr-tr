---
title: "damgasını, _localtime32, _localtime64 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _localtime64
- _localtime32
- localtime
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
- localtime64
- _localtime64
- localtime32
- localtime
- _localtime32
dev_langs: C++
helpviewer_keywords:
- localtime32 function
- _localtime32 function
- _localtime64 function
- localtime64 function
- localtime function
- time, converting values
ms.assetid: 4260ec3d-43ee-4538-b998-402a282bb9b8
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 77a0a297413c053dee3e165ece07034487535b06
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="localtime-localtime32-localtime64"></a>localtime, _localtime32, _localtime64
Bir saat değeri dönüştürmek ve yerel saat dilimini düzeltin. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct tm *localtime(  
   const time_t *timer   
);  
struct tm *_localtime32(  
   const __time32_t *timer  
);  
struct tm *_localtime64(  
   const __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `timer`  
 Saklı zaman işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi yapısı için sonuç veya `NULL` tarihi işleve ise:  
  
-   Gece yarısından önce 1 Ocak 1970'ten.  
  
-   Sonra 03:14:07, 19 Ocak 2038, UTC (kullanarak `_time32` ve `time32_t`).  
  
-   23:59:59 31 Aralık 3000 UTC sonra (kullanarak `_time64` ve `__time64_t`).  
  
 `_localtime64`, kullanan `__time64_t` yapısı, 23:59:59, 31 Aralık 3000 Eşgüdümlü Evrensel Saat (UTC) ayarlama ifade tarihleri sağlarken `_localtime32` ile 23:59:59 18 Ocak 2038, UTC tarihleri temsil eder.  
  
 `localtime`için değerlendiren bir satır içi işlev `_localtime64`, ve `time_t` eşdeğerdir `__time64_t`. Yorumlamaya derleyici zorlamak gerekiyorsa `time_t` eski 32 bit olarak `time_t`, tanımlayabileceğiniz `_USE_32BIT_TIME_T`. Bunun neden olacak `localtime` için değerlendirilecek `_localtime32`. Bu, uygulamanızın 18 Ocak 2038 sonra başarısız olabilir ve 64 bit platformlarda izin verilmiyor çünkü önerilmez.  
  
 Yapı türünde alanlar [tm](../../c-runtime-library/standard-types.md) , her biri aşağıdaki değerlerini depolayan bir `int`:  
  
 `tm_sec`  
 Saniye dakika sonra (0 - 59).  
  
 `tm_min`  
 Dakika sonra saat (0 - 59).  
  
 `tm_hour`  
 Gece yarısından sonra saat (0 - 23).  
  
 `tm_mday`  
 Ayın günü (1-31).  
  
 `tm_mon`  
 Ay (0 - 11; Ocak = 0).  
  
 `tm_year`  
 Yıl (1900 eksi geçerli yıl).  
  
 `tm_wday`  
 Haftanın günü (0 - 6; Pazar = 0).  
  
 `tm_yday`  
 Yılın günü (0 - 365; 1 Ocak = 0).  
  
 `tm_isdst`  
 Yaz Saati etkinse, pozitif bir değer; Yaz Saati etkin değilse, 0; Yaz Saati durumunu bilinmiyorsa negatif değer. Varsa `TZ` ortam değişkeni ayarlanmışsa, C çalışma zamanı kitaplığı kuralları Amerika Birleşik Devletleri uygun hesaplama – Yaz Saati (DST) uygulamak için varsayar.  
  
## <a name="remarks"></a>Açıklamalar  
 `localtime` İşlevi dönüştürür olarak saklanan bir süre bir [time_t](../../c-runtime-library/standard-types.md) değer ve sonuç türü yapısında depolar `tm`. `long` Değeri `timer` gece yarısından beri geçen saniye temsil eder (00: 00:00), 1 Ocak 1970'den itibaren UTC. Bu değer genellikle alanından elde `time` işlevi.  
  
 Hem 32 bit ve 64 bit sürümlerini `gmtime`, `mktime`, `mkgmtime`, ve `localtime` tüm tek kullanımlık `tm` dönüştürme için iş parçacığı başına yapısı. Bu yordamlar her çağrısına önceki çağrının sonucu bozar.  
  
 `localtime`Kullanıcı ilk genel ortam değişkeni ayarlarsa için yerel saat dilimi düzeltir `TZ`. Zaman `TZ` ayarlandığında, diğer üç ortam değişkenlerini (`_timezone`, `_daylight`, ve `_tzname`) otomatik olarak da ayarlanır. Varsa `TZ` değişken ayarlanmazsa `localtime` tarih uygulama Denetim Masası'nda belirtilen saat dilimi bilgilerini kullanmaya çalışır. Bu bilgiler alınamıyor, Pasifik saat diliminde güveninin, PST8PDT varsayılan olarak kullanılır. Bkz: [_tzset](../../c-runtime-library/reference/tzset.md) bu değişkenleri açıklaması. `TZ`bir Microsoft uzantısı ve ANSI standart tanımının parçası olmayan `localtime`.  
  
> [!NOTE]
>  Hedef ortam gün ışığından yararlanma saati etkin olup olmadığını belirlemek denemelisiniz.  
  
 Bu işlevler kendi parametreleri doğrulayın. Varsa `timer` null işaretçi ya da devre dışı zamanlayıcı değeri negatifse, bu işlevlerin bir geçersiz parametre işleyicisi açıklandığı gibi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, işlevlerin dönüş `NULL` ve `errno` için `EINVAL`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`localtime`|\<time.h >|  
|`_localtime32`|\<time.h >|  
|`_localtime64`|\<time.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_localtime.cpp  
// compile with: /W3  
/* This program uses _time64 to get the current time   
 * and then uses localtime64() to convert this time to a structure   
 * representing the local time. The program converts the result   
 * from a 24-hour clock to a 12-hour clock and determines the   
 * proper extension (AM or PM).  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <time.h>  
  
int main( void )  
{  
        struct tm *newtime;  
        char am_pm[] = "AM";  
        __time64_t long_time;  
  
        _time64( &long_time );           // Get time as 64-bit integer.  
                                         // Convert to local time.  
        newtime = _localtime64( &long_time ); // C4996  
        // Note: _localtime64 deprecated; consider _localetime64_s  
  
        if( newtime->tm_hour > 12 )        // Set up extension.  
                strcpy_s( am_pm, sizeof(am_pm), "PM" );  
        if( newtime->tm_hour > 12 )        // Convert from 24-hour  
                newtime->tm_hour -= 12;    //   to 12-hour clock.  
        if( newtime->tm_hour == 0 )        // Set hour to 12 if midnight.  
                newtime->tm_hour = 12;  
  
        char buff[30];  
        asctime_s( buff, sizeof(buff), newtime );  
        printf( "%.19s %s\n", buff, am_pm );  
}  
```  
  
```Output  
Tue Feb 12 10:05:58 AM  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman Yönetimi](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [CTime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [_time64 _time32, saat](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)