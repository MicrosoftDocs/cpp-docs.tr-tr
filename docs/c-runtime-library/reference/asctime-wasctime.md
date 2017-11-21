---
title: asctime, _wasctime | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wasctime
- asctime
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
- _tasctime
- asctime
- _wasctime
dev_langs: C++
helpviewer_keywords:
- asctime function
- tasctime function
- wasctime function
- _tasctime function
- _wasctime function
- time structure conversion
- time, converting
ms.assetid: 974f1727-10ff-4ed4-8cac-2eb2d681f576
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e356e6bef6c46bfede3f8337969fd1385cebd66
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="asctime-wasctime"></a>asctime, _wasctime
Dönüştürme bir `tm` zaman bir karakter dizesine yapısı. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *asctime(   
   const struct tm *timeptr   
);  
wchar_t *_wasctime(   
   const struct tm *timeptr   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `timeptr`  
 Saat/tarih yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `asctime`bir işaretçi karakter dizesi sonucu döndürür; `_wasctime` bir işaretçi için joker karakter dizesi sonucunu döndürür. Hata dönüş değeri yoktur.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md).  
  
 `asctime` İşlevi bir karakter dizesine yapısı olarak depolanan bir saat dönüştürür. `timeptr` Değeri çağrısından alınan genellikle `gmtime` veya `localtime`, hangi hem bir işaretçi döndürmek bir `tm` zamanında tanımlanan yapısı. H.  
  
|timeptr üyesi|Değer|  
|--------------------|-----------|  
|`tm_hour`|Saat (0-23) gece yarısından|  
|`tm_isdst`|Yaz Saati etkinse pozitif; Yaz Saati etkin değilse, 0; Yaz Saati durumunu bilinmiyorsa negatif. C çalışma zamanı kitaplığı, gün ışığından yararlanma saati (DST) hesaplama uygulamak için Amerika Birleşik Devletleri kuralları varsayar.|  
|`tm_mday`|(1-31) ayın günü|  
|`tm_min`|Dakika sonra saat (0-59)|  
|`tm_mon`|Ay (0-11; Ocak = 0)|  
|`tm_sec`|Dakika (0-59) saniye|  
|`tm_wday`|Haftanın günü (0-6; Pazar = 0)|  
|`tm_yday`|(0-365; yılın günü 1 Ocak = 0)|  
|`tm_year`|Yıl (1900 eksi geçerli yıl)|  
  
 Dönüştürülen karakter dizesini de yerel saat dilimi ayarlarını göre ayarlanır. Yerel saat yapılandırma hakkında daha fazla bilgi için bkz: [zaman](../../c-runtime-library/reference/time-time32-time64.md), [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md), ve [damgasını](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) işlevleri ve [_tzset](../../c-runtime-library/reference/tzset.md) işlevi saat dilimi ortamı ve genel değişkenler tanımlama hakkında daha fazla bilgi için.  
  
 Tarafından üretilen dize sonuç `asctime` tam olarak 26 karakter içerir ve form `Wed Jan 02 02:03:55 1980\n\0`. 24 saatlik kullanılır. Tüm alanları sabit genişlik sahiptir. Yeni satır karakteri ve null karakteri dize son iki konumlarını kaplar. `asctime`Dönüş dizesi tutmak için bir tek, statik olarak ayrılan arabellek kullanır. Bu işlev için her çağrı önceki çağrının sonucu bozar.  
  
 `_wasctime`bir joker karakter sürümü `asctime`. `_wasctime`ve `asctime` Aksi takdirde aynı şekilde davranır.  
  
 Bu işlevler kendi parametreleri doğrulayın. Varsa `timeptr` null işaretçi veya aralık dışı değerler içeriyorsa, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, işlevi döndürür `NULL` ve ayarlar `errno` için `EINVAL`.  
  
### <a name="generic-text-routine-mapping"></a>Genel metin rutin eşleme  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tasctime`|`asctime`|`asctime`|`_wasctime`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`asctime`|\<time.h >|  
|`_wasctime`|\<time.h > veya \<wchar.h >|  
  
## <a name="example"></a>Örnek  
 Bu program sistem saatini uzun tamsayı olarak yerleştirir `aclock`, yapısına çevirir `newtime` ve ardından dize form için çıktı, kullanarak `asctime` işlevi.  
  
```  
// crt_asctime.c  
// compile with: /W3  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
    struct tm   *newTime;  
    time_t      szClock;  
  
    // Get time in seconds  
    time( &szClock );  
  
    // Convert time to struct tm form   
    newTime = localtime( &szClock );  
  
    // Print local time as a string.  
    printf_s( "Current date and time: %s", asctime( newTime ) ); // C4996  
    // Note: asctime is deprecated; consider using asctime_s instead  
}  
```  
  
```Output  
Current date and time: Sun Feb 03 11:38:58 2002  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman Yönetimi](../../c-runtime-library/time-management.md)   
 [CTime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [damgasını, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [_time64 _time32, saat](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)