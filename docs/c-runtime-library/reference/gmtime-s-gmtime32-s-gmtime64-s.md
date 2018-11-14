---
title: gmtime_s, _gmtime32_s, _gmtime64_s
ms.date: 11/04/2016
apiname:
- _gmtime32_s
- gmtime_s
- _gmtime64_s
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
ms.openlocfilehash: 8225fed21ca9dc67440a4af5dcf43b2ad5cfdffb
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51332471"
---
# <a name="gmtimes-gmtime32s-gmtime64s"></a>gmtime_s, _gmtime32_s, _gmtime64_s

Bir saat değerine dönüştürür bir **tm** yapısı. Bunlar sürümleridir [_gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
İşaretçi bir [tm](../../c-runtime-library/standard-types.md) yapısı. Geri döndürülen yapı alanları değerlendirilen değerini tutmak *Zamanlayıcı* bağımsız değişkeni yerel zaman yerine UTC diliminde saat.

*sourceTime*<br/>
Depolanan zamana yönelik işaretçi. Zamanı saniye gece yarısından beri geçen olarak gösterilir (00: 00:00), 1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC).

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Bir hata varsa dönüş değeri bir hata kodudur. Hata kodları Errno.h içinde tanımlanır; Bu hataların bir listesi için bkz: [errno](../../c-runtime-library/errno-constants.md).

### <a name="error-conditions"></a>Hata koşulları

|*tmDest*|*sourceTime*|döndürülecek|Değerini *tmDest*|
|-----------|------------|------------|--------------------|
|**NULL**|Tüm|**EINVAL**|Değiştirilmedi.|
|Değil **NULL** (geçerli bellek noktaları)|**NULL**|**EINVAL**|Tüm alanları -1 olarak ayarlayın.|
|Değil **NULL**|< 0|**EINVAL**|Tüm alanları -1 olarak ayarlayın.|

İlk iki hata koşulları söz konusu olduğunda, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve dönüş **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Gmtime32_s** işlevi *sourceTime* değeri ve türündeki yapıda depolar **tm**TIME.h içinde tanımlanmış. Yapının adresi geçirilen *tmDest*. Değerini *sourceTime* genellikle çağrısından alınan [zaman](time-time32-time64.md) işlevi.

> [!NOTE]
> Hedef ortam günışığından yararlanmanın etkin olup olmadığını belirlemek denemelisiniz. C çalışma zamanı kitaplığı Yaz Saati hesaplama uygulamak için ABD kurallarını varsayar.

Her yapı alanı türüdür **int**aşağıdaki tabloda gösterildiği gibi.

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
|**tm_isdst**|Her zaman 0 için **gmtime_s**.|

**_gmtime64_s**, kullanan **__time64_t** yapısı, 23:59:59, 31 Aralık, 3000, UTC; yukarı ifade edilecek tarihleri sağlarken **gmtime32_s** yalnızca tarihleri temsil eder 23:59:59 18 Ocak 2038, UTC. Gece yarısı, 1 Ocak 1970, bu her iki işlev için tarih aralığının alt sınırdır.

**gmtime_s** olarak değerlendirilen bir satır içi işlev **_gmtime64_s** ve **time_t** eşdeğerdir **__time64_t**. Yorumlamak üzere zorlamanız gerekirse **time_t** eski 32-bit olarak **time_t**, tanımlayabileceğiniz **_use_32bıt_tıme_t**. Bunun yapılması neden olacak **gmtime_s** içinde-zorlamanız **_gmtime32_s**. Bu, 18 Ocak 2038 sonrasında uygulamanız çalışmayabilir ve 64-bit platformlarda izin verilmiyor çünkü önerilmez.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgisi|Gerekli C++ üst bilgisi|
|-------------|---------------------|-|
|**gmtime_s**, **_gmtime32_s**, **_gmtime64_s**|\<TIME.h >|\<CTime > veya \<TIME.h >|

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
