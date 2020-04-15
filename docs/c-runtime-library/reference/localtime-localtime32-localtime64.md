---
title: localtime, _localtime32, _localtime64
ms.date: 4/2/2020
api_name:
- _localtime64
- _localtime32
- localtime
- _o__localtime32
- _o__localtime64
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
ms.openlocfilehash: 21496b71c354c7bed7b87526dc40bc9b24865da2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342130"
---
# <a name="localtime-_localtime32-_localtime64"></a>localtime, _localtime32, _localtime64

Bir saat değerini dönüştürür ve yerel saat dilimi için düzeltir. Bu işlevlerin daha güvenli sürümleri mevcuttur; [localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
struct tm *localtime( const time_t *sourceTime );
struct tm *_localtime32( const __time32_t *sourceTime );
struct tm *_localtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Parametreler

*kaynakZaman*<br/>
Zaman depolanan işaretçi.

## <a name="return-value"></a>Dönüş Değeri

İşleve geçirilen tarih aşağıdakileri gerçekse, bir işaretçiyi yapı sonucuna veya **NULL'a** döndürün:

- 1 Ocak 1970 gece yarısından önce.

- 03:14:07 sonra, Ocak 19, 2038, UTC **(_time32** ve **time32_t**kullanarak).

- 23:59:59, 31 Aralık 3000, UTC **(_time64** ve **__time64_t**kullanarak) sonra.

**__time64_t**yapısını kullanan **__time64_t** _localtime64 tarihlerin 23:59:59, 31 Aralık 3000, eşgüdümlü evrensel saat (UTC) ile ifade edilmesine izin verirken, **_localtime32** tarihleri 23:59:59 18 Ocak 2038, UTC'ye kadar temsil eder.

**yerel** **saat, _localtime64**değerlendiren bir satır dışı işlevdir ve **time_t** **__time64_t**eşdeğerdir. Derleyiciyi **time_t** eski 32 bit **time_t**olarak yorumlamaya zorlamanız gerekiyorsa, **_USE_32BIT_TIME_T**tanımlayabilirsiniz. Bunu yapmak **yerel saatin** **_localtime32**değer baçması için neden olur. Başvurunuz 18 Ocak 2038'den sonra başarısız olabileceğinden ve 64 bit platformlarda izin verilmediği için bu önerilmez.

Yapı türü [tm](../../c-runtime-library/standard-types.md) alanları aşağıdaki değerleri depolar, her biri bir **int:**

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

**TZ** ortam değişkeni ayarlanırsa, C çalışma zamanı kitaplığı, gün ışığından yararlanma zamanının (DST) hesaplanması için ABD'ye uygun kuralları varsayar.

## <a name="remarks"></a>Açıklamalar

**Yerel saat** [işlevi, time_t](../../c-runtime-library/standard-types.md) değeri olarak depolanan bir saati dönüştürür ve sonucu [tm](../../c-runtime-library/standard-types.md)türünde bir yapıda depolar. **Uzun** değer *kaynağıZaman,* gece yarısından (00:00:00), 1 Ocak 1970, UTC'den bu yana geçen saniyeleri temsil eder. Bu değer genellikle [zaman](time-time32-time64.md) fonksiyonu elde edilir.

[Gmtime,](gmtime-gmtime32-gmtime64.md) [mktime,](mktime-mktime32-mktime64.md) [mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md)ve **localtime'ın** 32 bit ve 64 bit sürümlerinde dönüşüm için iş parçacığı başına tek bir **tm** yapısı kullanılır. Bu yordamlardan birine yapılan her arama, önceki aramanın sonucunu yok eder.

kullanıcı ilk olarak global çevre değişkeni **TZ'yi**ayarlarsa **yerel saat** dilimini düzeltir. **TZ** ayarlandığında, diğer üç ortam değişkeni **(_timezone,** **_daylight**ve **_tzname)** otomatik olarak ayarlanır. **TZ** değişkeni ayarlanmamışsa, **yerel saat** Denetim Masası'ndaki Tarih/Saat uygulamasında belirtilen saat dilimi bilgilerini kullanmaya çalışır. Bu bilgiler elde edilemiyorsa, Pasifik Saat Dilimini ifade eden PST8PDT varsayılan olarak kullanılır. Bu değişkenlerin açıklaması için [_tzset](tzset.md) bakın. **TZ,** ANSI standart **yerel saat**tanımının bir parçası değildir.

> [!NOTE]
> Hedef ortam, gün ışığından yararlanma saatinin geçerli olup olmadığını belirlemeye çalışmalıdır.

Bu işlevler parametrelerini doğrular. *SourceTime* null işaretçisi ise veya *kaynakZaman* değeri negatifse, bu işlevler [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre işleyicisi çağırır. Yürütmedevam etmesine izin verilirse, işlevler **NULL** döndürdü ve **EINVAL** **için errno** ayarlayın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgi|Gerekli C++ üstbilgi|
|-------------|---------------------|-|
|**localtime**, **_localtime32**, **_localtime64**|\<time.h>|\<ctime> \<veya time.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
