---
title: localtime_s, _localtime32_s, _localtime64_s
ms.date: 4/2/2020
api_name:
- _localtime64_s
- _localtime32_s
- localtime_s
- _o__localtime32_s
- _o__localtime64_s
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _localtime32_s
- localtime32_s
- localtime_s
- localtime64_s
- _localtime64_s
helpviewer_keywords:
- _localtime64_s function
- localtime32_s function
- _localtime32_s function
- localtime64_s function
- time, converting values
- localtime_s function
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
ms.openlocfilehash: 3c5d194da85eb5d008dfc9cf19f222ebb575747d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342115"
---
# <a name="localtime_s-_localtime32_s-_localtime64_s"></a>localtime_s, _localtime32_s, _localtime64_s

**time_t** bir zaman değerini **tm** yapısına dönüştürür ve yerel saat dilimini düzeltir. Bunlar, CRT'deki Güvenlik Özellikleri'nde açıklandığı gibi güvenlik geliştirmeleriyle _localtime64 [yerel saat, _localtime32](localtime-localtime32-localtime64.md) [sürümleridir.](../../c-runtime-library/security-features-in-the-crt.md)

## <a name="syntax"></a>Sözdizimi

```C
errno_t localtime_s(
   struct tm* const tmDest,
   time_t const* const sourceTime
);
errno_t _localtime32_s(
   struct tm* tmDest,
   __time32_t const* sourceTime
);
errno_t _localtime64_s(
   struct tm* tmDest,
   __time64_t const* sourceTime
);
```

### <a name="parameters"></a>Parametreler

*tmDest*<br/>
Doldurulacak zaman yapısına işaretçi.

*kaynakZaman*<br/>
Depolanan zamana işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır. İade değeri, bir hata varsa bir hata kodudur. Hata kodları Errno.h'de tanımlanır. Bu hataların listesi için [bkz.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

### <a name="error-conditions"></a>Hata Koşulları

|*tmDest*|*kaynakZaman*|Döndürülen değer|*tmDest* değeri|Geçersiz parametre işleyicisi çağırır|
|-----------|------------|------------------|--------------------|---------------------------------------|
|**Null**|herhangi bir|**Eınval**|Değiştirilmedi|Evet|
|**NULL** değil (geçerli belleğe işaret)|**Null**|**Eınval**|-1 olarak ayarlanmış tüm alanlar|Evet|
|**NULL** değil (geçerli belleğe işaret)|0'dan az veya **_MAX__TIME64_T** büyük|**Eınval**|-1 olarak ayarlanmış tüm alanlar|Hayır|

İlk iki hata koşulu söz konusu olduğunda, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, bu işlevler EINVAL **için errno** ayarlayın ve **EINVAL** döndürün. **EINVAL**

## <a name="remarks"></a>Açıklamalar

**localtime_s** [işlevi, time_t](../../c-runtime-library/standard-types.md) değeri olarak depolanan bir zamanı dönüştürür ve sonucu [tm](../../c-runtime-library/standard-types.md)türünde bir yapıda depolar. **time_t** değeri *kaynağıTime,* gece yarısından (00:00:00), 1 Ocak 1970, UTC'den bu yana geçen saniyeleri temsil eder. Bu değer genellikle [zaman](time-time32-time64.md) fonksiyonu elde edilir.

**localtime_s,** kullanıcı küresel ortam değişkeni **TZ'yi**ilk ayarlarsa yerel saat dilimini düzeltir. **TZ** ayarlandığında, diğer üç ortam değişkeni **(_timezone,** **_daylight**ve **_tzname)** otomatik olarak ayarlanır. **TZ** değişkeni ayarlanmamışsa, **localtime_s** Denetim Masası'ndaki Tarih/Saat uygulamasında belirtilen saat dilimi bilgilerini kullanmaya çalışır. Bu bilgiler elde edilemiyorsa, Pasifik saat dilimini ifade eden PST8PDT varsayılan olarak kullanılır. Bu değişkenlerin açıklaması için [_tzset](tzset.md) bakın. **TZ,** ANSI standart **yerel saat**tanımının bir parçası değildir.

> [!NOTE]
> Hedef ortam, gün ışığından yararlanma saatinin geçerli olup olmadığını belirlemeye çalışmalıdır.

**__time64_t**yapısını kullanan **__time64_t** _localtime64_s tarihlerin 23:59:59, 18 Ocak 3001, eşgüdümlü evrensel saat (UTC) ile ifade edilmesine izin vererken, **_localtime32_s** tarihleri 23:59:59 18 Ocak 2038, UTC'ye kadar temsil eder.

**localtime_s** **_localtime64_s**için değerlendiren bir satır dışı fonksiyondur ve **time_t** **__time64_t**eşdeğerdir. Derleyiciyi **time_t** eski 32 bit **time_t**olarak yorumlamaya zorlamanız gerekiyorsa, **_USE_32BIT_TIME_T**tanımlayabilirsiniz. Bunu yapmak **localtime_s** **_localtime32_s**için değerlendirmeye neden olur. Başvurunuz 18 Ocak 2038'den sonra başarısız olabileceğinden ve 64 bit platformlarda izin verilmediği için bu önerilmez.

Yapı türü [tm](../../c-runtime-library/standard-types.md) alanları aşağıdaki değerleri depolar, her biri bir **int**.

|Alan|Açıklama|
|-|-|
|**tm_sec**|Saniye dakika sonra (0 - 59).|
|**tm_min**|Dakika sonra saat (0 - 59).|
|**tm_hour**|Gece yarısından (0 - 23) itibaren saatler.|
|**tm_mday**|Ayın günü (1 - 31).|
|**tm_mon**|Ay (0 - 11; Ocak = 0).|
|**tm_year**|Yıl (cari yıl eksi 1900).|
|**tm_wday**|Haftanın günü (0 - 6; Pazar = 0).|
|**tm_yday**|Yılın günü (0 - 365; 1 Ocak = 0).|
|**tm_isdst**|Gün ışığından yararlanma saati etkinse pozitif değer; Yaz saati uygulaması geçerli değilse 0; gün ışığından yararlanma saatinin durumu bilinmiyorsa negatif değer.|

**TZ** ortam değişkeni ayarlanırsa, C çalışma zamanı kitaplığı, gün ışığından yararlanma saati (DST) hesaplaması için ABD'ye uygun kuralları varsayar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgi|Gerekli C++ üstbilgi|
|-------------|---------------------|-|
|**localtime_s**, **_localtime32_s**, **_localtime64_s**|\<time.h>|\<ctime> \<veya time.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_localtime_s.c
// This program uses _time64 to get the current time
// and then uses _localtime64_s() to convert this time to a structure
// representing the local time. The program converts the result
// from a 24-hour clock to a 12-hour clock and determines the
// proper extension (AM or PM).

#include <stdio.h>
#include <string.h>
#include <time.h>

int main( void )
{
    struct tm newtime;
    char am_pm[] = "AM";
    __time64_t long_time;
    char timebuf[26];
    errno_t err;

    // Get time as 64-bit integer.
    _time64( &long_time );
    // Convert to local time.
    err = _localtime64_s( &newtime, &long_time );
    if (err)
    {
        printf("Invalid argument to _localtime64_s.");
        exit(1);
    }
    if( newtime.tm_hour > 12 )        // Set up extension.
        strcpy_s( am_pm, sizeof(am_pm), "PM" );
    if( newtime.tm_hour > 12 )        // Convert from 24-hour
        newtime.tm_hour -= 12;        // to 12-hour clock.
    if( newtime.tm_hour == 0 )        // Set hour to 12 if midnight.
        newtime.tm_hour = 12;

    // Convert to an ASCII representation.
    err = asctime_s(timebuf, 26, &newtime);
    if (err)
    {
        printf("Invalid argument to asctime_s.");
        exit(1);
    }
    printf( "%.19s %s\n", timebuf, am_pm );
}
```

```Output
Fri Apr 25 01:19:27 PM
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
