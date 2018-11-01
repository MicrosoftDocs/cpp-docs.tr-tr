---
title: _ftime_s, _ftime32_s, _ftime64_s
ms.date: 11/04/2016
apiname:
- _ftime_s
- _ftime64_s
- _ftime32_s
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
- _ftime_s
- _ftime64_s
- ftime_s
- _ftime32_s
- ftime32_s
- ftime64_s
helpviewer_keywords:
- ftime32_s function
- ftime_s function
- _ftime64_s function
- current time
- ftime64_s function
- time, getting current
- _ftime_s function
- _ftime32_s function
ms.assetid: d03080d9-a520-45be-aa65-504bdb197e8b
ms.openlocfilehash: 696b461cdb6b8d58bb668b996a99c5d0bb774d6c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435483"
---
# <a name="ftimes-ftime32s-ftime64s"></a>_ftime_s, _ftime32_s, _ftime64_s

Geçerli saati alır. Bunlar sürümleridir [_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _ftime_s( struct _timeb *timeptr );
errno_t _ftime32_s( struct __timeb32 *timeptr );
errno_t _ftime64_s( struct __timeb64 *timeptr );
```

### <a name="parameters"></a>Parametreler

*timeptr*<br/>
İşaretçi bir **_timeb**, **__timeb32**, veya **__timeb64** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır, bir hata kodu. Varsa *timeptr* olduğu **NULL**, dönüş değeri **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Ftime_s** işlevi, geçerli yerel saat alır ve işaret ettiği yapısında depolar *timeptr*. **_Timeb**, **__timeb32**, ve **__timeb64** yapıları SYS\Timeb.h içinde tanımlanır. Aşağıdaki tabloda listelenen dört alan içerirler.

|Alan|Açıklama|
|-|-|
|**dstflag**|Gün ışığından yararlanma saatine göre geçerli yerel saat dilimini ise sıfır olmayan. (Bkz [_tzset](tzset.md) gün ışığından yararlanma saatine nasıl belirlendiğini'nın açıklaması.)|
|**millitm**|Saniyenin milisaniye cinsinden.|
|**saat**|Saniye cinsinden gece yarısından itibaren saat (00: 00:00), 1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC).|
|**saat dilimi**|Dakika cinsinden farkı westward, yerel saat ve UTC arasında taşıma. Değerini **saat dilimi** genel değişkenin değerini ayarlamak **_timezone** (bkz **_tzset**).|

**_Ftime64_s** kullanan işlevi **__timeb64** yapısı, 23:59:59, 31 Aralık, 3000, UTC; yukarı ifade edilecek tarihleri dosya oluşturma sağlarken **_ftime32_s** yalnızca 23:59:59 18 Ocak 2038, UTC tarihleri temsil eder. Gece yarısı, 1 Ocak 1970, tüm bu işlevler için tarih aralığının alt sınırdır.

**_Ftime_s** işlev, eşdeğer **_ftime64_s**, ve **_timeb** 64-bit birer pr'nin **_use_32bıt_tıme_t** olduğu tanımlanan, bu durumda eski davranış geçerli olur; **_ftime_s** bir 32-bit kullanır ve **_timeb** 32-bit saati içerir.

**_ftime_s** kendi parametrelerini doğrular. Null bir işaretçi olarak geçirilmiş *timeptr*, işlev içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse işlev ayarlar **errno** için **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_ftime_s**|\<sys/Types.h > ve \<sys/timeb.h >|
|**_ftime32_s**|\<sys/Types.h > ve \<sys/timeb.h >|
|**_ftime64_s**|\<sys/Types.h > ve \<sys/timeb.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_ftime64_s.c
// This program uses _ftime64_s to obtain the current
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

   _ftime64_s( &timebuffer );

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
