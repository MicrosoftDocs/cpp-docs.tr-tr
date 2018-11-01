---
title: gmtime, _gmtime32, _gmtime64
ms.date: 11/04/2016
apiname:
- _gmtime32
- gmtime
- _gmtime64
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
ms.openlocfilehash: 4f32da5920a0cb892619195207d6501a4b1fd874
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480008"
---
# <a name="gmtime-gmtime32-gmtime64"></a>gmtime, _gmtime32, _gmtime64

Dönüştürür bir **time_t** saat değeri için bir **tm** yapısı. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md).

## <a name="syntax"></a>Sözdizimi

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Parametreler

*sourceTime*<br/>
Depolanan zamana yönelik işaretçi. Zamanı saniye gece yarısından beri geçen olarak gösterilir (00: 00:00), 1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC).

## <a name="return-value"></a>Dönüş Değeri

Bir işaretçi türünden bir yapıyı [tm](../../c-runtime-library/standard-types.md). Geri döndürülen yapı alanları değerlendirilen değerini tutmak *sourceTime* bağımsız değişkeni yerel zaman yerine UTC diliminde saat. Her yapı alanı türüdür **int**gibi:

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
|**tm_isdst**|Her zaman 0 için **gmtime**.|

Hem 32-bit ve 64 bit sürümlerini **gmtime**, [mktime](mktime-mktime32-mktime64.md), [mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md), ve [localtime](localtime-localtime32-localtime64.md) tüm bir ortak kullanmak **tm**  dönüştürme için iş parçacığı başına yapısı. Bu işlevlerden birine yapılan her çağrı, herhangi bir önceki çağrının sonucu yok eder. Varsa *sourceTime* 1 Ocak 1970 gece yarısından önce bir tarihi temsil **gmtime** döndürür **NULL**. Döndürülen hata yok.

**_gmtime64**, kullanan **__time64_t** yapısı, 23:59:59, 31 Aralık, 3000, UTC yukarı ifade edilecek tarihleri etkinleştirirken **_gmtime32** yalnızca 23:59:59 tarihleri temsil eder 18 Ocak 2038, UTC. Gece yarısı, 1 Ocak 1970, iki işlev için de tarih aralığının alt sınırdır.

**gmtime** olarak değerlendirilen bir satır içi işlevdir **_gmtime64**, ve **time_t** eşdeğerdir **__time64_t** sürece **_USE_32BIT_TIME_ T** tanımlanır. Yorumlamak üzere zorlamanız gerekir, **time_t** eski 32-bit olarak **time_t**, tanımlayabileceğiniz **_use_32bıt_tıme_t**, ancak bunu neden yapılması **gmtime** içinde-zorlamanız **_gmtime32** ve **time_t** olarak tanımlanması **__time32_t**. 64-bit platformlarda izin verilmiyor ve 18 Ocak 2038 sonrasında uygulamanız her durumda çalışmayabilir çünkü bunu değil, öneririz.

Bu işlevler kendi parametrelerini doğrular. Varsa *sourceTime* null bir işaretçiyse veya *sourceTime* değeri negatif ise, bu işlevler içinde açıklanan şekilde geçersiz parametre işleyicisini çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md) . Yürütmenin devam etmesine izin verilirse, İşlevler döndürür **NULL** ayarlayıp **errno** için **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Gmtime32** işlevi *sourceTime* değeri ve türü statik olarak ayrılan bir yapıda depolar **tm**zaman içinde tanımlanmış. H Değerini *sourceTime* genellikle çağrısından alınan [zaman](time-time32-time64.md) işlevi.

> [!NOTE]
> Çoğu durumda, hedef ortam günışığından yararlanmanın etkin olup olmadığını saptamaya çalışır. C çalışma zamanı kitaplığı, gün ışığından yararlanma saatine (DST) hesaplanması uygulamak için ABD kurallarının kullanıldığını varsayar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgisi|Gerekli C++ üst bilgisi|
|-------------|---------------------|-|
|**gmtime**, **_gmtime32**, **_gmtime64**|\<TIME.h >|\<CTime > veya \<TIME.h >|

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
