---
title: gmtime, _gmtime32, _gmtime64
description: '`gmtime`, `_gmtime32` Ve için `_gmtime64` bir `time_t` değeri yapıya dönüştüren `tm` API başvurusu.'
ms.date: 10/27/2020
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
ms.openlocfilehash: bb8bee6b752f64d85dfb0f8c9e5ba7acf204a76f
ms.sourcegitcommit: 9c801a43ee0d4d84956b03fd387716c818705e0d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2020
ms.locfileid: "92907551"
---
# <a name="gmtime-_gmtime32-_gmtime64"></a>`gmtime`, `_gmtime32`, `_gmtime64`

Bir `time_t` zaman değerini bir yapıya dönüştürür `tm` . Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [ `gmtime_s` , `_gmtime32_s` , `_gmtime64_s` ](gmtime-s-gmtime32-s-gmtime64-s.md).

## <a name="syntax"></a>Sözdizimi

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Parametreler

*`sourceTime`*\
Saklı saate yönelik işaretçi. Süre gece yarısı (00:00:00), 1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC) itibariyle geçen saniye olarak gösterilir.

## <a name="return-value"></a>Dönüş Değeri

Türü yapısına yönelik bir işaretçi [`tm`](../../c-runtime-library/standard-types.md) . Döndürülen yapının alanları, *`sourceTime`* bağımsız değişkenin değerlendirilen değerini yerel saat yerıne UTC olarak tutar. Yapı alanlarının her biri `int` , aşağıdaki gibi türündedir:

|Alan|Açıklama|
|-|-|
|`tm_sec`|Dakika sonra saniye (0-59).|
|`tm_min`|Saat sonra dakika (0-59).|
|`tm_hour`|Gece yarısından itibaren saat (0-23).|
|`tm_mday`|Ayın günü (1-31).|
|`tm_mon`|Ay (0-11; Ocak = 0).|
|`tm_year`|Yıl (geçerli yıl eksi 1900).|
|`tm_wday`|Haftanın günü (0-6; Pazar = 0).|
|`tm_yday`|Yılın günü (0-365; 1 Ocak = 0).|
|`tm_isdst`|**Gmtime** için her zaman 0.|

,, Ve tüm 32-bit ve 64 bit sürümleri **`gmtime`** , [`mktime`](mktime-mktime32-mktime64.md) [`mkgmtime`](mkgmtime-mkgmtime32-mkgmtime64.md) [`localtime`](localtime-localtime32-localtime64.md) `tm` dönüştürme için iş parçacığı başına bir ortak yapı kullanır. Bu işlevlerden birine yapılan her bir çağrı, önceki çağrının sonucunu yok eder. *`sourceTime`* Gece yarısından önce bir tarihi temsil ediyorsa, 1 ocak 1970, **`gmtime`** döndürür `NULL` . Hata döndürme yok.

yapıyı kullanan **_gmtime64** , `__time64_t` tarihleri 23:59:59, 31 Aralık 3000, UTC 'ye kadar ifade etmenizi sağlar. **`_gmtime32`** yalnızca 23:59:59 ile 18, 2038, UTC arasındaki tarihleri temsil eder. 1 Ocak 1970 gece yarısı, her iki işlev için de tarih aralığının alt sınırıdır.

**`gmtime`** , olarak değerlendirilen **`_gmtime64`** ve `time_t` tanımsız olarak eşdeğer bir satır içi işlevdir `__time64_t` `_USE_32BIT_TIME_T` . Derleyicinin eski 32 bit olarak yorumlanmasını zorunlu kılmak istiyorsanız `time_t` `time_t` `_USE_32BIT_TIME_T` , tanımlayabilir, ancak bunu yaparak, **`gmtime`** **`_gmtime32`** `time_t` olarak tanımlanabilmesi ve olarak tanımlanması gerekir `__time32_t` . Bunu, 64 bit platformlarda izin verilmediğinden yapmanızı önermeyiz. Herhangi bir durumda, uygulamanız 18 Ocak 2038 ' den sonra başarısız olabilir.

Bu işlevler, parametrelerini doğrular. *`sourceTime`* Null işaretçisiyse veya *`sourceTime`* değer negatifse, bu işlevler [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklanan şekilde geçersiz bir parametre işleyicisi çağırır. Yürütmenin devam etmesine izin veriliyorsa, işlevleri döndürür ve öğesini `NULL` olarak ayarlar `errno` `EINVAL` .

## <a name="remarks"></a>Açıklamalar

**`_gmtime32`** İşlev *`sourceTime`* değeri ayırır ve içinde tanımlanan statik olarak ayrılmış bir yapıda depolar `tm` `TIME.H` . Değeri, *`sourceTime`* genellikle işleve yapılan çağrıdan alınır [`time`](time-time32-time64.md) .

> [!NOTE]
> Çoğu durumda, hedef ortam gün ışığından yararlanma saatinin etkin olup olmadığını belirlemeyi dener. C çalışma zamanı kitaplığı, gün ışığından yararlanma zamanının (DST) hesaplanmasını uygulamaya yönelik Birleşik Devletler kuralların kullanıldığını varsayar.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgisi|Gerekli C++ üstbilgisi|
|-------------|---------------------|-|
|**`gmtime`** , **`_gmtime32`** , **`_gmtime64`**|`<time.h>`| `<ctime>` veya `<time.h>`|

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

int main(void)
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

[Zaman yönetimi](../../c-runtime-library/time-management.md)\
[`asctime`, `_wasctime`](asctime-wasctime.md)\
[`ctime`, `_ctime32`, `_ctime64`, `_wctime`, `_wctime32`, `_wctime64`](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)\
[`_ftime`, `_ftime32`, `_ftime64`](ftime-ftime32-ftime64.md)\
[`gmtime_s`, `_gmtime32_s`, `_gmtime64_s`](gmtime-s-gmtime32-s-gmtime64-s.md)\
[`localtime`, `_localtime32`, `_localtime64`](localtime-localtime32-localtime64.md)\
[`_mkgmtime`, `_mkgmtime32`, `_mkgmtime64`](mkgmtime-mkgmtime32-mkgmtime64.md)\
[`mktime`, `_mktime32`, `_mktime64`](mktime-mktime32-mktime64.md)\
[`time`, `_time32`, `_time64`](time-time32-time64.md)
