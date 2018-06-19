---
title: Zaman Yönetimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.memory
dev_langs:
- C++
helpviewer_keywords:
- dates, run-time library members
- time, time management
- date functions
- time functions
ms.assetid: 93599220-c011-45d5-978f-12182abfdd2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c33d22f30275c9d6581d6c1cd97de4ffe68bc08
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418347"
---
# <a name="time-management"></a>Zaman Yönetimi

Geçerli saati almak ve dönüştürme, ayarlamak ve gerektiği şekilde depolamak için bu işlevler kullanın. Geçerli sistem saati saattir.

 **_Ftime** ve **damgasını** yordamları kullanın **TZ** ortam değişkeni. Varsa **TZ** , çalışma zamanı kitaplığı çalışır işletim sistemi tarafından belirtilen saat dilimi bilgilerini kullanmak, ayarlı değil. Bu bilgiler kullanılamıyorsa, bu işlevler PST8PDT varsayılan değeri kullanın. Daha fazla bilgi için **TZ**, bkz: [_tzset](../c-runtime-library/reference/tzset.md); Ayrıca bkz. [_daylight, saat dilimi ve _tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

### <a name="time-routines"></a>Zamanı yordamları

|İşlev|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|--------------|---------|
|[asctime, _wasctime](../c-runtime-library/reference/asctime-wasctime.md), [asctime_s, _wasctime_s](../c-runtime-library/reference/asctime-s-wasctime-s.md)|Saat türünden dönüştürmek **yapısı tm** karakter dizesi. Bu işlevleri sürümlerini **_Yanları** soneki daha güvenlidir.|
|[clock](../c-runtime-library/reference/clock.md)|İşlem için geçen duvar saati süresi döndür.|
|[CTime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [_ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)|Saat türünden dönüştürmek **time_t**, **__time32_t** veya **__time64_t** karakter dizesi. Bu işlevleri sürümlerini **_Yanları** soneki daha güvenlidir.|
|[difftime, _difftime32, _difftime64](../c-runtime-library/reference/difftime-difftime32-difftime64.md)|İki kez arasındaki farkı işlem.|[System::DateTime:: çıkarma](https://msdn.microsoft.com/en-us/library/system.datetime.subtract.aspx)|
|[_ftime, _ftime32, _ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md),[_ftime_s, _ftime32_s, _ftime64_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)|Geçerli sistem saatinin türü değişkeninde depolar **yapısı _timeb** veya türü **yapısı __timeb64** bu işlevleri sürümlerini **_Yanları** soneki daha güvenli.|
|[_futime, _futime32, _futime64](../c-runtime-library/reference/futime-futime32-futime64.md)|Açık dosyada değiştirme saati ayarlayın|
|[gmtime, _gmtime32, _gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md), [gmtime_s, _gmtime32_s, _gmtime64_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)|Saat türünden dönüştürmek **time_t** için **yapısı tm** veya türünden **__time64_t** için **yapısı tm**. Bu işlevleri sürümlerini **_Yanları** soneki daha güvenlidir.|
|[damgasını, _localtime32, _localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md), [localtime_s, _localtime32_s, _localtime64_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)|Saat türünden dönüştürmek **time_t** için **yapısı tm** veya türünden **__time64_t** için **yapısı tm** yerel düzeltme. Bu işlevleri sürümlerini **_Yanları** soneki daha güvenlidir.|
|[_mkgmtime, _mkgmtime32, _mkgmtime64](../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)|Zamanı Greenwich saati Takvim değeri dönüştürülemiyor.|
|[mktime, _mktime32, _mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md)|Zaman Takvim değerine dönüştürür.|
|[_strdate, _wstrdate](../c-runtime-library/reference/strdate-wstrdate.md), [_strdate_s, _wstrdate_s](../c-runtime-library/reference/strdate-s-wstrdate-s.md)|Geçerli sistem tarihi dize olarak döndürür. Bu işlevleri sürümlerini **_Yanları** soneki daha güvenlidir.|
|[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|Tarih ve saat dizesi uluslararası kullanmak için biçimlendirin.|
|[_strtime, _wstrtime](../c-runtime-library/reference/strtime-wstrtime.md), [_strtime_s, _wstrtime_s](../c-runtime-library/reference/strtime-s-wstrtime-s.md)|Geçerli sistem saatinin dize olarak döndürür. Bu işlevleri sürümlerini **_Yanları** soneki daha güvenlidir.|
|[time, _time32, _time64](../c-runtime-library/reference/time-time32-time64.md)|Geçerli sistem saatinin türü olarak alma **time_t**, **__time32_t** türü olarak veya **__time64_t**.|
|[_tzset](../c-runtime-library/reference/tzset.md)|Ortam zaman değişkeninden dış zamanı değişkenlerini ayarlamak **TZ**.|
|[_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)|Geçerli saat veya saat değeri yapısında depolanmış kullanarak belirtilen dosya için değiştirme saati ayarlayın.|

> [!NOTE]
> 1 Ocak 1970'ten gece yarısından beri geçen saniye sayısı gibi Microsoft C/C++ Microsoft C/C++ version 7.0 dışında tüm sürümlerinde ve tüm sürümlerinde Visual C++, zaman işlevi geçerli saati döndürür. Microsoft C/C++ version 7.0 **zaman** 31 Aralık 1899 gece yarısından beri geçen saniye sayısı olarak geçerli saati döndürdü.

> [!NOTE]
> Visual C++ ve Microsoft C/C++ Visual C++ 2005 önce sürümlerinde **time_t** olan bir **uzun** **int** (32 bit) ve bu nedenle tarihlerini kullanılamadı 3:14:07 19 Ocak 2038 geçmiş , UTC. **time_t** şimdi eşdeğer olan **__time64_t** varsayılan, ancak tanımlama **_USE_32BIT_TIME_T** değişiklikleri **time_t** için **__time32_t** ve 32-bit ele sürümleri çağırmak için çok zaman işlevleri zorlar **time_t**. Daha fazla bilgi için bkz: [standart türler](../c-runtime-library/standard-types.md) ve tek tek zaman işlevleri için belgeleri açıklamaları.

## <a name="see-also"></a>Ayrıca Bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
