---
title: _mkgmtime, _mkgmtime32, _mkgmtime64
ms.date: 11/04/2016
apiname:
- _mkgmtime32
- _mkgmtime64
- _mkgmtime
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
- _mkgmtime64
- mkgmtime32
- _mkgmtime32
- mkgmtime
- mkgmtime64
- _mkgmtime
helpviewer_keywords:
- mkgmtime32 function
- time functions
- mkgmtime function
- _mkgmtime function
- converting times
- mkgmtime64 function
- _mkgmtime64 function
- _mkgmtime32 function
- time, converting
ms.assetid: b4ca2b67-e198-4f43-b3e2-e8ad6bd01867
ms.openlocfilehash: 65d96d79a45e05e4b371315c0612ed086f6ea2a0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452266"
---
# <a name="mkgmtime-mkgmtime32-mkgmtime64"></a>_mkgmtime, _mkgmtime32, _mkgmtime64

Tarafından temsil edilen UTC saati dönüştürür bir **yapı** **tm** UTC saati için temsil ettiği bir **time_t** türü.

## <a name="syntax"></a>Sözdizimi

```C
time_t _mkgmtime(
   struct tm* timeptr
);
__time32_t _mkgmtime32(
   struct tm* timeptr
);
__time64_t _mkgmtime64(
   struct tm* timeptr
);
```

### <a name="parameters"></a>Parametreler

*timeptr*<br/>
Bir işaretçi UTC saati için bir **yapı** **tm** dönüştürülecek.

## <a name="return-value"></a>Dönüş Değeri

Türünde bir miktar **__time32_t** veya **__time64_t** gece yarısı, 1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC) beri geçen saniye sayısını temsil eden. Tarih aralık dışında ise (Açıklamalar bölümüne bakın) veya giriş geçerli bir saat yorumlanamıyor, dönüş değeri -1'dir.

## <a name="remarks"></a>Açıklamalar

**_Mkgmtime32** ve **_mkgmtime64** işlevleri dönüştürmek için UTC saati bir **__time32_t** veya **__time64_t** saati temsil eden tür. UTC. Yerel saati UTC saati için dönüştürmek için **mktime**, **_mktime32**, ve **_mktime64** yerine.

**_mkgmtime** olarak değerlendirilen bir satır içi işlevdir **_mkgmtime64**, ve **time_t** eşdeğerdir **__time64_t**. Yorumlamak üzere zorlamanız gerekirse **time_t** eski 32-bit olarak **time_t**, tanımlayabileceğiniz **_use_32bıt_tıme_t**. 18 Ocak 2038 sonrasında uygulamanız işlemi başarısız olduğundan bu önerilmez (32 bit en büyük aralık **time_t**), ve onu tüm 64-bit platformlarda izin verilmez.

İle değiştirilmiş olarak yapısı geçirilen zaman aşağıdaki gibi aynı şekilde değiştirilecek **_mktime** işlevleri: **tm_wday** ve **tm_yday** alanları ayarlanmış yeni değerler temel değerlerine **tm_mday** ve **tm_year**. Belirtirken bir **tm** ayarlayın, yapı zaman **tm_isdst** alanı:

- Sıfır Standart Saati etkin olduğunu belirtmek için (0).

- Gün ışığından yararlanma saatine göre geçerli olduğunu göstermek için 0'dan büyük bir değer.

- Bir değeri sıfırdan küçük C çalışma zamanı kitaplık kodu için standart saat veya gün ışığından yararlanma etkin olup olmadığını işlem.

C çalışma zamanı kitaplığı TZ ortam değişkeninin doğru günışığından tasarruf belirlemek için kullanır. TZ ayarlanmazsa, işletim sistemi doğru bölgesel günışığından süresi davranışını almak için sorgulanır. **tm_isdst** gerekli bir alandır. Değeri tanımlanmamış ayarlanmazsa ve dönüş değeri **mktime** tahmin edilemez.

Aralığı **_mkgmtime32** işlev, 1 Ocak 1970 gece UTC ile 23:59:59 18 Ocak 2038, UTC. Aralığı **_mkgmtime64** 1 Ocak 1970 gece yarısı UTC ile olan 23:59:59, 31 Aralık, 3000, UTC olduğu. -1 dönüş değeri aralık dışı tarih sonuçlanır. Aralığı **_mkgmtime** bağlıdır **_use_32bıt_tıme_t** tanımlanır. (Varsayılan) tanımlı değil, aralığı **_mkgmtime64**; Aksi takdirde, 32-bit aralığı için sınırlı bir aralığı **_mkgmtime32**.

Unutmayın **gmtime** ve **localtime** dönüştürme için tek bir statik olarak ayrılan arabelleğin kullanın. Bu arabelleğin sağlarsanız **mkgmtime**, önceki içeriği yok edilir.

## <a name="example"></a>Örnek

```C
// crt_mkgmtime.c
#include <stdio.h>
#include <time.h>

int main()
{
    struct tm t1, t2;
    time_t now, mytime, gmtime;
    char buff[30];

    time( & now );

    _localtime64_s( &t1, &now );
    _gmtime64_s( &t2, &now );

    mytime = mktime(&t1);
    gmtime = _mkgmtime(&t2);

    printf("Seconds since midnight, January 1, 1970\n");
    printf("My time: %I64d\nGM time (UTC): %I64d\n\n", mytime, gmtime);

    /* Use asctime_s to display these times. */

    _localtime64_s( &t1, &mytime );
    asctime_s( buff, sizeof(buff), &t1 );
    printf( "Local Time: %s\n", buff );

    _gmtime64_s( &t2, &gmtime );
    asctime_s( buff, sizeof(buff), &t2 );
    printf( "Greenwich Mean Time: %s\n", buff );

}
```

### <a name="sample-output"></a>Örnek Çıktı

```Output
Seconds since midnight, January 1, 1970
My time: 1171588492
GM time (UTC): 1171588492

Local Time: Thu Feb 15 17:14:52 2007

Greenwich Mean Time: Fri Feb 16 01:14:52 2007
```

Aşağıdaki örnek, tamamlanmamış yapısı yılın günü ve haftanın hesaplanan değerlerle nasıl doldurulur gösterir.

```C
// crt_mkgmtime2.c
#include <stdio.h>
#include <time.h>
#include <memory.h>

int main()
{
    struct tm t1, t2;
    time_t gmtime;
    char buff[30];

    memset(&t1, 0, sizeof(struct tm));
    memset(&t2, 0, sizeof(struct tm));

    t1.tm_mon = 1;
    t1.tm_isdst = 0;
    t1.tm_year = 103;
    t1.tm_mday = 12;

    // The day of the week and year will be incorrect in the output here.
    asctime_s( buff, sizeof(buff), &t1);
    printf("Before calling _mkgmtime, t1 = %s t.tm_yday = %d\n",
            buff, t1.tm_yday );

    gmtime = _mkgmtime(&t1);

    // The correct day of the week and year were determined.
    asctime_s( buff, sizeof(buff), &t1);
    printf("After calling _mkgmtime, t1 = %s t.tm_yday = %d\n",
            buff, t1.tm_yday );

}
```

### <a name="output"></a>Çıkış

```Output
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003
t.tm_yday = 0
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003
t.tm_yday = 42
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
