---
description: 'Daha fazla bilgi edinin: süre yönetimi'
title: Zaman Yönetimi
ms.date: 11/04/2016
helpviewer_keywords:
- dates, run-time library members
- time, time management
- date functions
- time functions
ms.assetid: 93599220-c011-45d5-978f-12182abfdd2f
ms.openlocfilehash: c8a5b65c66ab89506149c92bd32999be3503c700
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326914"
---
# <a name="time-management"></a>Zaman Yönetimi

Bu işlevleri, geçerli saati almak ve dönüştürmek, ayarlamak ve gerektiği şekilde depolamak için kullanın. Geçerli saat sistem saati.

**_Ftime** ve **localtime** yordamları **TZ** ortam değişkenini kullanır. **TZ** ayarlanmamışsa, çalışma zamanı kitaplığı işletim sistemi tarafından belirtilen saat dilimi bilgilerini kullanmaya çalışır. Bu bilgiler kullanılamıyorsa, bu işlevler varsayılan değer olan PST8PDT kullanır. **TZ** hakkında daha fazla bilgi için bkz. [_tzset](../c-runtime-library/reference/tzset.md); Ayrıca bkz. [_daylight, saat dilimi ve _tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

### <a name="time-routines"></a>Zaman yordamları

|İşlev|Kullanın|
|--------------|---------|
|[yoksaat, _wasctime](../c-runtime-library/reference/asctime-wasctime.md), [asctime_s _wasctime_s](../c-runtime-library/reference/asctime-s-wasctime-s.md)|**Struct** from türünden karakter dizesine saati dönüştürür. **_S** sonekine sahip bu işlevlerin sürümleri daha güvenlidir.|
|[saat](../c-runtime-library/reference/clock.md)|İşlem için geçen duvar saati saati döndürür.|
|[CTime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [_ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)|**Time_t**, **__time32_t** veya **__time64_t** türünden karakter dizesine kadar olan süreyi dönüştürür. **_S** sonekine sahip bu işlevlerin sürümleri daha güvenlidir.|
|[difftime, _difftime32, _difftime64](../c-runtime-library/reference/difftime-difftime32-difftime64.md)|İki kez işlem farkı.|
|[_ftime, _ftime32, _ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md),[_ftime_s, _ftime32_s, _ftime64_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)|Geçerli sistem saatini **struct _timeb** veya Type struct türünde bir değişkende depolayın **__timeb64** bu işlevlerin sürümleri **_s** sonekiyle daha güvenlidir.|
|[_futime, _futime32, _futime64](../c-runtime-library/reference/futime-futime32-futime64.md)|Açık dosyada değişiklik saatini ayarla|
|[gmsaati, _gmtime32, _gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md), [gmtime_s, _gmtime32_s, _gmtime64_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)|**Time_t** türünden **Yapı tm** 'ye veya **__time64_t** türünden **struct tm**'e dönüştürün. **_S** sonekine sahip bu işlevlerin sürümleri daha güvenlidir.|
|[localtime, _localtime32, _localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md), [localtime_s, _localtime32_s, _localtime64_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)|**Time_t** türünden **Yapı tm** 'ye veya **__time64_t** türünden **struct tm 'e, yerel** düzeltme içeren bir süre dönüştürme. **_S** sonekine sahip bu işlevlerin sürümleri daha güvenlidir.|
|[_mkgmtime, _mkgmtime32, _mkgmtime64](../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)|Greenwich saati cinsinden saati takvim değerine dönüştürür.|
|[mktime, _mktime32, _mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md)|Saati takvim değerine dönüştürür.|
|[_strdate, _wstrdate](../c-runtime-library/reference/strdate-wstrdate.md), [_strdate_s, _wstrdate_s](../c-runtime-library/reference/strdate-s-wstrdate-s.md)|Geçerli sistem tarihini dize olarak döndürür. **_S** sonekine sahip bu işlevlerin sürümleri daha güvenlidir.|
|[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|Uluslararası kullanım için tarih ve saat dizesini biçimlendirin.|
|[_strtime, _wstrtime](../c-runtime-library/reference/strtime-wstrtime.md), [_strtime_s, _wstrtime_s](../c-runtime-library/reference/strtime-s-wstrtime-s.md)|Geçerli sistem saatini dize olarak döndürür. **_S** sonekine sahip bu işlevlerin sürümleri daha güvenlidir.|
|[time, _time32, _time64](../c-runtime-library/reference/time-time32-time64.md)|**Time_t**, **__time32_t** veya türü **__time64_t** olarak geçerli sistem saatini alın.|
|[_tzset](../c-runtime-library/reference/tzset.md)|Dış zaman değişkenlerini, ortam zaman değişkeni **TZ** değerinden ayarlayın.|
|[_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)|Belirtilen dosya için, yapıda depolanan geçerli saat veya saat değerini kullanarak değiştirme süresini ayarlayın.|

> [!NOTE]
> Microsoft c/C++ sürüm 7,0 hariç tüm Microsoft C/C++ sürümlerinde ve tüm Visual C++ sürümlerinde, Time işlevi, 1 Ocak 1970 ' de gece yarısından beri geçen saniye sayısı olarak geçerli saati döndürür. Microsoft C/C++ sürüm 7,0 ' de, **süresi** 31 Aralık 1899 ' de gece yarısından beri geçen saniye sayısı olarak geçerli saati geri döndürdü.

> [!NOTE]
> Visual Studio 2005 ' den önceki Visual C++ ve Microsoft C/C++ sürümlerinde, **time_t** bir **`long int`** (32 bit) ve bu nedenle 19 Ocak 2038, UTC 'den 3:14:07 önceki tarihler için kullanılamadı. **time_t** artık varsayılan olarak **__time64_t** eşdeğerdir, ancak **_USE_32BIT_TIME_T** değişiklik **time_t** ve 32-bit **__time32_t** alan sürümleri **çağırmak için birçok** zaman işlevi zorlayarak. Daha fazla bilgi için, bireysel zaman işlevleri için belgelerde [standart türler](../c-runtime-library/standard-types.md) ve açıklamalar bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
