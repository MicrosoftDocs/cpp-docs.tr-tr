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
ms.openlocfilehash: 9d5983795dbb5711452db2f59b07cb6aa8b22a8c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200211"
---
# <a name="time-management"></a>Zaman Yönetimi

Geçerli saati Al ve Dönüştür, ayarlamak ve gerektiği şekilde depolamak için bu işlevleri kullanın. Geçerli sistem saatini zamandır.

 **_Ftime** ve **localtime** kullanmalarını **TZ** ortam değişkeni. Varsa **TZ** ayarlanmazsa işletim sistemi tarafından belirtilen saat dilimi bilgilerini kullanmak çalışma zamanı kitaplığı çalışır. Bu bilgiler kullanılamıyorsa, bu işlevler PST8PDT varsayılan değeri kullanın. Daha fazla bilgi için **TZ**, bakın [_tzset](../c-runtime-library/reference/tzset.md); Ayrıca bkz: [_daylight, saat diliminizi ve _tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

### <a name="time-routines"></a>Zamanı yordamları

|İşlev|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|--------------|---------|
|[asctime, _wasctime](../c-runtime-library/reference/asctime-wasctime.md), [asctime_s, _wasctime_s](../c-runtime-library/reference/asctime-s-wasctime-s.md)|Saat türünden dönüştürme **yapı tm** karakter dizesi. Sahip bu işlevlerin sürümleri **_Yanları** sonekine daha güvenli.|
|[clock](../c-runtime-library/reference/clock.md)|İşlem için geçen duvar saati döndürür.|
|[CTime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [_ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)|Saat türünden dönüştürme **time_t**, **__time32_t** veya **__time64_t** karakter dizesi. Sahip bu işlevlerin sürümleri **_Yanları** sonekine daha güvenli.|
|[difftime, _difftime32, _difftime64](../c-runtime-library/reference/difftime-difftime32-difftime64.md)|İki zaman arasındaki farkı hesaplayın.|[System::DateTime:: çıkarma](https://msdn.microsoft.com/library/system.datetime.subtract.aspx)|
|[_ftime, _ftime32, _ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md),[_ftime_s, _ftime32_s, _ftime64_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)|Türünde bir değişken geçerli sistem saatinin Store **yapı _timeb** veya türü **yapı __timeb64** sahip bu işlevlerin sürümleri **_Yanları** sonekine daha güvenli.|
|[_futime, _futime32, _futime64](../c-runtime-library/reference/futime-futime32-futime64.md)|Açık dosya değiştirme saati ayarla|
|[gmtime, _gmtime32, _gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md), [gmtime_s, _gmtime32_s, _gmtime64_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)|Saat türünden dönüştürme **time_t** için **yapı tm** veya türünden **__time64_t** için **yapı tm**. Sahip bu işlevlerin sürümleri **_Yanları** sonekine daha güvenli.|
|[localtime, _localtime32, _localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md), [localtime_s, _localtime32_s, _localtime64_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)|Saat türünden dönüştürme **time_t** için **yapı tm** veya türünden **__time64_t** için **yapı tm** yerel düzeltme. Sahip bu işlevlerin sürümleri **_Yanları** sonekine daha güvenli.|
|[_mkgmtime, _mkgmtime32, _mkgmtime64](../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)|Greenwich saati Takvim değerine dönüştürün.|
|[mktime, _mktime32, _mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md)|Takvim değerine dönüştürün.|
|[_strdate, _wstrdate](../c-runtime-library/reference/strdate-wstrdate.md), [_strdate_s, _wstrdate_s](../c-runtime-library/reference/strdate-s-wstrdate-s.md)|Geçerli sistem tarihi dize olarak döndürür. Sahip bu işlevlerin sürümleri **_Yanları** sonekine daha güvenli.|
|[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|Uluslararası kullanılmak tarih ve saat dizesi biçimi.|
|[_strtime, _wstrtime](../c-runtime-library/reference/strtime-wstrtime.md), [_strtime_s, _wstrtime_s](../c-runtime-library/reference/strtime-s-wstrtime-s.md)|Geçerli sistem saatinin dize olarak döndürür. Sahip bu işlevlerin sürümleri **_Yanları** sonekine daha güvenli.|
|[time, _time32, _time64](../c-runtime-library/reference/time-time32-time64.md)|Geçerli sistem saatinin türü olarak alma **time_t**, **__time32_t** türü olarak veya **__time64_t**.|
|[_tzset](../c-runtime-library/reference/tzset.md)|Dış saat değişkenlerini zaman iliştirdiğinizde ayarlama **TZ**.|
|[_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)|Değiştirme saati için belirtilen dosya geçerli saat veya saat değeri yapısında depolanmış kullanarak ayarlayın.|

> [!NOTE]
> 1 Ocak 1970 gece yarısından beri geçen saniye sayısı saat olarak, Microsoft C/C++ Microsoft C/C++ version 7.0 dışında tüm sürümlerinde ve tüm sürümlerinde Visual C++ zaman işlev geçerli saati döndürür. Microsoft C/C++ version 7.0, **zaman** 31 Aralık 1899 gece yarısından beri geçen saniye sayısı saat olarak geçerli saati döndürdü.

> [!NOTE]
> Visual C++ ve Visual C++ 2005 önce Microsoft C/C++ sürümlerinde **time_t** olduğu bir **uzun** **int** (32 bit) ve bu nedenle tarihlerini kullanılamadı 3:14:07 19 Ocak 2038 geçmiş , UTC. **time_t** artık değerine eşdeğer olan **__time64_t** varsayılan, ancak tanımlama **_use_32bıt_tıme_t** değişiklikleri **time_t** için **__time32_t** alan 32-bit sürümleri çağırmak için birçok saat işlevleri zorlar **time_t**. Daha fazla bilgi için [standart türler](../c-runtime-library/standard-types.md) ve bireysel saat işlevleri belgelerindeki açıklamalar.

## <a name="see-also"></a>Ayrıca Bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
