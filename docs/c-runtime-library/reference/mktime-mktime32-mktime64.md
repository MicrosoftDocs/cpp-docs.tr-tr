---
description: 'Hakkında daha fazla bilgi edinin: mktime, _mktime32, _mktime64'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: aebb12324de5a18dfac6ab84b3b7b2c3da15a2ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97256425"
---
# <a name="mktime-_mktime32-_mktime64"></a>mktime, _mktime32, _mktime64

Yerel saati bir takvim değerine dönüştürür.

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
Zaman yapısına işaretçi; bkz. [asctime](asctime-wasctime.md).

## <a name="return-value"></a>Dönüş Değeri

**_mktime32** , [time_t](../../c-runtime-library/standard-types.md)türünde bir değer olarak kodlanmış belirtilen takvim saatini döndürür. *Timeptr* gece yarısından önce bir tarihe, 1 Ocak 1970 ' e veya takvim saatinin temsil edilemeyeceği takdirde, **_mktime32** **time_t** türüne-1 tür dönüştürme döndürür. **_Mktime32** kullanırken ve *timeptr* , 23:59:59 Ocak 2038, Eşgüdümlü Evrensel Saat (UTC) sonrasında bir tarihe başvuruyorsa, **time_t** türüne-1 tür dönüştürme döndürür.

**_mktime64** , *timeptr* 23:59:59, 31 Aralık 3000 ' den sonra bir tarihe başvuruyorsa, **__time64_t** tür olarak 1 ' e cast.

## <a name="remarks"></a>Açıklamalar

**Mktime**, **_mktime32** ve **_mktime64** işlevleri, *timeptr* tarafından işaret edilen zaman yapısını (muhtemelen tamamlanmamış), normalleştirilmiş değerlerle tam olarak tanımlanmış bir yapıya dönüştürür ve sonra bunu bir **time_t** takvim süresi değerine dönüştürür. Dönüştürülen süre, [Time](time-time32-time64.md) işlevi tarafından döndürülen değerlerle aynı kodlamaya sahiptir. *Timeptr* yapısının **tm_wday** ve **tm_yday** bileşenlerinin özgün değerleri yok sayılır ve diğer bileşenlerin özgün değerleri normal aralıklarıyla sınırlandırılır.

**mktime** , **_USE_32BIT_TIME_T** tanımlanmadığı müddetçe **_mktime64** eşdeğer bir satır içi işlevdir, bu durumda **_mktime32** eşdeğerdir.

UTC ayarından sonra, **_mktime32** gece yarısından Itibaren 1 ocak 1970 23:59:59, 18 Ocak 2038, UTC tarihine kadar olan tarihleri işler. **_mktime64** tarihleri gece yarısı, 1 Ocak 1970, 31 aralık 3000 23:59:59 için işler. Bu ayarlama, belirttiğiniz tarih aralık dahilinde olmasına rağmen bu işlevlerin-1 ( **time_t**, **__time32_t** veya **__time64_t**) döndürmesini sağlayabilir. Örneğin, bu, UTC 'den iki saat önce olan, Cairo kullanıyorsanız, ilk olarak *timeptr*'de belirttiğiniz tarihten iki saat çıkarılır; Bu, artık tarihi Aralık dışında yerleştirebilir.

Bu işlevler, bir tm yapısını doğrulamak ve doldurmanız için kullanılabilir. Başarılı olursa, bu işlevler **tm_wday** ve **tm_yday** değerlerini ayarlar ve diğer bileşenleri belirtilen takvim zamanını temsil edecek şekilde ayarlar, ancak değerleri normal aralıklar için zorlanır. **Tm_mday** son değeri **tm_mon** ve **tm_year** belirlenene kadar ayarlı değildir. Bir **TM** yapı süresi belirtirken, **tm_isdst** alanını şu şekilde ayarlayın:

- Standart saatin geçerli olduğunu belirtmek için sıfır (0).

- Gün ışığından yararlanma saatinin etkin olduğunu göstermek için 0 ' dan büyük bir değer.

- Standart saat veya yaz saati kaydetme saatinin etkin olup olmadığını C çalışma zamanı kitaplığı kodunun işlem için sıfırdan küçük bir değer.

C çalışma zamanı kitaplığı, [TZ](tzset.md) ortam değişkeninden gündüz tasarrufu süresi davranışını belirleyecek. **TZ** ayarlanmamışsa, işletim sisteminden gün ışığından yararlanma saati bilgilerini almak Için [gettimezoneınformation](/windows/win32/api/timezoneapi/nf-timezoneapi-gettimezoneinformation) Win32 API çağrısı kullanılır. Bu başarısız olursa, kitaplık gün ışığından yararlanma saatinin hesaplanmasını uygulamak için Birleşik Devletler ' kurallarının kullanıldığını varsayar. **tm_isdst** gerekli bir alandır. Ayarlanmamışsa, değeri tanımsızdır ve bu işlevlerden dönüş değeri tahmin edilemez. *Timeptr* , önceki bir [asctime](asctime-wasctime.md), [gmtime](gmtime-gmtime32-gmtime64.md)veya [localtime](localtime-localtime32-localtime64.md) (veya bu işlevlerin çeşitleri) çağrısı tarafından döndürülen bir **TM** yapısına işaret ediyorsa, **tm_isdst** alanı doğru değeri içerir.

**Gmtime** ve **localtime** (ve **_gmtime32**, **_gmtime64**, **_localtime32** ve **_localtime64**) dönüştürme için her iş parçacığı için tek bir arabellek kullanılacağını unutmayın. Bu arabelleği **mktime**, **_mktime32** veya **_mktime64** olarak sağlarsanız, önceki içerikler yok edilir.

Bu işlevler, parametresini doğrular. *Timeptr* null Işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlevler-1 döndürür ve **errno** , **EINVAL** olarak ayarlanır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mktime**|\<time.h>|
|**_mktime32**|\<time.h>|
|**_mktime64**|\<time.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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
