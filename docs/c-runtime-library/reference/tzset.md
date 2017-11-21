---
title: _tzset | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _tzset
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
f1_keywords: _tzset
dev_langs: C++
helpviewer_keywords:
- _tzset function
- time environment variables
- environment variables, setting time
ms.assetid: 3f6ed537-b414-444d-b272-5dd377481930
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 494d8908660913396fb86f4cbbcfcc577a3f3166
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="tzset"></a>_tzset
Ayarlar, ortam değişkenleri zaman.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _tzset( void );  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `_tzset` İşlevini kullanır ve ortam değişkeninin geçerli ayar `TZ` üç genel değişkenleri için değerleri atamak için: `_daylight`, `_timezone`, ve `_tzname`. Bu değişkenler tarafından kullanılan [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) ve [damgasını](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) yerel saate ve tarafından Eşgüdümlü Evrensel Saat (UTC) düzeltmeler yapmak için işlevleri `time` UTC sistemden hesaplamak için işlevi süre. Ayarlamak için aşağıdaki sözdizimini kullanın `TZ` ortam değişkeni:  
  
 `set` `TZ`=`tzn`[+ &#124; -]`hh`[`:mm`[`:ss`] ][`dzn`]  
  
 `tzn`  
 PST gibi üç harfli saat dilimi adı. Yerel saat UTC doğru uzaklık belirtmeniz gerekir.  
  
 `hh`  
 UTC ve yerel saat arasındaki farkı saat. İşareti (+) pozitif değer isteğe bağlıdır.  
  
 `mm`  
 Dakika. Gelen ayrılmış `hh` bir virgülle (`:`).  
  
 `ss`  
 Saniye sayısı. Gelen ayrılmış `mm` bir virgülle (`:`).  
  
 `dzn`  
 Üç harfli gün ışığından yararlanma saati dilimi saati gibi. Yaz Saati hiçbir zaman yürürlükte yerleşim ise, `TZ` için bir değer olmadan `dzn`. C çalışma zamanı kitaplığı gün ışığından yararlanma saati (DST) hesaplama uygulamak için Amerika Birleşik Devletleri kuralları varsayar.  
  
> [!NOTE]
>  Bilgisayar zaman farkı oturum dikkatli olun. UTC (geriye doğru yerine) için yerel saat uzaklığı zaman farkı olduğu için onun oturum sezgisel beklediğiniz tersi olabilir. Öncesinde UTC saat dilimleri için saat farkı negatifse; Bu UTC arkasında pozitif farktır.  
  
 Örneğin, ayarlamak için `TZ` Almanya, geçerli saat diliminizde karşılık gelecek şekilde ortam değişkeni komut satırında aşağıdakileri girin:  
  
```  
set TZ=GST-1GDT  
```  
  
 Bu kullanımları GST Almanca Standart Saati, belirtmek için komut UTC Almanya arkasında (veya Almanya UTC öncesinde bir saattir diğer sözcükler,), bir saat olduğunu varsayar ve Almanya – ışığından gözlemleyen varsayar.  
  
 Varsa `TZ` değeri ayarlanmazsa, `_tzset` işletim sistemi tarafından belirtilen saat dilimi bilgilerini kullanmaya çalışır. Windows işletim sisteminde, Denetim Masası'ndaki Tarih uygulama bu bilgileri belirtildi. Varsa `_tzset` bu bilgileri elde edemiyor Pasifik saat diliminde güveninin varsayılan PST8PDT kullanır.  
  
 Temel `TZ` ortam değişkeni değeri, aşağıdaki değerleri genel değişkenler atanır `_daylight`, `_timezone`, ve `_tzname` zaman `_tzset` adı verilir:  
  
|Genel değişkeni|Açıklama|Varsayılan değer|  
|---------------------|-----------------|-------------------|  
|`_daylight`|Bir gün ışığından yararlanma saati bölge belirtilmişse sıfır olmayan bir değer `TZ` ayarlama; Aksi takdirde, 0.|1.|  
|`_timezone`|Yerel saat ile UTC arasındaki farkı saniye cinsinden.|28800 (28800 saniye eşittir 8 saat)|  
|`_tzname`[0]|Saat dilimi adı değeri dize `TZ` ortam değişkeni; boş ise `TZ` ayarlanmadı.|PST|  
|`_tzname`[1]|Dize değeri gün ışığından yararlanma saati bölgenin; gelen gün ışığından yararlanma saati dilimi atlanırsa boş `TZ` ortam değişkeni.|SAATİ|  
  
 Önceki tabloda gösterilen varsayılan değerler `_daylight` ve `_tzname` dizi karşılık gelen "PST8PDT." Gelen DST bölge atlanırsa `TZ` ortam değişkeni, değeri `_daylight` 0'dır ve `_ftime`, `gmtime`, ve `localtime` işlevleri için kendi DST bayraklar 0 döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_tzset`|\<time.h >|  
  
 Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_tzset.cpp  
// This program uses _tzset to set the global variables  
// named _daylight, _timezone, and _tzname. Since TZ is  
// not being explicitly set, it uses the system time.  
  
#include <time.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    _tzset();  
    int daylight;  
    _get_daylight( &daylight );  
    printf( "_daylight = %d\n", daylight );  
    long timezone;  
    _get_timezone( &timezone );  
    printf( "_timezone = %ld\n", timezone );  
    size_t s;  
    char tzname[100];  
    _get_tzname( &s, tzname, sizeof(tzname), 0 );  
    printf( "_tzname[0] = %s\n", tzname );  
    exit( 0 );  
}  
```  
  
```Output  
_daylight = 1  
_timezone = 28800  
_tzname[0] = Pacific Standard Time  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman Yönetimi](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [damgasını, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [_time64 _time32, saat](../../c-runtime-library/reference/time-time32-time64.md)   
 [_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)