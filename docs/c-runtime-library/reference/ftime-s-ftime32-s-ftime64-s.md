---
title: _ftime_s, _ftime32_s, _ftime64_s
ms.date: 11/04/2016
api_name:
- _ftime_s
- _ftime64_s
- _ftime32_s
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
ms.openlocfilehash: b45a22afc824a33e81170f954e6f99088b629f83
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956320"
---
# <a name="_ftime_s-_ftime32_s-_ftime64_s"></a>_ftime_s, _ftime32_s, _ftime64_s

Geçerli saati alır. Bunlar, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md) sürümleridir.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _ftime_s( struct _timeb *timeptr );
errno_t _ftime32_s( struct __timeb32 *timeptr );
errno_t _ftime64_s( struct __timeb64 *timeptr );
```

### <a name="parameters"></a>Parametreler

*timeptr*<br/>
**_Timeb**, **__timeb32**veya **__timeb64** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır, hata durumunda hata kodu. *Timeptr* **null**Ise, dönüş değeri **EINVAL**' dir.

## <a name="remarks"></a>Açıklamalar

**_Ftime_s** işlevi, geçerli yerel saati alır ve *timeptr*tarafından işaret edilen yapıda depolar. **_Timeb**, **__timeb32**ve **__timeb64** yapıları sys\timeb.exe içinde tanımlanmıştır. Bunlar, aşağıdaki tabloda listelenen dört alan içerirler.

|Alan|Açıklama|
|-|-|
|**dstflag**|Yerel Saat dilimi için günışığından tasarrutasarrufu süresi geçerli ise sıfır dışında. (Gün ışığından yararlanma zamanının nasıl belirlendiği hakkında bir açıklama için bkz. [_tzset](tzset.md) .)|
|**milimetre TM**|Saniyenin bir saniye cinsinden kesri.|
|**saat**|Gece yarısından bu yana geçen süre (00:00:00), 1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC).|
|**TI**|Dakikalar içinde, Westward, UTC ve yerel saat arasında hareket eden fark. **Saat dilimi** değeri, genel değişken **_saat dilimi** değerinden ayarlanır (bkz. **_tzset**).|

**__Timeb64** yapısını kullanan **_ftime64_s** işlevi, dosya oluşturma tarihlerinin 23:59:59, 31 Aralık 3000, UTC; tarihine kadar ifade etmesine olanak tanır. Ancak **_ftime32_s** yalnızca 23:59:59 tarihi 18 Ocak 2038, UTC olarak gösterir. Gece yarısı, 1 Ocak 1970, tüm bu işlevler için tarih aralığının alt sınırdır.

**_Ftime_s** işlevi **_ftime64_s**ile eşdeğerdir ve **_Timeb** , **_Use_32bit_time_t** tanımlanmadığı ve bu durumda eski davranış etkin olduğu müddetçe 64 bitlik bir zaman içerir; **_ftime_s** 32 bitlik bir süre kullanır ve **_timeb** , 32 bit bir zaman içerir.

**_ftime_s** , parametrelerini doğrular. Null bir işaretçi *timeptr*olarak geçirilmemişse, Işlev [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, işlev **errno** ' ı **EINVAL**olarak ayarlar.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_ftime_s**|\<sys/Types. h > ve \<sys/timeb. h >|
|**_ftime32_s**|\<sys/Types. h > ve \<sys/timeb. h >|
|**_ftime64_s**|\<sys/Types. h > ve \<sys/timeb. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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
