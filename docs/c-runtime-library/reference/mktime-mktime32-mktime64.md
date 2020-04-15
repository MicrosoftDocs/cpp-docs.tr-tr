---
title: mktime, _mktime32, _mktime64
ms.date: 4/2/2020
api_name:
- _mktime32
- mktime
- _mktime64
- _o__mktime32
- _o__mktime64
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
- mktime
- _mktime64
helpviewer_keywords:
- _mktime32 function
- mktime function
- time functions
- mktime64 function
- converting times
- mktime32 function
- _mktime64 function
- time, converting
ms.assetid: 284ed5d4-7064-48a2-bd50-15effdae32cf
ms.openlocfilehash: b0981f33d70945083eacd28eb7517e80b3f2539f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338711"
---
# <a name="mktime-_mktime32-_mktime64"></a>mktime, _mktime32, _mktime64

Yerel saati takvim değerine dönüştürün.

## <a name="syntax"></a>Sözdizimi

```C
time_t mktime(
   struct tm *timeptr
);
__time32_t _mktime32(
   struct tm *timeptr
);
__time64_t _mktime64(
   struct tm *timeptr
);
```

### <a name="parameters"></a>Parametreler

*timeptr*<br/>
Zaman yapısına işaretçi; [bkz. asctime](asctime-wasctime.md).

## <a name="return-value"></a>Dönüş Değeri

**_mktime32,** [time_t](../../c-runtime-library/standard-types.md)türü değeri olarak kodlanmış belirtilen takvim saatini döndürür. *Timeptr* gece yarısından önceki bir tarihe başvuruyorsa, 1 Ocak 1970'te veya takvim saati temsil edilemiyorsa, **_mktime32** **-1**döküm time_t yazına döndürür. **_mktime32** kullanırken ve *timeptr* referansları 23:59:59 18 Ocak 2038, Eşgüdümlü Evrensel Zaman (UTC) sonra bir tarih, bu **time_t**türüne -1 döküm döndürür.

**_mktime64** 23:59:59, 31 Aralık 3000, UTC sonra *timeptr* referansları bir tarih **__time64_t** türüne -1 döküm döndürür.

## <a name="remarks"></a>Açıklamalar

**mktime,** **_mktime32** ve **_mktime64** işlevleri, *timeptr* tarafından işaret edilen sağlanan zaman yapısını (muhtemelen eksik) normalleştirilmiş değerlere sahip tam tanımlı bir yapıya dönüştürür ve daha sonra **time_t** takvim saati değerine dönüştürür. Dönüştürülen süre, [zaman](time-time32-time64.md) işlevi tarafından döndürülen değerlerle aynı kodlamaya sahiptir. *Timeptr* yapısının **tm_wday** ve **tm_yday** bileşenlerinin özgün değerleri yoksayılır ve diğer bileşenlerin özgün değerleri normal aralıklarıyla sınırlı değildir.

**mktime,** **_USE_32BIT_TIME_T** tanımlanmadıkça **_mktime64**eşdeğer olan, bu durumda **_mktime32**eşdeğer olan bir satır dışı fonksiyondur.

UTC'de yapılan bir ayarlamadan sonra **_mktime32,** 1 Ocak 1970, 23:59:59 Ocak 18, 2038, UTC tarihleri ne kadar dır. **_mktime64,** 1 Ocak 1970 ile 31 Aralık 3000 tarihleri 23:59:59'a kadar dır. Bu ayarlama, belirttiğiniz tarih aralık içinde olsa bile bu işlevlerin -1 (döküm **time_t,** **__time32_t** veya **__time64_t)** dönmesine neden olabilir. Örneğin, UTC'den iki saat önce Kahire, Mısır'daysanız, ilk olarak *timeptr'de*belirttiğiniz tarihten iki saat çıkarılır; bu artık tarihinizi kapsama alanının dışına çıkartabilir.

Bu işlevler bir tm yapısını doğrulamak ve doldurmak için kullanılabilir. Başarılı olursa, bu işlevler **tm_wday** ve **tm_yday** değerlerini uygun olarak ayarlar ve diğer bileşenleri belirtilen takvim saatini temsil edecek şekilde ayarlar, ancak değerleri normal aralıklara zorlanmış olarak ayarlar. **tm_mday** son değeri **tm_mon** ve **tm_year** belirlenene kadar belirlenmez. **TM** yapı süresi belirtilirken, **tm_isdst** alanını aşağıdakilere ayarlayın:

- Standart saatin geçerli olduğunu belirtmek için sıfır (0).

- Gün ışığından yararlanma saatinin geçerli olduğunu belirtmek için 0'dan büyük bir değer.

- Standart saat veya gün ışığından yararlanma saati etkin olup olmadığını C çalışma zamanı kitaplık kodu hesaplaması için sıfırdan daha az bir değer.

C çalışma zamanı kitaplığı, [TZ](tzset.md) ortam değişkeninden gün ışığından yararlanma saati davranışını belirler. **TZ** ayarlanmazsa, Win32 API [aramagetTimeZoneInformation](/windows/win32/api/timezoneapi/nf-timezoneapi-gettimezoneinformation) işletim sisteminden gün ışığından yararlanma saati bilgilerini almak için kullanılır. Bu başarısız olursa, kitaplık, gün ışığından yararlanma saati hesaplamasını uygulamak için ABD'nin kurallarının kullanıldığını varsayar. **tm_isdst** gerekli bir alandır. Ayarlanmamışsa, değeri tanımsızdır ve bu işlevlerden gelen geri dönüş değeri tahmin edilemez. *Timeptr,* önceki bir çağrıyla döndürülen bir **tm** yapısına işaret [localtime](localtime-localtime32-localtime64.md) [ederse,](asctime-wasctime.md) [tm_isdst](gmtime-gmtime32-gmtime64.md) **alanı** doğru değeri içerir.

**GMTIME** ve **localtime** (ve **_gmtime32**, **_gmtime64**, **_localtime32**ve **_localtime64**) dönüşüm için iş parçacığı başına tek bir arabellek kullanın. Bu arabelleği **mktime**, **_mktime32** veya **_mktime64**olarak sağlarsanız, önceki içerik yok edilir.

Bu işlevler parametrelerini doğrular. *Timeptr* null işaretçisi ise, Geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, işlevleri -1 döndürün ve **EINVAL** **için errno** ayarlayın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mktime**|\<time.h>|
|**_mktime32**|\<time.h>|
|**_mktime64**|\<time.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

```C
// crt_mktime.c
/* The example takes a number of days
* as input and returns the time, the current
* date, and the specified number of days.
*/

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm  when;
   __time64_t now, result;
   int        days;
   char       buff[80];

   time( &now );
   _localtime64_s( &when, &now );
   asctime_s( buff, sizeof(buff), &when );
   printf( "Current time is %s\n", buff );
   days = 20;
   when.tm_mday = when.tm_mday + days;
   if( (result = mktime( &when )) != (time_t)-1 ) {
      asctime_s( buff, sizeof(buff), &when );
      printf( "In %d days the time will be %s\n", days, buff );
   } else
      perror( "mktime failed" );
}
```

### <a name="sample-output"></a>Örnek Çıktı

```Output
Current time is Fri Apr 25 13:34:07 2003

In 20 days the time will be Thu May 15 13:34:07 2003
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[_mkgmtime, _mkgmtime32, _mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
