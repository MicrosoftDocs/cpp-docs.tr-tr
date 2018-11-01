---
title: localtime_s, _localtime32_s, _localtime64_s
ms.date: 11/04/2016
apiname:
- _localtime64_s
- _localtime32_s
- localtime_s
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
ms.openlocfilehash: 44b2eb2515035d56143a2aab251437a92515e652
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492787"
---
# <a name="localtimes-localtime32s-localtime64s"></a>localtime_s, _localtime32_s, _localtime64_s

Dönüştürür bir **time_t** saat değeri için bir **tm** yapısı ve yerel saat dilimini düzeltir. Bunlar sürümleridir [localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Doldurulması için süresi yapısına yönelik işaretçi.

*sourceTime*<br/>
Depolanan zamana yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Bir hata varsa dönüş değeri bir hata kodudur. Hata kodları Errno.h içinde tanımlanır. Bu hataların bir listesi için bkz: [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Hata koşulları

|*tmDest*|*sourceTime*|Dönüş değeri|Değerini *tmDest*|Geçersiz parametre işleyicisini çağırır|
|-----------|------------|------------------|--------------------|---------------------------------------|
|**NULL**|Tüm|**EINVAL**|değiştirilmedi|Evet|
|Değil **NULL** (geçerli bellek noktaları)|**NULL**|**EINVAL**|Tüm alanları -1 olarak ayarlayın.|Evet|
|Değil **NULL** (geçerli bellek noktaları)|0'den küçük veya büyük **_MAX__TIME64_T**|**EINVAL**|Tüm alanları -1 olarak ayarlayın.|Hayır|

İlk iki hata koşulları söz konusu olduğunda, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve dönüş **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Localtime32_s** işlevi dönüştürür bir saat olarak depolanan bir [time_t](../../c-runtime-library/standard-types.md) değeri ve sonucu türündeki yapıda depolar [tm](../../c-runtime-library/standard-types.md). **Uzun** değer *sourceTime* saniye gece yarısından beri geçen temsil eder (00: 00:00), 1 Ocak 1970, UTC. Bu değer genellikle öğesinden alınan [zaman](time-time32-time64.md) işlevi.

**_localtime32_s** kullanıcı önce genel ortam değişkenini ayarlar, yerel saat dilimini düzeltir **TZ**. Zaman **TZ** ayarlandığında, üç ortam değişkenlerini (**_timezone**, **_daylight**, ve **_tzname**) de otomatik olarak ayarlanır. Varsa **TZ** değişkeni ayarlanmamış, **localtime32_s** Denetim Masası'ndaki Tarih/saat uygulamasında belirtilen saat dilimi bilgilerini kullanmaya çalışır. Bu bilgileri alınamıyor, Pasifik Saat dilimini belirtir, PST8PDT, varsayılan olarak kullanılır. Bkz: [_tzset](tzset.md) bu değişkenleri açıklaması. **TZ** standart ANSI tanımının parçası değildir ve Microsoft uzantısı olduğundan **localtime**.

> [!NOTE]
> Gün ışığından yararlanma etkin olup olmadığını belirlemek hedef ortamı denemelisiniz.

**_localtime64_s**, kullanan **__time64_t** yapısı, 23:59:59 18 Ocak 3001, Eşgüdümlü Evrensel Saat (UTC), yedekleme ifade edilecek tarihleri sağlarken **_localtime32_s** 23:59:59 18 Ocak 2038, UTC tarihleri temsil eder.

**localtime_s** olarak değerlendirilen bir satır içi işlev **_localtime64_s**, ve **time_t** eşdeğerdir **__time64_t**. Yorumlamak üzere zorlamanız gerekirse **time_t** eski 32-bit olarak **time_t**, tanımlayabileceğiniz **_use_32bıt_tıme_t**. Bunun yapılması neden olacak **localtime_s** için değerlendirilecek **_localtime32_s**. Bu, 18 Ocak 2038 sonrasında uygulamanız çalışmayabilir ve 64-bit platformlarda izin verilmiyor çünkü önerilmez.

Yapı türü alanlarını [tm](../../c-runtime-library/standard-types.md) her biri aşağıdaki değerlerini depolayan bir **int**.

|Alan|Açıklama|
|-|-|
|**tm_sec**|Dakikadan sonra saniye (0 - 59).|
|**tm_min**|Saatten sonraki dakika sayısı (0 - 59).|
|**tm_hour**|Gece yarısından itibaren saat (0 - 23).|
|**tm_mday**|(1-31) ayın günü.|
|**tm_mon**|Ay (0 - 11; Ocak = 0).|
|**tm_year**|Yıl (mevcut yıl eksi 1900).|
|**tm_wday**|Haftanın günü (0 - 6; Pazar = 0).|
|**tm_yday**|Yılın günü (0 - 365; 1 Ocak = 0).|
|**tm_isdst**|Gün ışığından yararlanma etkinse pozitif değer; gün ışığından yararlanma etkin değilse, 0; Yaz Saati durum bilinmiyorsa, negatif değer.|

Varsa **TZ** ortam değişkeninin ayarlı, C çalışma zamanı kitaplığı kuralları Amerika Birleşik Devletleri'nde uygun gün ışığından yararlanma saatinin (DST) hesaplanmasını uygulamak için varsayar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgisi|Gerekli C++ üst bilgisi|
|-------------|---------------------|-|
|**localtime_s**, **_localtime32_s**, **_localtime64_s**|\<TIME.h >|\<CTime > veya \<TIME.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
