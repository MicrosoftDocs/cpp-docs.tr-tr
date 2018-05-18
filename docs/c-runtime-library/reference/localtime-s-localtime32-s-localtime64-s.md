---
title: localtime_s, _localtime32_s, _localtime64_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _localtime64_s function
- localtime32_s function
- _localtime32_s function
- localtime64_s function
- time, converting values
- localtime_s function
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 513bfe5baa16c9cae5052da084c65f580aad7f2e
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="localtimes-localtime32s-localtime64s"></a>localtime_s, _localtime32_s, _localtime64_s

Dönüştüren bir **time_t** saat değeri için bir **tm** yapısı ve yerel saat dilimini düzeltir. Sürümleri bunlar [damgasını, _localtime32, _localtime64](localtime-localtime32-localtime64.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Doldurulacak zaman yapısına yönelik işaretçinin.

*sourceTime*<br/>
Saklı zaman işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Bir hata olduğunda dönüş değeri bir hata kodudur. Hata kodları Errno.h içinde tanımlanmıştır. Bu hataların listesi için bkz: [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Hata koşulları

|*tmDest*|*sourceTime*|Dönüş değeri|Değer *tmDest*|Geçersiz parametre işleyiciyi çağırır|
|-----------|------------|------------------|--------------------|---------------------------------------|
|**NULL**|tüm|**EINVAL**|değiştirilmedi|Evet|
|Değil **NULL** (noktaları için geçerli bellek)|**NULL**|**EINVAL**|Tüm alanları -1 olarak ayarlayın|Evet|
|Değil **NULL** (noktaları için geçerli bellek)|0'den küçük ya da daha büyük **_MAX__TIME64_T**|**EINVAL**|Tüm alanları -1 olarak ayarlayın|Hayır|

İlk iki hata koşulları söz konusu olduğunda geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve geri dönüp **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Localtime32_s** işlevi dönüştürür olarak saklanan bir süre bir [time_t](../../c-runtime-library/standard-types.md) değer ve sonuç türü yapısında depolar [tm](../../c-runtime-library/standard-types.md). **Uzun** değeri *sourceTime* gece yarısından beri geçen saniye temsil eder (00: 00:00), 1 Ocak 1970'den itibaren UTC. Bu değer genellikle alanından elde [zaman](time-time32-time64.md) işlevi.

**_localtime32_s** kullanıcı ilk genel ortam değişkeni ayarlarsa için yerel saat dilimi düzeltir **TZ**. Zaman **TZ** ayarlandığında, diğer üç ortam değişkenlerini (**_timezone**, **_daylight**, ve **_tzname**) otomatik olarak da ayarlanır. Varsa **TZ** değişken ayarlanmazsa **localtime32_s** tarih uygulama Denetim Masası'nda belirtilen saat dilimi bilgilerini kullanmaya çalışır. Bu bilgiler alınamıyor, Pasifik saat diliminde güveninin, PST8PDT varsayılan olarak kullanılır. Bkz: [_tzset](tzset.md) bu değişkenleri açıklaması. **TZ** bir Microsoft uzantısı ve ANSI standart tanımının parçası olmayan **damgasını**.

> [!NOTE]
> Hedef ortam gün ışığından yararlanma saati etkin olup olmadığını belirlemek denemelisiniz.

**_localtime64_s**, kullanan **__time64_t** yapısı, 23:59:59, Ocak 18 3001, Eşgüdümlü Evrensel Saat (UTC) ayarlama ifade tarihleri sağlarken **_localtime32_s** ile 23:59:59 18 Ocak 2038, UTC tarihleri temsil eder.

**localtime_s** değerlendiren bir satır içi işlev **_localtime64_s**, ve **time_t** eşdeğerdir **__time64_t**. Yorumlamaya derleyici zorlamak gerekiyorsa **time_t** eski 32 bit olarak **time_t**, tanımlayabileceğiniz **_USE_32BIT_TIME_T**. Bunun neden olacak **localtime_s** için değerlendirilecek **_localtime32_s**. Bu, uygulamanızın 18 Ocak 2038 sonra başarısız olabilir ve 64 bit platformlarda izin verilmiyor çünkü önerilmez.

Yapı türünde alanlar [tm](../../c-runtime-library/standard-types.md) , her biri aşağıdaki değerlerini depolayan bir **int**.

|Alan|Açıklama|
|-|-|
|**tm_sec**|Saniye dakika sonra (0 - 59).|
|**tm_min**|Dakika sonra saat (0 - 59).|
|**tm_hour**|Gece yarısından saat (0 - 23).|
|**tm_mday**|Ayın günü (1-31).|
|**tm_mon**|Ay (0 - 11; Ocak = 0).|
|**tm_year**|Yıl (1900 eksi geçerli yıl).|
|**tm_wday**|Haftanın günü (0 - 6; Pazar = 0).|
|**tm_yday**|Yılın günü (0 - 365; 1 Ocak = 0).|
|**tm_isdst**|Yaz Saati etkinse, pozitif bir değer; Yaz Saati etkin değilse, 0; Yaz Saati durumunu bilinmiyorsa negatif değer.|

Varsa **TZ** ortam değişkeni ayarlanmışsa, C çalışma zamanı kitaplığı kuralları Amerika Birleşik Devletleri uygun gün ışığından yararlanma saati (DST) hesaplama uygulamak üzere varsayar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgisi|Gerekli C++ üstbilgisi|
|-------------|---------------------|-|
|**localtime_s**, **_localtime32_s**, **_localtime64_s**|\<time.h >|\<CTime > veya \<time.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
