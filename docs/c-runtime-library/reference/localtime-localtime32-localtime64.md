---
title: localtime, _localtime32, _localtime64
ms.date: 11/04/2016
api_name:
- _localtime64
- _localtime32
- localtime
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- localtime64
- _localtime64
- localtime32
- localtime
- _localtime32
helpviewer_keywords:
- localtime32 function
- _localtime32 function
- _localtime64 function
- localtime64 function
- localtime function
- time, converting values
ms.assetid: 4260ec3d-43ee-4538-b998-402a282bb9b8
ms.openlocfilehash: 7e2f39b3a1b6376e24d8a812d1074840862f398a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953341"
---
# <a name="localtime-_localtime32-_localtime64"></a>localtime, _localtime32, _localtime64

Bir saat değerini dönüştürür ve yerel saat dilimi için düzeltir. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md).

## <a name="syntax"></a>Sözdizimi

```C
struct tm *localtime( const time_t *sourceTime );
struct tm *_localtime32( const __time32_t *sourceTime );
struct tm *_localtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Parametreler

*sourceTime*<br/>
Saklı saate yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Yapı sonucuna bir işaretçi döndürün veya işleve geçirilen Tarih şu ise **null** olur:

- Gece yarısından önce, 1 Ocak 1970.

- 03:14:07 sonra, 19 Ocak 2038, UTC ( **_time32** ve **time32_t**kullanarak).

- 23:59:59 sonra, 31 Aralık 3000, UTC ( **_time64** ve **__time64_t**kullanarak).

**__time64_t** yapısını kullanan **_localtime64**, tarihlerin 23:59:59, Aralık 31, 3000, Eşgüdümlü Evrensel Saat (UTC) ile ifade etmesine izin verir, ancak **_localtime32** tarihleri 18 Ocak 2038, 23:59:59 ile gösterir. UTC.

**localtime** , **_localtime64**olarak değerlendirilen bir satır içi işlevdir ve **time_t** , **__time64_t**ile eşdeğerdir. Derleyicinin **time_t** 'i eski 32 bit **time_t**olarak yorumlamasını zorlamak Istiyorsanız **_Use_32bit_time_t**tanımlayabilirsiniz. Bunun yapılması **localtime** 'ın **_localtime32**olarak değerlendirilmesini sağlar. Uygulamanız 18 Ocak 2038 ' den sonra başarısız olabileceğinden ve 64-bit platformlarda izin verilmediği için bu önerilmez.

[TM](../../c-runtime-library/standard-types.md) yapı türü alanları, her biri bir **int**olan aşağıdaki değerleri depolar:

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

## <a name="remarks"></a>Açıklamalar

**Localtime** işlevi, [time_t](../../c-runtime-library/standard-types.md) değeri olarak depolanan bir saati dönüştürür ve sonucu [TM](../../c-runtime-library/standard-types.md)türünde bir yapıda depolar. **Long** değeri *sourcetime* , gece yarısı (00:00:00), 1 Ocak 1970, UTC 'den beri geçen saniyeleri temsil eder. Bu değer genellikle [zaman](time-time32-time64.md) işlevinden elde edilir.

[Gmtime](gmtime-gmtime32-gmtime64.md), [mktime](mktime-mktime32-mktime64.md), [mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md)ve **localtime** 'ın 32-bit ve 64 bit sürümleri, dönüştürme için iş parçacığı başına tek bir **TM** yapısı kullanır. Bu yordamların birine yapılan her bir çağrı, önceki çağrının sonucunu yok eder.

Kullanıcı ilk olarak **TZ**genel ortam değişkenini ayarladığında yerel saat dilimi için **yerelsaat** düzeltir. **TZ** ayarlandığında, diğer üç ortam değişkeni ( **_timezone**, **_gündüz**ve **_tzname**) de otomatik olarak ayarlanır. **TZ** değişkeni ayarlanmamışsa, **localtime** Denetim Masası 'ndaki Tarih/Saat uygulamasında belirtilen saat dilimi bilgilerini kullanmaya çalışır. Bu bilgiler alınamıyorsa, varsayılan olarak Pasifik saati dilimini belirten PST8PDT kullanılır. Bu değişkenlerin açıklaması için bkz. [_tzset](tzset.md) . **TZ** , bir Microsoft uzantısıdır ve **LOCALTIME**'ın ANSI standart tanımının bir parçası değildir.

> [!NOTE]
> Hedef ortam, gün ışığından yararlanma saatinin etkin olup olmadığını belirlemeyi denemelidir.

Bu işlevler, parametrelerini doğrular. *Sourcetime* null bir işaretçisiyse veya *sourcetime* değeri negatifse, bu işlevler [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, işlevler **null** döndürür ve **errno** , **EINVAL**olarak ayarlanır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgisi|Gerekli C++ üst bilgi|
|-------------|---------------------|-|
|**yerelsaat**, **_localtime32**, **_localtime64**|\<Time. h >|\<CTime > veya \<saati. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_localtime.cpp
// compile with: /W3
// This program uses _time64 to get the current time
// and then uses localtime64() to convert this time to a structure
// representing the local time. The program converts the result
// from a 24-hour clock to a 12-hour clock and determines the
// proper extension (AM or PM).

#include <stdio.h>
#include <string.h>
#include <time.h>

int main( void )
{
    struct tm *newtime;
    char am_pm[] = "AM";
    __time64_t long_time;

    _time64( &long_time );             // Get time as 64-bit integer.
                                       // Convert to local time.
    newtime = _localtime64( &long_time ); // C4996
    // Note: _localtime64 deprecated; consider _localetime64_s

    if( newtime->tm_hour > 12 )        // Set up extension.
        strcpy_s( am_pm, sizeof(am_pm), "PM" );
    if( newtime->tm_hour > 12 )        // Convert from 24-hour
        newtime->tm_hour -= 12;        //   to 12-hour clock.
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

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
