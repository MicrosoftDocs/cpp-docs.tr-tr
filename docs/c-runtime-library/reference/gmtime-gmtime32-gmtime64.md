---
title: gmtime, _gmtime32, _gmtime64
ms.date: 4/2/2020
api_name:
- _gmtime32
- gmtime
- _gmtime64
- _o__gmtime32
- _o__gmtime64
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
- gmtime
- _gmtime32
- _gmtime64
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
ms.openlocfilehash: 16f4315837873c8d78065ea97a11188bdddedbed
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916231"
---
# <a name="gmtime-_gmtime32-_gmtime64"></a>gmtime, _gmtime32, _gmtime64

**Time_t** saat değerini bir **TM** yapısına dönüştürür. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md).

## <a name="syntax"></a>Sözdizimi

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Parametreler

*sourceTime*<br/>
Saklı saate yönelik işaretçi. Süre gece yarısı (00:00:00), 1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC) itibariyle geçen saniye olarak gösterilir.

## <a name="return-value"></a>Dönüş Değeri

[TM](../../c-runtime-library/standard-types.md)türünde bir yapıya yönelik işaretçi. Döndürülen yapının alanları, *sourcetime* bağımsız değişkeninin değerlendirilen değerini yerel saat yerine UTC olarak tutar. Yapı alanlarının her biri, aşağıdaki gibi **int**türündedir:

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
|**tm_isdst**|**Gmtime**için her zaman 0.|

Yalnızca **gmtime**, [mktime](mktime-mktime32-mktime64.md), [mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md)ve [localtime](localtime-localtime32-localtime64.md) 'ın 32-bit ve 64 bit sürümleri, dönüştürme için iş parçacığı başına bir ortak **TM** yapısı kullanır. Bu işlevlerden birine yapılan her bir çağrı, önceki çağrının sonucunu yok eder. *Sourcetime* gece yarısından önce bir tarihi gösteriyorsa, 1 Ocak 1970, **gmzamanı** **null**değerini döndürür. Hata döndürme yok.

**__time64_t** yapısını kullanan **_gmtime64**, Tarih 23:59:59, 31 Aralık 3000, UTC, saat **_gmtime32** yalnızca tarihleri 18 Ocak 2038, UTC 23:59:59 ile ifade eder. 1 Ocak 1970 gece yarısı, her iki işlev için de tarih aralığının alt sınırıdır.

**gmtime** , **_gmtime64**değerlendirilen bir satır içi işlevdir ve **_USE_32BIT_TIME_T** tanımlanmadığı müddetçe **__time64_t** eşdeğerdir **time_t** . Derleyicinin **time_t** eski 32 bit **time_t**olarak yorumlaması için zorladıysanız **_USE_32BIT_TIME_T**tanımlayabilirsiniz, ancak bunu yapmak **gmzamanının** **_gmtime32** ve **time_t** **__time32_t**olarak tanımlanmasına neden olur. Bunu, 64-bit platformlarda izin verilmediğinden ve uygulamanız 18 Ocak 2038 ' den sonra başarısız olabileceğinden, bunu yapmanızı öneririz.

Bu işlevler, parametrelerini doğrular. *Sourcetime* null bir işaretçisiyse veya *sourcetime* değeri negatifse, bu işlevler [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, işlevler **null** döndürür ve **errno** , **EINVAL**olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**_Gmtime32** Işlevi *sourcetime* DEĞERINI ayırır ve, zaman içinde tanımlanan **TM**türünde bir statik olarak ayrılmış yapıda depolar. Olsun. *Sourcetime* değeri genellikle [Time](time-time32-time64.md) işlevine yapılan çağrıdan alınır.

> [!NOTE]
> Çoğu durumda, hedef ortam gün ışığından yararlanma saatinin etkin olup olmadığını belirlemeyi dener. C çalışma zamanı kitaplığı, gün ışığından yararlanma zamanının (DST) hesaplanmasını uygulamaya yönelik Birleşik Devletler kuralların kullanıldığını varsayar.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgisi|Gerekli C++ üstbilgisi|
|-------------|---------------------|-|
|**gmsaati**, **_gmtime32** **_gmtime64**|\<Time. h>|\<CTime> veya \<saati. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_gmtime.c
// compile with: /W3
// This program uses _gmtime64 to convert a long-
// integer representation of coordinated universal time
// to a structure named newtime, then uses asctime to
// convert this structure to an output string.

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm *newtime;
   __int64 ltime;
   char buff[80];

   _time64( &ltime );

   // Obtain coordinated universal time:
   newtime = _gmtime64( &ltime ); // C4996
   // Note: _gmtime64 is deprecated; consider using _gmtime64_s
   asctime_s( buff, sizeof(buff), newtime );
   printf( "Coordinated universal time is %s\n", buff );
}
```

```Output
Coordinated universal time is Tue Feb 12 23:11:31 2002
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[_mkgmtime, _mkgmtime32, _mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
