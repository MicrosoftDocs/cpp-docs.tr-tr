---
title: gmtime, _gmtime32, _gmtime64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28ce8b8e2367e1d4dd26672206557867c07827e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403966"
---
# <a name="gmtime-gmtime32-gmtime64"></a>gmtime, _gmtime32, _gmtime64

Dönüştüren bir **time_t** saat değeri için bir **tm** yapısı. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md).

## <a name="syntax"></a>Sözdizimi

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Parametreler

*sourceTime*<br/>
Saklı zaman işaretçi. Gece yarısından beri geçen saat saniye olarak zaman gösterilir (00: 00:00), 1 Ocak 1970'den itibaren Eşgüdümlü Evrensel Saat (UTC).

## <a name="return-value"></a>Dönüş Değeri

Türünde bir yapı için bir işaretçi [tm](../../c-runtime-library/standard-types.md). Döndürülen yapısı alanlarının değerlendirilen değeri tutun *sourceTime* bağımsız değişkeni UTC yerine yerel saat. Yapı alanların her biri türünde **int**aşağıdaki gibi:

|Alan|Açıklama|
|-|-|
|**tm_sec**|Saniye dakika sonra (0 - 59).|
|**tm_min**|Dakika sonra saat (0 - 59).|
|**tm_hour**|Gece yarısından saat (0 - 23).|
|**tm_mday**|Ayın günü (1-31).|
|**tm_mon**|Ay (0 - 11; Ocak = 0).|
|**tm_year**|Yıl (1900 eksi geçerli yıl).|
|**tm_wday**|Haftanın günü (0 - 6; Pazar = 0).|
|**tm_yday**|Yılın günü (0 - 365; 1 Ocak = 0).|
|**tm_isdst**|Her zaman 0 için **gmtime**.|

Hem 32 bit ve 64 bit sürümlerini **gmtime**, [mktime](mktime-mktime32-mktime64.md), [mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md), ve [damgasını](localtime-localtime32-localtime64.md) tüm bir ortak kullanmak **tm**  dönüştürme için iş parçacığı başına yapısı. Bu işlevlerin her çağrısına herhangi önceki çağrının sonucu bozar. Varsa *sourceTime* gece, 1 Ocak 1970'ten, önceki bir tarihi temsil eden **gmtime** döndürür **NULL**. Döndürülen hata yoktur.

**_gmtime64**, kullanan **__time64_t** yapısı, ancak yukarı 23:59:59, 31 Aralık 3000 UTC, ifade için tarihleri etkinleştirir **_gmtime32** yalnızca tarihler ile 23:59:59 temsil eder 18 Ocak 2038, UTC. Gece yarısından, 1 Ocak 1970'ten, hem işlevleri için tarih aralığını alt sınırdır.

**gmtime** değerlendiren bir satır içi işlev **_gmtime64**, ve **time_t** eşdeğerdir **__time64_t** sürece **_USE_32BIT_TIME_ T** tanımlanır. Yorumlamaya derleyici zorlarsanız gerekir **time_t** eski 32 bit olarak **time_t**, tanımlayabileceğiniz **_USE_32BIT_TIME_T**, ancak bunu neden yapılması **gmtime** içinde-çizgili için olacak şekilde **_gmtime32** ve **time_t** olarak tanımlanması için **__time32_t**. 64 bit platformlarda izin verilmiyor ve her durumda, uygulamanızın 18 Ocak 2038 sonra başarısız olabilir çünkü bunu değil yapmanızı öneririz.

Bu işlevler kendi parametreleri doğrulayın. Varsa *sourceTime* null işaretçinin veya *sourceTime* değeri negatif, bu işlevler açıklandığı gibi bir geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmek için izin verilip verilmediğini, işlevlerin dönüş **NULL** ve **errno** için **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Gmtime32** işlevi böler *sourceTime* değeri ve statik olarak ayrılan türü yapısında depolar **tm**, zaman içinde tanımlı. H. Değeri *sourceTime* genellikle çağrısından alınan [zaman](time-time32-time64.md) işlevi.

> [!NOTE]
> Çoğu durumda, hedef ortam günışığından etkin olup olmadığını belirlemek çalışır. C çalışma zamanı kitaplığı, gün ışığından yararlanma saati (DST) hesaplama uygulamak için Amerika Birleşik Devletleri kurallarının kullanıldığı varsayılmaktadır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgisi|Gerekli C++ üstbilgisi|
|-------------|---------------------|-|
|**gmtime**, **_gmtime32**, **_gmtime64**|\<time.h >|\<CTime > veya \<time.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
