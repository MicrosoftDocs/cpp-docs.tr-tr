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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: e73d2d3cca852b657631361d8271bec7f9c86ac5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344090"
---
# <a name="gmtime_s-_gmtime32_s-_gmtime64_s"></a>gmtime_s, _gmtime32_s, _gmtime64_s

Bir zaman değerini **tm** yapısına dönüştürür. Bunlar, [CRT'deki](gmtime-gmtime32-gmtime64.md) Güvenlik Özellikleri'nde açıklandığı gibi güvenlik geliştirmeleriyle _gmtime64 _gmtime32 [sürümleridir.](../../c-runtime-library/security-features-in-the-crt.md)

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
[TM](../../c-runtime-library/standard-types.md) yapısına işaretçi. Döndürülen yapının alanları, yerel saat yerine UTC'de *zamanlayıcı* bağımsız değişkeninin değerlendirilen değerini tutar.

*kaynakZaman*<br/>
Zaman depolanan işaretçi. Zaman, gece yarısından (00:00:00), 1 Ocak 1970, eşgüdümlü evrensel saat (UTC) itibaren geçen saniyeolarak temsil edilir.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır. İade değeri, bir hata varsa bir hata kodudur. Hata kodları Errno.h tanımlanır; bu hataların bir listesi için, [bkz.](../../c-runtime-library/errno-constants.md)

### <a name="error-conditions"></a>Hata Koşulları

|*tmDest*|*kaynakZaman*|Dönüş|*tmDest* değeri|
|-----------|------------|------------|--------------------|
|**Null**|herhangi bir|**Eınval**|Değiştirilmedi.|
|**NULL** değil (geçerli belleğe işaret)|**Null**|**Eınval**|Tüm alanlar -1 olarak ayarlanır.|
|**NULL** değil|< 0|**Eınval**|Tüm alanlar -1 olarak ayarlanır.|

İlk iki hata koşulu söz konusu olduğunda, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, bu işlevler EINVAL **için errno** ayarlayın ve **EINVAL** döndürün. **EINVAL**

## <a name="remarks"></a>Açıklamalar

**_gmtime32_s** işlevi *kaynakZaman* değerini ayırır ve Time.h'de tanımlanan **tm**türünde bir yapıda saklar. Yapının adresi *tmDest'te*geçer. *SourceTime* değeri genellikle bir aramadan [zaman](time-time32-time64.md) işlevine elde edilir.

> [!NOTE]
> Hedef ortam, gün ışığından yararlanma zamanının geçerli olup olmadığını belirlemeye çalışmalıdır. C çalışma zamanı kitaplığı, gün ışığından yararlanma saatinin hesaplanmasını uygulamak için ABD kurallarını varsayar.

Yapı alanlarının her biri, aşağıdaki tabloda gösterildiği gibi, tür **int'dir.**

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
|**tm_isdst**|her zaman 0 **gmtime_s**için .|

**_gmtime64_s,** **__time64_t** yapısını kullanan, tarihlerin 23:59:59, 31 Aralık 3000, UTC; **gmtime32_s** ise sadece 23:59:59 18 Ocak 2038, UTC tarihleri temsil ediyor. Midnight, 1 Ocak 1970, her iki işlev için de tarih aralığının alt sınırıdır.

**gmtime_s** **_gmtime64_s** değerlendiren bir satır dışı fonksiyondur ve **time_t** **__time64_t**eşdeğerdir. Derleyiciyi **time_t** eski 32 bit **time_t**olarak yorumlamaya zorlamanız gerekiyorsa, **_USE_32BIT_TIME_T**tanımlayabilirsiniz. Bunu yapmak **gmtime_s** **_gmtime32_s**için sıralı olmasını sağlayacaktır. Başvurunuz 18 Ocak 2038'den sonra başarısız olabileceğinden ve 64 bit platformlarda izin verilmediği için bu önerilmez.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgi|Gerekli C++ üstbilgi|
|-------------|---------------------|-|
|**gmtime_s**, **_gmtime32_s**, **_gmtime64_s**|\<time.h>|\<ctime> \<veya time.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
