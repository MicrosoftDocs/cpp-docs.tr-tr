---
title: _mkgmtime, _mkgmtime32, _mkgmtime64
ms.date: 11/04/2016
api_name:
- _mkgmtime32
- _mkgmtime64
- _mkgmtime
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
ms.openlocfilehash: fcd1e3fdcca37d7e5bb381c234a6d8555ce2766c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951664"
---
# <a name="_mkgmtime-_mkgmtime32-_mkgmtime64"></a>_mkgmtime, _mkgmtime32, _mkgmtime64

**Struct** **TM** tarafından temsil edilen UTC zamanını bir **time_t** türüyle temsil edilen UTC zamanına dönüştürür.

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
Dönüştürülecek **Yapı** **TM** olarak UTC zamanına yönelik bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC) cinsinden gece yarısından beri geçen saniye sayısını temsil eden **__time32_t** veya **__time64_t** türünde bir miktar. Tarih Aralık dışında (açıklamalar bölümüne bakın) veya giriş geçerli bir saat olarak yorumlanamaz, dönüş değeri-1 ' dir.

## <a name="remarks"></a>Açıklamalar

**_Mkgmtime32** ve **_mkgmtime64** işlevleri UTC olarak saati temsil eden bir **__time32_t** veya **__time64_t** türüne dönüştürür. Yerel saati UTC saatine dönüştürmek için, bunun yerine **mktime**, **_mktime32**ve **_mktime64** kullanın.

**_mkgmtime** , **_mkgmtime64**olarak değerlendirilen bir satır içi işlevdir ve **time_t** , **__time64_t**ile eşdeğerdir. Derleyicinin **time_t** 'i eski 32 bit **time_t**olarak yorumlamasını zorlamak Istiyorsanız **_Use_32bit_time_t**tanımlayabilirsiniz. Uygulamanız 18 Ocak 2038 (en fazla 32 bit **time_t**) ile başarısız olabileceğinden ve tüm 64-bit platformlarda izin verilmediği için bu önerilmez.

Geçirilen zaman yapısı, **_mktime** işlevleriyle değiştirildikleri şekilde aşağıdaki şekilde değiştirilir: **tm_wday** ve **tm_yday** alanları **tm_mday** ve **tm_year**değerlerine göre yeni değerler olarak ayarlanır. Bir **TM** yapı süresi belirtirken, **tm_isdst** alanını şu şekilde ayarlayın:

- Standart saatin geçerli olduğunu belirtmek için sıfır (0).

- Gün ışığından yararlanma saatinin etkin olduğunu göstermek için 0 ' dan büyük bir değer.

- Standart saat veya yaz saati kaydetme saatinin etkin olup olmadığını C çalışma zamanı kitaplığı kodunun işlem için sıfırdan küçük bir değer.

C çalışma zamanı kitaplığı, doğru gün ışığından yararlanma süresini belirleyebilmek için TZ ortam değişkenini kullanır. TZ ayarlanmamışsa, doğru bölgesel gün tasarrufu süresi davranışını almak için işletim sistemi sorgulanır. **tm_isdst** , gerekli bir alandır. Ayarlanmamışsa, değeri tanımsızdır ve **mktime** 'den dönüş değeri tahmin edilemez.

**_Mkgmtime32** işlevinin aralığı gece yarısı, 1 Ocak 1970, UTC, 18 Ocak 2038, utc 'den 23:59:59 ' dir. **_Mkgmtime64** aralığı gece yarısı, 1 Ocak 1970, utc 'den 23:59:59, 31 Aralık 3000, UTC 'den. Aralık dışı bir tarih,-1 dönüş değeri ile sonuçlanır. **_Mkgmtime** aralığı, **_Use_32bit_time_t** öğesinin tanımlanıp tanımlanmayacağı. Tanımlanmamışsa (varsayılan), Aralık **_mkgmtime64**' dir; Aksi takdirde, Aralık 32 bitlik **_mkgmtime32**aralığı ile sınırlıdır.

**Gmtime** ve **localtime** ' ın dönüştürme için tek bir statik olarak ayrılan bir arabellek kullanmasını unutmayın. Bu arabelleği **mkgmtime**için sağlarsanız, önceki içerik yok edilir.

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

Aşağıdaki örnek, tamamlanmamış yapının Haftanın gününün hesaplanan değerleriyle ve yılın gününe nasıl doldurulacağını gösterir.

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
