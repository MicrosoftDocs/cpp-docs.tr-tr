---
title: _mkgmtime, _mkgmtime32, _mkgmtime64
description: C Runtime kitaplığı işlevlerinin _mkgmtime, _mkgmtime32 ve _mkgmtime64 açıklar ve bunların nasıl kullanılacağına örnekler verir.
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: e8b3170fc0413a878777035fd76aac5eefa7b6bf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338767"
---
# <a name="_mkgmtime-_mkgmtime32-_mkgmtime64"></a>_mkgmtime, _mkgmtime32, _mkgmtime64

Bir **yapı** **tm** tarafından temsil edilen UTC süresini **time_t** türüyle temsil edilen UTC zamanına dönüştürür.

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
Dönüştürmek için bir **yapı** **tm** olarak UTC zaman için bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

1 Ocak 1970 gece yarısından bu yana geçen saniye sayısını temsil eden **__time32_t** veya **__time64_t** türü, Eşgüdümlü Evrensel Saat'te (UTC) bulunur. Tarih aralık dışındaysa (Açıklamalar bölümüne bakın) veya giriş geçerli bir saat olarak yorumlanamazsa, iade değeri -1'dir.

## <a name="remarks"></a>Açıklamalar

**_mkgmtime32** ve **_mkgmtime64** işlevleri, UTC'deki zamanı temsil eden bir **__time32_t** veya **__time64_t** türüne UTC zamanını dönüştürür. Yerel saati UTC saatine dönüştürmek için **mktime**, **_mktime32**ve bunun yerine **_mktime64** kullanın.

**_mkgmtime** **_mkgmtime64**değerlendiren bir satır dışı işlevdir ve **time_t** **__time64_t**eşdeğerdir. Derleyiciyi **time_t** eski 32 bit **time_t**olarak yorumlamaya zorlamanız gerekiyorsa, **_USE_32BIT_TIME_T**tanımlayabilirsiniz. Başvurunuz 18 Ocak 2038 tarihinden sonra başarısız olabileceğinden, 32 **bitlik**bir time_t maksimum aralığı nasibini alabilirsiniz. 64 bit platformlarda buna izin verilmiyor.

Geçirilen zaman yapısı, **_mktime** işlevleri ile değiştirildiği gibi aşağıdaki gibi değiştirilir: **tm_wday** ve **tm_yday** alanları **tm_mday** ve **tm_year**değerlerine göre yeni değerlere ayarlanır. Zaman UTC olarak kabul edilir, tm_isdst **alanı** yoksayılır.

**_mkgmtime32** fonksiyonunun aralığı 1 Ocak 1970, UTC ile 23:59:59 ocak 18, 2038, UTC gece yarısı arasındadır. **_mkgmtime64** aralığı 1 Ocak 1970, UTC gece yarısı, UTC ile 23:59:59, 31 Aralık 3000, UTC arasındadır. Aralık dışı bir tarih , -1'in geri dönüş değeriyle sonuçlanır. **_mkgmtime** aralığı **_USE_32BIT_TIME_T** tanımlanıp tanımlanmadığına bağlıdır. Varsayılan olan tanımlanmadığında, aralık **_mkgmtime64.** Aksi takdirde, aralık **_mkgmtime32**32-bit aralığı ile sınırlıdır.

Hem **gmtime** hem de **localtime** dönüştürme için ortak bir statik arabellek kullanır. Bu arabelleği **_mkgmtime**sağlarsanız, önceki içerik yok edilir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

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

Aşağıdaki örnek, eksik yapının **_mkgmtime**tarafından nasıl doldurulduğunu gösterir. Hem haftanın günü hem de yılın değerlerini hesaplar.

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

[Zaman Yönetimi](../../c-runtime-library/time-management.md)\
[asctime, _wasctime](asctime-wasctime.md)\
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)\
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)\
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)\
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)\
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)\
[time, _time32, _time64](time-time32-time64.md)
