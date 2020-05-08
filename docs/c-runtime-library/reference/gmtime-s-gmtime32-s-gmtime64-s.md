---
title: gmtime_s, _gmtime32_s, _gmtime64_s
ms.date: 4/2/2020
api_name:
- _gmtime32_s
- gmtime_s
- _gmtime64_s
- _o__gmtime32_s
- _o__gmtime64_s
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
- _gmtime_s
- gmtime64_s
- gmtime32_s
- _gmtime64_s
- gmtime_s
- _gmtime32_s
helpviewer_keywords:
- gmtime_s function
- gmtime32_s function
- time functions
- gmtime64_s function
- _gmtime64_s function
- time structure conversion
- _gmtime_s function
- _gmtime32_s function
ms.assetid: 261c7df0-2b0c-44ba-ba61-cb83efaec60f
ms.openlocfilehash: 152b0569d452fc48af7583b23c6a2449cb24d0d6
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916228"
---
# <a name="gmtime_s-_gmtime32_s-_gmtime64_s"></a>gmtime_s, _gmtime32_s, _gmtime64_s

Bir zaman değerini bir **TM** yapısına dönüştürür. Bunlar, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [_gmtime64 _gmtime32](gmtime-gmtime32-gmtime64.md) sürümleridir.

## <a name="syntax"></a>Sözdizimi

```C
errno_t gmtime_s(
   struct tm* tmDest,
   const __time_t* sourceTime
);
errno_t _gmtime32_s(
   struct tm* tmDest,
   const __time32_t* sourceTime
);
errno_t _gmtime64_s(
   struct tm* tmDest,
   const __time64_t* sourceTime
);
```

### <a name="parameters"></a>Parametreler

*tmDest*<br/>
[TM](../../c-runtime-library/standard-types.md) yapısına yönelik işaretçi. Döndürülen yapının alanları, *Zamanlayıcı* bağımsız değişkeninin değerlendirilen değerini yerel saat yerine UTC olarak tutar.

*sourceTime*<br/>
Saklı saate yönelik işaretçi. Süre gece yarısı (00:00:00), 1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC) itibariyle geçen saniye olarak gösterilir.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Hata varsa dönüş değeri bir hata kodudur. Hata kodları errno. h; içinde tanımlanmıştır Bu hataların listelenmesi için bkz. [errno](../../c-runtime-library/errno-constants.md).

### <a name="error-conditions"></a>Hata koşulları

|*tmDest*|*sourceTime*|Döndürülmesini|*Tmdest* değeri|
|-----------|------------|------------|--------------------|
|**DEĞER**|kaydedilmemiş|**EıNVAL**|Değiştirilmedi.|
|**Null** değil (geçerli belleğe işaret eder)|**DEĞER**|**EıNVAL**|Tüm alanlar-1 olarak ayarlanmıştır.|
|**Null** değil|< 0|**EıNVAL**|Tüm alanlar-1 olarak ayarlanmıştır.|

İlk iki hata koşulu durumunda, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** olarak **EINVAL** ve **EINVAL**döndürür.

## <a name="remarks"></a>Açıklamalar

**_Gmtime32_s** Işlevi *sourcetime* değerini ayırır ve, Time. h içinde tanımlanan **TM**türünde bir yapıda depolar. Yapının adresi, *Tmdest*' de geçirilir. *Sourcetime* değeri genellikle [Time](time-time32-time64.md) işlevine yapılan çağrıdan alınır.

> [!NOTE]
> Hedef ortam, gün ışığından yararlanma saatinin etkin olup olmadığını belirlemeyi denemelidir. C çalışma zamanı kitaplığı, gün ışığından yararlanma saatinin hesaplanmasını uygulamak için Birleşik Devletler kuralları varsayar.

Yapı alanlarının her biri, aşağıdaki tabloda gösterildiği gibi **int**türündedir.

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
|**tm_isdst**|**Gmtime_s**için her zaman 0.|

**__time64_t** yapısını kullanan **_gmtime64_s**, tarihlerin 23:59:59, 31 Aralık 3000, UTC; tarihine kadar ifade etmesine izin verir. **gmtime32_s** yalnızca tarihi 18 Ocak 2038, UTC 23:59:59 ile temsil eder. 1 Ocak 1970 gece yarısı, bu işlevlerin her ikisi için de tarih aralığının alt sınırıdır.

**gmtime_s** , **_gmtime64_s** değerlendirilen ve **time_t** **__time64_t**eşdeğer bir satır içi işlevdir. Derleyicinin **time_t** eski 32 bit **time_t**olarak yorumlamasını zorlamak istiyorsanız **_USE_32BIT_TIME_T**tanımlayabilirsiniz. Bunun yapılması, **gmtime_s** **_gmtime32_s**olarak sıralanmasına neden olur. Uygulamanız 18 Ocak 2038 ' den sonra başarısız olabileceğinden ve 64-bit platformlarda izin verilmediği için bu önerilmez.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgisi|Gerekli C++ üstbilgisi|
|-------------|---------------------|-|
|**gmtime_s**, **_gmtime32_s**, **_gmtime64_s**|\<Time. h>|\<CTime> veya \<saati. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_gmtime64_s.c
// This program uses _gmtime64_s to convert a 64-bit
// integer representation of coordinated universal time
// to a structure named newtime, then uses asctime_s to
// convert this structure to an output string.

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm newtime;
   __int64 ltime;
   char buf[26];
   errno_t err;

   _time64( &ltime );

   // Obtain coordinated universal time:
   err = _gmtime64_s( &newtime, &ltime );
   if (err)
   {
      printf("Invalid Argument to _gmtime64_s.");
   }

   // Convert to an ASCII representation
   err = asctime_s(buf, 26, &newtime);
   if (err)
   {
      printf("Invalid Argument to asctime_s.");
   }

   printf( "Coordinated universal time is %s\n",
           buf );
}
```

```Output
Coordinated universal time is Fri Apr 25 20:12:33 2003
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[_mkgmtime, _mkgmtime32, _mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
