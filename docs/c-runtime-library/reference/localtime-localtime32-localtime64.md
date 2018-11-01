---
title: localtime, _localtime32, _localtime64
ms.date: 11/04/2016
apiname:
- _localtime64
- _localtime32
- localtime
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
ms.openlocfilehash: d34a45ff20cb74d61a8eb189282bfdce4d8954ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629976"
---
# <a name="localtime-localtime32-localtime64"></a>localtime, _localtime32, _localtime64

Bir saat değerine dönüştürür ve yerel saat dilimini düzeltir. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md).

## <a name="syntax"></a>Sözdizimi

```C
struct tm *localtime( const time_t *sourceTime );
struct tm *_localtime32( const __time32_t *sourceTime );
struct tm *_localtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Parametreler

*sourceTime*<br/>
Depolanan zamana yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Yapı sonucu için bir işaretçi döndürür veya **NULL** tarih işleve geçirilen ise:

- Gece yarısından önce 1 Ocak 1970.

- Sonra 03:14:07, Ocak 19, 2038, UTC (kullanarak **_time32** ve **time32_t**).

- Sonra 23:59:59, 31 Aralık, 3000, UTC (kullanarak **_time64** ve **__time64_t**).

**_localtime64**, kullanan **__time64_t** yapısı, 23:59:59, 31 Aralık, 3000, Eşgüdümlü Evrensel Saat (UTC), yedekleme ifade edilecek tarihleri sağlarken **_localtime32** 23:59:59 18 Ocak 2038, UTC tarihleri temsil eder.

**localtime** olarak değerlendirilen bir satır içi işlev **_localtime64**, ve **time_t** eşdeğerdir **__time64_t**. Yorumlamak üzere zorlamanız gerekirse **time_t** eski 32-bit olarak **time_t**, tanımlayabileceğiniz **_use_32bıt_tıme_t**. Bunun yapılması neden olacak **localtime** için değerlendirilecek **_localtime32**. Bu, 18 Ocak 2038 sonrasında uygulamanız çalışmayabilir ve 64-bit platformlarda izin verilmiyor çünkü önerilmez.

Yapı türü alanlarını [tm](../../c-runtime-library/standard-types.md) her biri aşağıdaki değerlerini depolayan bir **int**:

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

Varsa **TZ** ortam değişkeninin ayarlı, C çalışma zamanı kitaplığı kuralları Amerika Birleşik Devletleri'nde uygun Yaz Saati (DST) hesaplanmasını uygulamak için varsayar.

## <a name="remarks"></a>Açıklamalar

**Localtime** işlevi dönüştürür bir saat olarak depolanan bir [time_t](../../c-runtime-library/standard-types.md) değeri ve sonucu türündeki yapıda depolar [tm](../../c-runtime-library/standard-types.md). **Uzun** değer *sourceTime* saniye gece yarısından beri geçen temsil eder (00: 00:00), 1 Ocak 1970, UTC. Bu değer genellikle öğesinden alınan [zaman](time-time32-time64.md) işlevi.

Hem 32-bit ve 64 bit sürümlerini [gmtime](gmtime-gmtime32-gmtime64.md), [mktime](mktime-mktime32-mktime64.md), [mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md), ve **localtime** tüm tek kullanımlık **tm** yapısı dönüştürme için iş parçacığı başına. Bu yordamların her çağrısına, önceki çağrının sonucu yok eder.

**localtime** kullanıcı önce genel ortam değişkenini ayarlar, yerel saat dilimini düzeltir **TZ**. Zaman **TZ** ayarlandığında, üç ortam değişkenlerini (**_timezone**, **_daylight**, ve **_tzname**) de otomatik olarak ayarlanır. Varsa **TZ** değişkeni ayarlanmamış, **localtime** Denetim Masası'ndaki Tarih/saat uygulamasında belirtilen saat dilimi bilgilerini kullanmaya çalışır. Bu bilgileri alınamıyor, Pasifik Saat dilimini belirtir, PST8PDT, varsayılan olarak kullanılır. Bkz: [_tzset](tzset.md) bu değişkenleri açıklaması. **TZ** standart ANSI tanımının parçası değildir ve Microsoft uzantısı olduğundan **localtime**.

> [!NOTE]
> Gün ışığından yararlanma etkin olup olmadığını belirlemek hedef ortamı denemelisiniz.

Bu işlevler kendi parametrelerini doğrular. Varsa *sourceTime* null bir işaretçiyse veya *sourceTime* değeri negatif ise, bu işlevler içinde açıklanan şekilde geçersiz parametre işleyicisini çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md) . Yürütmenin devam etmesine izin verilirse, İşlevler döndürür **NULL** ayarlayıp **errno** için **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgisi|Gerekli C++ üst bilgisi|
|-------------|---------------------|-|
|**localtime**, **_localtime32**, **_localtime64**|\<TIME.h >|\<CTime > veya \<TIME.h >|

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
