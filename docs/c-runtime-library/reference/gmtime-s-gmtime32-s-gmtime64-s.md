---
title: gmtime_s, _gmtime32_s, _gmtime64_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b15896ff9ec96ed8dd9867c14d252edaad2c67a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405282"
---
# <a name="gmtimes-gmtime32s-gmtime64s"></a>gmtime_s, _gmtime32_s, _gmtime64_s

Bir süre değerine dönüştürür bir **tm** yapısı. Sürümleri bunlar [_gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
İşaretçi bir [tm](../../c-runtime-library/standard-types.md) yapısı. Döndürülen yapısı alanlarının değerlendirilen değeri tutun *Zamanlayıcı* bağımsız değişkeni UTC yerine yerel saat.

*sourceTime*<br/>
Saklı zaman işaretçi. Gece yarısından beri geçen saat saniye olarak zaman gösterilir (00: 00:00), 1 Ocak 1970'den itibaren Eşgüdümlü Evrensel Saat (UTC).

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Bir hata olduğunda dönüş değeri bir hata kodudur. Hata kodları Errno.h içinde tanımlanan; Bu hataların listesi için bkz: [errno](../../c-runtime-library/errno-constants.md).

### <a name="error-conditions"></a>Hata koşulları

|*tmDest*|*sourceTime*|Döndür|Değer *tmDest*|
|-----------|------------|------------|--------------------|
|**NULL**|tüm|**EINVAL**|Değiştirilmedi.|
|Değil **NULL** (noktaları için geçerli bellek)|**NULL**|**EINVAL**|Tüm alanları -1 olarak ayarlayın.|
|değil **NULL**|< 0|**EINVAL**|Tüm alanları -1 olarak ayarlayın.|

İlk iki hata koşulları söz konusu olduğunda geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve geri dönüp **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Gmtime32_s** işlevi böler *sourceTime* değer ve türü yapısında depolar **tm**, Time.h içinde tanımlı. Adres yapısı geçirilen *tmDest*. Değeri *sourceTime* genellikle çağrısından alınan [zaman](time-time32-time64.md) işlevi.

> [!NOTE]
> Hedef ortam günışığından etkin olup olmadığını belirlemek denemelisiniz. C çalışma zamanı kitaplığı gün ışığından yararlanma saati hesaplama uygulamak için Amerika Birleşik Devletleri kuralları varsayar.

Yapı alanların her biri türünde **int**aşağıdaki tabloda gösterildiği gibi.

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
|**tm_isdst**|Her zaman 0 için **gmtime_s**.|

**_gmtime64_s**, kullanan **__time64_t** yapısı, 23:59:59, 31 Aralık 3000 UTC; yukarı ifade tarihleri sağlarken **gmtime32_s** yalnızca tarihler aracılığıyla temsil eder 23:59:59 18 Ocak 2038, UTC. Gece yarısından, 1 Ocak 1970'ten, hem bu işlevler için tarih aralığını alt sınırdır.

**gmtime_s** değerlendiren bir satır içi işlev **_gmtime64_s** ve **time_t** eşdeğerdir **__time64_t**. Yorumlamaya derleyici zorlamak gerekiyorsa **time_t** eski 32 bit olarak **time_t**, tanımlayabileceğiniz **_USE_32BIT_TIME_T**. Bunun neden olacak **gmtime_s** içinde-çizgili için olacak şekilde **_gmtime32_s**. Bu, uygulamanızın 18 Ocak 2038 sonra başarısız olabilir ve 64 bit platformlarda izin verilmiyor çünkü önerilmez.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgisi|Gerekli C++ üstbilgisi|
|-------------|---------------------|-|
|**gmtime_s**|, **_gmtime32_s**, **_gmtime64_s**|\<time.h >|\<CTime > veya \<time.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
