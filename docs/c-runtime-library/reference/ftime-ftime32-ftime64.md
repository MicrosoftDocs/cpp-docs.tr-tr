---
title: _ftime, _ftime32, _ftime64
ms.date: 4/2/2020
api_name:
- _ftime64
- _ftime
- _ftime32
- _o__ftime32
- _o__ftime64
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
- _ftime32
- _ftime
- _ftime64
- ftime64
- ftime
- ftime32
helpviewer_keywords:
- ftime64 function
- _ftime64 function
- current time
- _ftime function
- ftime function
- _ftime32 function
- ftime32 function
- time, getting current
ms.assetid: 96bc464c-3bcd-41d5-a212-8bbd836b814a
ms.openlocfilehash: 4e06eec975f02744c4b49c1980383c2ab2338ddc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345577"
---
# <a name="_ftime-_ftime32-_ftime64"></a>_ftime, _ftime32, _ftime64

Geçerli zamanı alın. Bu işlevlerin daha güvenli sürümleri mevcuttur; [_ftime_s, _ftime32_s, _ftime64_s](ftime-s-ftime32-s-ftime64-s.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
void _ftime( struct _timeb *timeptr );
void _ftime32( struct __timeb32 *timeptr );
void _ftime64( struct __timeb64 *timeptr );
```

### <a name="parameters"></a>Parametreler

*timeptr*<br/>
**_timeb,** **__timeb32**veya **__timeb64** bir yapıya işaretçi.

## <a name="remarks"></a>Açıklamalar

**_ftime** işlevi geçerli yerel saati alır ve *zaman ptr*tarafından işaret edilen yapıda depolar. **_timeb**, **__timeb32**, ve **__timeb64** yapıları \<sys\\timeb.h> tanımlanır. Aşağıdaki tabloda listelenen dört alan içerir.

|Alan|Açıklama|
|-|-|
|**dstflag**|Yerel saat dilimi için gün ışığından yararlanma saati şu anda geçerliyse sıfırdeğildir. (Gün ışığından yararlanma saatinin nasıl belirlendiği yle ilgili bir açıklama için [_tzset](tzset.md) bakınız.)|
|**militm**|Milisaniye cinsinden saniyenin kesir.|
|**time**|Gece yarısından saniye cinsinden (00:00:00), 1 Ocak 1970, eşgüdümlü evrensel saat (UTC).|
|**Zaman dilim**|Dakika farkı, utc ve yerel saat arasında, batıya doğru hareket. **Saat diliminin** değeri, **_timezone** genel değişkenin değerinden ayarlanır (bkz. **_tzset).**|

**__timeb64** yapısını kullanan **_ftime64** işlevi, dosya oluşturma tarihlerinin 23:59:59, 31 Aralık 3000, UTC' ye kadar ifade edilmesine olanak tanır; **_ftime32** ise sadece 23:59:59 18 Ocak 2038, UTC tarihleri temsil eder. Midnight, 1 Ocak 1970, tüm bu işlevler için tarih aralığının alt sınırıdır.

**_ftime** işlevi **_ftime64**eşdeğerdir ve **_USE_32BIT_TIME_T** tanımlanmadıkça **_timeb** 64 bitlik bir süre içerir, bu durumda eski davranış geçerlidir; **_ftime** 32 bit, **_timeb** 32 bit lik bir zaman içerir.

**_ftime** parametrelerini doğrular. Null işaretçisi *zaman ptr*olarak geçerse, işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, işlev **EINVAL** **için errno** ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_ftime**|\<sys/types.h> \<ve sys/timeb.h>|
|**_ftime32**|\<sys/types.h> \<ve sys/timeb.h>|
|**_ftime64**|\<sys/types.h> \<ve sys/timeb.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_ftime.c
// compile with: /W3
// This program uses _ftime to obtain the current
// time and then stores this time in timebuffer.

#include <stdio.h>
#include <sys/timeb.h>
#include <time.h>

int main( void )
{
   struct _timeb timebuffer;
   char timeline[26];
   errno_t err;
   time_t time1;
   unsigned short millitm1;
   short timezone1;
   short dstflag1;

   _ftime( &timebuffer ); // C4996
   // Note: _ftime is deprecated; consider using _ftime_s instead

   time1 = timebuffer.time;
   millitm1 = timebuffer.millitm;
   timezone1 = timebuffer.timezone;
   dstflag1 = timebuffer.dstflag;

   printf( "Seconds since midnight, January 1, 1970 (UTC): %I64d\n",
   time1);
   printf( "Milliseconds: %d\n", millitm1);
   printf( "Minutes between UTC and local time: %d\n", timezone1);
   printf( "Daylight savings time flag (1 means Daylight time is in "
           "effect): %d\n", dstflag1);

   err = ctime_s( timeline, 26, & ( timebuffer.time ) );
   if (err)
   {
       printf("Invalid argument to ctime_s. ");
   }
   printf( "The time is %.19s.%hu %s", timeline, timebuffer.millitm,
           &timeline[20] );
}
```

```Output
Seconds since midnight, January 1, 1970 (UTC): 1051553334
Milliseconds: 230
Minutes between UTC and local time: 480
Daylight savings time flag (1 means Daylight time is in effect): 1
The time is Mon Apr 28 11:08:54.230 2003
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
