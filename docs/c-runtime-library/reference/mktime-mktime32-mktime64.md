---
title: mktime, _mktime32, _mktime64
ms.date: 11/04/2016
apiname:
- _mktime32
- mktime
- _mktime64
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
ms.openlocfilehash: 8e9524249d6c90323bdcfc0b92ecf2dad281c79b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156492"
---
# <a name="mktime-mktime32-mktime64"></a>mktime, _mktime32, _mktime64

Yerel Takvim değerine dönüştürün.

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
Zaman yapısı işaretçisi; bkz: [asctime](asctime-wasctime.md).

## <a name="return-value"></a>Dönüş Değeri

**_mktime32** türünde bir değer kodlanan ve belirtilen takvim zamanı döndüren [time_t](../../c-runtime-library/standard-types.md). Varsa *timeptr* başvuran 1 Ocak 1970 gece yarısından önce bir tarih veya takvim üzerinde zaman temsil edilemiyorsa, **_mktime32** türüne yapılan -1 döndürür **time_t**. Kullanırken **_mktime32** ve *timeptr* tarihten sonra 23:59:59 18 Ocak 2038 Eşgüdümlü Evrensel Saat (UTC), bir başvuru türüne yapılan -1 döndürecektir **time_t**.

**_mktime64** türüne yapılan -1 döndürür **__time64_t** varsa *timeptr* 23:59:59, 31 Aralık, 3000, UTC tarihinden başvuruyor.

## <a name="remarks"></a>Açıklamalar

**Mktime**, **_mktime32** ve **_mktime64** işlevler tarafından sağlanan zaman yapısı (muhtemelen eksik) dönüştürme *timeptr*ile tam olarak tanımlanmış bir yapı içinde normalleştirilmiş değerleri ve ona dönüştürür bir **time_t** takvim saat değeri. Dönüştürülen zaman tarafından döndürülen değerlerin aynı kodlama sahip [zaman](time-time32-time64.md) işlevi. Öğesinin özgün değerleri **tm_wday** ve **tm_yday** bileşenlerinin *timeptr* yapısı yok sayılır ve diğer bileşenleri öğesinin özgün değerleri sınırlı değildir. kendi normal aralıklarına.

**mktime** değerine eşdeğer olan bir satır içi işlevdir **_mktime64**sürece **_use_32bıt_tıme_t** tanımlanır ve bu durumda değerine eşdeğer olan **_mktime32** .

Sonra UTC ayarlama **_mktime32** tanıtıcıları tarihler 1 Ocak 1970 gece 23:59:59 18 Ocak 2038, UTC. **_mktime64** tanıtıcıları tarihleri gece yarısı, 1 Ocak 1970 ile 23:59:59, 31 Aralık, 3000. Bu ayarı, bu işlevler -1 döndürür neden olabilir (başvurusuna **time_t**, **__time32_t** veya **__time64_t**), belirttiğiniz tarih aralığı içinde olsa bile. Kahire, utc'nin iki saat olan Mısır içinde Eğer Örneğin, iki saat önce belirttiğiniz tarihten itibaren çıkarılır *timeptr*; bu artık tarihinizden aralık dışında bırakabilir.

Bu işlevler, doğrulamak ve tm yapısında doldurmak için kullanılabilir. Başarılı, bu işlevlerin değerlerini ayarlayın. **tm_wday** ve **tm_yday** uygun şekilde ve belirtilen takvim üzerinde zaman temsil etmek için diğer bileşenleri ayarlandı, ancak değerleriyle normal zorla aralıkları. Son değeri **tm_mday** kadar ayarlanmadı **tm_mon** ve **tm_year** belirlenir. Belirtirken bir **tm** ayarlayın, yapı zaman **tm_isdst** alanı:

- Sıfır Standart Saati etkin olduğunu belirtmek için (0).

- Gün ışığından yararlanma saatine göre geçerli olduğunu göstermek için 0'dan büyük bir değer.

- Bir değeri sıfırdan küçük C çalışma zamanı kitaplık kodu için standart saat veya gün ışığından yararlanma etkin olup olmadığını işlem.

C çalışma zamanı kitaplığı gün ışığından tasarruf zamanı davranışından belirleyecek [TZ](tzset.md) ortam değişkeni. Varsa **TZ** ayarlanmadı, Win32 API çağrısı [GetTimeZoneInformation](/windows/desktop/api/timezoneapi/nf-timezoneapi-gettimezoneinformation) günışığından işletim sisteminden saat bilgilerini almak için kullanılır. Bu başarısız olursa, Amerika Birleşik Devletleri kuralları Yaz Saati hesaplama uygulamak için kullanılan kitaplık varsayar. **tm_isdst** gerekli bir alandır. Yoksa değerine ayarlanırsa, tanımsız olur ve bu işlevlerin dönüş değeri tahmin edilemez. Varsa *timeptr* işaret eden bir **tm** önceki bir çağrı tarafından döndürülen yapısı [asctime](asctime-wasctime.md), [gmtime](gmtime-gmtime32-gmtime64.md), veya [localtime](localtime-localtime32-localtime64.md) (veya türevleri bu işlevlerin) **tm_isdst** alan geçerli bir değer içerir.

Unutmayın **gmtime** ve **localtime** (ve **_gmtime32**, **_gmtime64**, **_localtime32**, ve **_localtime64**) dönüştürme için iş parçacığı başına tek bir arabellek kullanın. Bu arabelleğin sağlarsanız **mktime**, **_mktime32** veya **_mktime64**, önceki içeriği yok edilir.

Bu işlevler, parametresini doğrular. Varsa *timeptr* null bir işaretçiyse, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, İşlevler -1 döndürür ve **errno** için **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mktime**|\<TIME.h >|
|**_mktime32**|\<TIME.h >|
|**_mktime64**|\<TIME.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

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
