---
title: mktime, _mktime32, _mktime64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d7ead8ea50a617a5b0c67f4528b2138e9cd9e31e
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="mktime-mktime32-mktime64"></a>mktime, _mktime32, _mktime64

Yerel saat Takvim değerine dönüştürür.

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
Zaman yapısına yönelik işaretçinin; bkz: [asctime](asctime-wasctime.md).

## <a name="return-value"></a>Dönüş Değeri

**_mktime32** türünde bir değer kodlanmış belirtilen takvim saati döndürür [time_t](../../c-runtime-library/standard-types.md). Varsa *timeptr* gece, 1 Ocak 1970'ten, önceki bir tarihi başvuruyor veya Takvim zaman gösterilemezse **_mktime32** yazmak için cast -1 döndürür **time_t**. Kullanırken **_mktime32** ve *timeptr* başvurular bir tarih 23:59:59 18 Ocak 2038, Eşgüdümlü Evrensel Saat (UTC), sonra da yazmak için cast -1 döndürecektir **time_t**.

**_mktime64** yazmak için cast -1 döner **__time64_t** varsa *timeptr* 23:59:59 31 Aralık 3000 UTC tarihinden başvuruyor.

## <a name="remarks"></a>Açıklamalar

**Mktime**, **_mktime32** ve **_mktime64** işlevleri Dönüştür gösterdiği sağlanan zaman yapısı (büyük olasılıkla tamamlanmamış) *timeptr*ile tam olarak tanımlanmış bir yapı içinde normalleştirilmiş değerleri ve kendisine dönüştüren bir **time_t** takvim saat değeri. Aynı kodlama tarafından döndürülen değer olarak dönüştürülen süresi olan [zaman](time-time32-time64.md) işlevi. Özgün değerlerini **tm_wday** ve **tm_yday** bileşenlerinin *timeptr* yapısı yok sayılır ve diğer bileşenleri özgün değerlerini sınırlı değildir kendi normal aralıklarına.

**mktime** eşdeğer olan bir satır içi işlev **_mktime64**sürece **_USE_32BIT_TIME_T** tanımlanır ve bu durumda eşdeğer olan **_mktime32** .

UTC, ayarlama sonra **_mktime32** tanıtıcıları 23:59:59 18 Ocak 2038, 1 Ocak 1970 yarısı UTC tarihleri. **_mktime64** tanıtıcıları tarihleri gece yarısına, 1 Ocak 1970'ten ile 23:59:59 31 Aralık 3000. Bu düzeltme -1 döndürmek bu işlevler neden olabilir (için cast **time_t**, **__time32_t** veya **__time64_t**) belirttiğiniz tarih aralığı içinde olsa bile. Kahire, UTC öncesinde iki saat olan Mısır içinde varsa örneğin, iki saat önce belirttiğiniz tarih çıkarılacak *timeptr*; bu artık Tarih aralık dışında bırakabilir.

Bu işlevler doğrulamak ve tm yapısında doldurmak için kullanılabilir. Başarılı, bu işlevlerin değerini ayarlarsanız **tm_wday** ve **tm_yday** olarak uygun ve belirtilen Takvim zaman temsil etmek için diğer bileşenleri ayarlanmış, ancak değerlerinde normal olarak zorla aralıkları. Son değerini **tm_mday** kadar ayarlanmadı **tm_mon** ve **tm_year** belirlenir. Belirtirken bir **tm** yapısı zaman, Ayarla **tm_isdst** alanı:

- Standart Saati geçerli olduğunu belirtmek için bir sıfır (0).

- Yaz Saati geçerli olduğunu göstermek için 0'dan büyük bir değer.

- Bir değer sıfırdan C çalışma zamanı kitaplığı kodu sağlamak için standart saati gün ışığından yararlanma saati etkin olup işlem.

C çalışma zamanı kitaplığı gün ışığından yararlanma tasarrufları zamanı davranışından belirleyecek [TZ](tzset.md) ortam değişkeni. Varsa **TZ** ayarlı değil, Win32 API çağrısı [GetTimeZoneInformation](http://msdn.microsoft.com/library/windows/desktop/ms724421.aspx) gün ışığından yararlanma işletim sisteminden saat bilgisi almak için kullanılır. Bu başarısız olursa, Amerika Birleşik Devletleri kurallar gün ışığından yararlanma saati hesaplama uygulamak için kullanılan kitaplık varsayar. **tm_isdst** gerekli bir alandır. Yoksa değerini ayarlamak, tanımlı değil ve bu işlevlerin dönüş değerini tahmin edilemez. Varsa *timeptr* işaret eden bir **tm** önceki bir çağrı tarafından döndürülen yapısı [asctime](asctime-wasctime.md), [gmtime](gmtime-gmtime32-gmtime64.md), veya [damgasını](localtime-localtime32-localtime64.md) (veya bu işlevler çeşitlemelerini) **tm_isdst** alan doğru değeri içerir.

Unutmayın **gmtime** ve **damgasını** (ve **_gmtime32**, **_gmtime64**, **_localtime32**, ve **_localtime64**) dönüştürme için iş parçacığı başına tek bir arabellek kullanın. Bu arabelleğin sağlarsanız **mktime**, **_mktime32** veya **_mktime64**, önceki içeriği yok.

Bu işlevler kendi parametre doğrulayın. Varsa *timeptr* null işaretçi açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, işlevleri -1 döndürür ve **errno** için **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mktime**|\<time.h >|
|**_mktime32**|\<time.h >|
|**_mktime64**|\<time.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
