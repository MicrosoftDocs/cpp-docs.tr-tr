---
description: 'Hakkında daha fazla bilgi edinin: localtime_s, _localtime32_s, _localtime64_s'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 856ab5610d176e3a5b2b928bda36154dd071fea5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198823"
---
# <a name="localtime_s-_localtime32_s-_localtime64_s"></a>localtime_s, _localtime32_s, _localtime64_s

Bir **time_t** zamanı değerini bir **TM** yapısına dönüştürür ve yerel saat dilimi için düzeltir. Bu sürümler, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklanan şekilde, güvenlik geliştirmeleriyle [localtime, _localtime32 _localtime64](localtime-localtime32-localtime64.md) sürümleridir.

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
Doldurulacak zaman yapısına yönelik işaretçi.

*sourceTime*<br/>
Saklı saate yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Hata varsa dönüş değeri bir hata kodudur. Hata kodları errno. h içinde tanımlanır. Bu hataların listelenmesi için bkz. [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Hata koşulları

|*tmDest*|*sourceTime*|Döndürülen değer|*Tmdest* değeri|Geçersiz parametre işleyicisini çağırır|
|-----------|------------|------------------|--------------------|---------------------------------------|
|**DEĞER**|herhangi biri|**EıNVAL**|Değiştirilmedi|Evet|
|**Null** değil (geçerli belleğe işaret eder)|**DEĞER**|**EıNVAL**|Tüm alanlar-1 olarak ayarlandı|Evet|
|**Null** değil (geçerli belleğe işaret eder)|0 ' dan küçük veya **_MAX__TIME64_T** değerinden büyük|**EıNVAL**|Tüm alanlar-1 olarak ayarlandı|Hayır|

İlk iki hata koşulu durumunda, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** olarak **EINVAL** ve **EINVAL** döndürür.

## <a name="remarks"></a>Açıklamalar

**Localtime_s** işlevi, [time_t](../../c-runtime-library/standard-types.md) değer olarak depolanan bir saati dönüştürür ve sonucu [TM](../../c-runtime-library/standard-types.md)türünde bir yapıda depolar. *Sourcetime* **time_t** değeri, gece yarısı (00:00:00), 1 Ocak 1970, UTC 'den beri geçen saniyeleri temsil eder. Bu değer genellikle [zaman](time-time32-time64.md) işlevinden elde edilir.

**localtime_s** , Kullanıcı Ilk olarak **TZ** genel ortam değişkenini ayarladığında yerel saat dilimine göre düzeltir. **TZ** ayarlandığında, diğer üç ortam değişkeni (**_timezone**, **_daylight** ve **_tzname**) de otomatik olarak ayarlanır. **TZ** değişkeni ayarlanmamışsa, **localtime_s** Denetim Masası 'ndaki Tarih/Saat uygulamasında belirtilen saat dilimi bilgilerini kullanmaya çalışır. Bu bilgiler alınamıyorsa, varsayılan olarak Pasifik saati dilimini belirten PST8PDT kullanılır. Bu değişkenlerin açıklaması için bkz. [_tzset](tzset.md) . **TZ** , bir Microsoft uzantısıdır ve **LOCALTIME**'ın ANSI standart tanımının bir parçası değildir.

> [!NOTE]
> Hedef ortam, gün ışığından yararlanma saatinin etkin olup olmadığını belirlemeyi denemelidir.

**__time64_t** yapısını kullanan **_localtime64_s**, tarihin 18 Ocak 3001, Eşgüdümlü Evrensel Saat (UTC) ile 23:59:59 arasında ifade etmesine izin verir, ancak **_localtime32_s** tarihleri 18 Ocak 2038, UTC 23:59:59 ile gösterir.

**localtime_s** , **_localtime64_s** değerlendirilen ve **time_t** **__time64_t** eşdeğer bir satır içi işlevdir. Derleyicinin **time_t** eski 32 bit **time_t** olarak yorumlamasını zorlamak istiyorsanız **_USE_32BIT_TIME_T** tanımlayabilirsiniz. Bunu yapmak **localtime_s** **_localtime32_s** değerlendirmesine neden olur. Uygulamanız 18 Ocak 2038 ' den sonra başarısız olabileceğinden ve 64-bit platformlarda izin verilmediği için bu önerilmez.

[TM](../../c-runtime-library/standard-types.md) yapı türü alanları, her biri bir olan aşağıdaki değerleri depolar **`int`** .

|Alan|Açıklama|
|-|-|
|**tm_sec**|Dakika sonra saniye (0-59).|
|**tm_min**|Saat sonra dakika (0-59).|
|**tm_hour**|Gece yarısından itibaren saat (0-23).|
|**tm_mday**|Ayın günü (1-31).|
|**tm_mon**|Ay (0-11; Ocak = 0).|
|**tm_year**|Yıl (geçerli yıl eksi 1900).|
|**tm_wday**|Haftanın günü (0-6; Pazar = 0).|
|**tm_yday**|Yılın günü (0-365; 1 Ocak = 0).|
|**tm_isdst**|Gün ışığından yararlanma saati etkin ise pozitif değer; gün ışığından yararlanma saati etkin değilse 0; gün ışığından yararlanma saatinin durumu bilinmiyorsa negatif değer.|

**TZ** ortam değişkeni ayarlandıysa, C çalışma zamanı kitaplığı, gün ışığından yararlanma ZAMANıNıN (DST) hesaplanmasını uygulamak için Birleşik Devletler uygun kuralları kabul eder.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgisi|Gerekli C++ üstbilgisi|
|-------------|---------------------|-|
|**localtime_s**, **_localtime32_s**, **_localtime64_s**|\<time.h>|\<ctime> veya \<time.h>|

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
