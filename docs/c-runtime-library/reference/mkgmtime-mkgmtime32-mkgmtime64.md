---
title: _mkgmtime, _mkgmtime32, _mkgmtime64
description: _Mkgmtime, _mkgmtime32 ve _mkgmtime64 C çalışma zamanı kitaplığı işlevlerini açıklar ve bunların nasıl kullanılacağına ilişkin örnekler verir.
ms.date: 4/2/2020
api_name:
- _mkgmtime32
- _mkgmtime64
- _mkgmtime
- _o__mkgmtime32
- _o__mkgmtime64
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
ms.openlocfilehash: 4b20073a2022c7da59a5e224a04051901b7b8a4f
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914650"
---
# <a name="_mkgmtime-_mkgmtime32-_mkgmtime64"></a>_mkgmtime, _mkgmtime32, _mkgmtime64

**Struct** **TM** tarafından temsil edilen UTC zamanını, **TIME_T** türü tarafından temsil edilen UTC zamanına dönüştürür.

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

*timeptr*\
Dönüştürülecek **Yapı** **TM** olarak UTC zamanına yönelik bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC) ile gece yarısından beri geçen saniye sayısını temsil eden **__time32_t** veya **__time64_t** türünde bir miktar. Tarih Aralık dışında (açıklamalar bölümüne bakın) veya giriş geçerli bir saat olarak yorumlanamaz, dönüş değeri-1 ' dir.

## <a name="remarks"></a>Açıklamalar

**_Mkgmtime32** ve **_mkgmtime64** işlevleri UTC olarak saati temsil eden bir **__time32_t** veya **__time64_t** türüne dönüştürür. Yerel saati UTC zamanına dönüştürmek için, bunun yerine **mktime**, **_mktime32**ve **_mktime64** kullanın.

**_mkgmtime** , **_mkgmtime64**değerlendirilen bir satır içi işlevdir ve **time_t** **__time64_t**eşdeğerdir. Derleyicinin **time_t** eski 32 bit **time_t**olarak yorumlamasını zorlamak istiyorsanız **_USE_32BIT_TIME_T**tanımlayabilirsiniz. Uygulamanız 18 Ocak 2038 ' den sonra, 32 bit **time_t**maksimum aralığında başarısız olabileceğinden, bunu önermiyoruz. Tüm 64-bit platformlarda izin verilmez.

Geçirilen zaman yapısı, **_mktime** işlevleri tarafından değiştirildiği şekilde aşağıdaki şekilde değiştirilmiştir: **tm_wday** ve **tm_yday** alanları **tm_mday** ve **tm_year**değerlerine göre yeni değerler olarak ayarlanır. Zamanın UTC olduğu varsayılır, **tm_isdst** alanı yok sayılır.

**_Mkgmtime32** işlevin aralığı gece yarısı, 1 Ocak 1970, utc 'Den 23:59:59 Ocak 2038, UTC 'ye kadar. **_Mkgmtime64** aralığı gece yarısı, 1 Ocak 1970, utc 'den 23:59:59, 31 Aralık 3000, UTC 'den. Aralık dışı bir tarih,-1 dönüş değeri ile sonuçlanır. **_Mkgmtime** aralığı **_USE_32BIT_TIME_T** tanımlanıp tanımlanamayacağını bağlıdır. Tanımlı olmadığında, varsayılan olarak Aralık **_mkgmtime64**aynıdır. Aksi takdirde, Aralık 32-bit **_mkgmtime32**ile sınırlıdır.

Hem **gmtime** hem de **localtime** , dönüştürme için ortak bir statik arabellek kullanır. Bu arabelleği **_mkgmtime**sağlarsanız, önceki içerikler yok edilir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="examples"></a>Örnekler

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

```Output
Seconds since midnight, January 1, 1970
My time: 1171588492
GM time (UTC): 1171588492

Local Time: Thu Feb 15 17:14:52 2007

Greenwich Mean Time: Fri Feb 16 01:14:52 2007
```

Aşağıdaki örnek, tamamlanmamış yapının **_mkgmtime**tarafından nasıl doldurulacağını gösterir. Hem haftanın hem de yılın günü için değerleri hesaplar.

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

```Output
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003
t.tm_yday = 0
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003
t.tm_yday = 42
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman yönetimi](../../c-runtime-library/time-management.md)\
[yoksaati, _wasctime](asctime-wasctime.md)\
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)\
[gmsaati, _gmtime32 _gmtime64](gmtime-gmtime32-gmtime64.md)\
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)\
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)\
[mktime, _mktime32 _mktime64](mktime-mktime32-mktime64.md)\
[time, _time32, _time64](time-time32-time64.md)
