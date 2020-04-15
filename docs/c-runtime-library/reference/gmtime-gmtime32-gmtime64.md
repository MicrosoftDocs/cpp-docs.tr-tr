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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: afa46e583437ebace8edd3a54a6d85e61e02854c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344097"
---
# <a name="gmtime-_gmtime32-_gmtime64"></a>gmtime, _gmtime32, _gmtime64

**time_t** bir zaman değerini **tm** yapısına dönüştürür. Bu işlevlerin daha güvenli sürümleri mevcuttur; [gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Parametreler

*kaynakZaman*<br/>
Depolanan zamana işaretçi. Zaman, gece yarısından (00:00:00), 1 Ocak 1970, eşgüdümlü evrensel saat (UTC) itibaren geçen saniyeolarak temsil edilir.

## <a name="return-value"></a>Dönüş Değeri

[Tm](../../c-runtime-library/standard-types.md)türüyapısına işaretçi. Döndürülen yapının alanları, yerel saat yerine *KAYNAK Zaman* bağımsız değişkeninin değerlendirilen değerini UTC'de tutar. Yapı alanlarının her biri aşağıdaki gibi tür **int'** dir:

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
|**tm_isdst**|Gmtime **gmtime**için her zaman 0 .|

**Gmtime,** [mktime,](mktime-mktime32-mktime64.md) [mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md)ve [localtime'ın](localtime-localtime32-localtime64.md) 32 bit ve 64 bit sürümlerinde dönüşüm için iş parçacığı başına tek bir ortak **tm** yapısı kullanılır. Bu işlevlerden birine yapılan her çağrı, önceki herhangi bir aramanın sonucunu yok eder. *SourceTime* gece yarısından önceki bir tarihi temsil ediyorsa, 1 Ocak 1970, **gmtime** **NULL**döndürür. Hata iadesi yok.

**__time64_t** yapısını kullanan **_gmtime64**tarihlerin 23:59:59, 31 Aralık 3000, UTC'ye kadar ifade edilmesini sağlarken, **_gmtime32** tarihleri yalnızca 23:59:59 18 Ocak 2038, UTC'ye kadar temsil eder. Midnight, 1 Ocak 1970, her iki işlev için tarih aralığının alt sınırıdır.

**gmtime,** **_gmtime64**değerlendiren bir satır dışı fonksiyondur ve **_USE_32BIT_TIME_T** tanımlanmadıkça **time_t** **__time64_t** eşdeğerdir. Derleyiciyi **time_t** eski 32 bit **time_t**olarak yorumlamaya zorlamanız gerekiyorsa, **_USE_32BIT_TIME_T**tanımlayabilirsiniz, ancak bunu yapmak **gmtime'ın** **_gmtime32** ve **time_t** **__time32_t**olarak tanımlanmasına neden olur. 64 bit platformlarda izin verilmediği ve her halükarda başvurunuzun 18 Ocak 2038'den sonra başarısız olabileceği nden bunu yapmamanızı öneririz.

Bu işlevler parametrelerini doğrular. *SourceTime* null işaretçisi ise veya *kaynakZaman* değeri negatifse, bu işlevler [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre işleyicisi çağırır. Yürütmedevam etmesine izin verilirse, işlevler **NULL** döndürdü ve **EINVAL** **için errno** ayarlayın.

## <a name="remarks"></a>Açıklamalar

**_gmtime32** işlevi *kaynakZaman* değerini ayırır ve TIME'da tanımlanan **tm**türünde statik olarak ayrılmış bir yapıda saklar. H. *SourceTime* değeri genellikle bir aramadan [zaman](time-time32-time64.md) işlevine elde edilir.

> [!NOTE]
> Çoğu durumda, hedef ortam gün ışığından yararlanma zamanının geçerli olup olmadığını belirlemeye çalışır. C çalışma zamanı kitaplığı, Gün Işığından Yararlanma Saati (DST) hesaplamasını uygulamak için ABD kurallarının kullanıldığını varsayar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgi|Gerekli C++ üstbilgi|
|-------------|---------------------|-|
|**gmtime**, **_gmtime32**, **_gmtime64**|\<time.h>|\<ctime> \<veya time.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
