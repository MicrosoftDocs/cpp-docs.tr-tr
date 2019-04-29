---
title: asctime, _wasctime
ms.date: 11/04/2016
apiname:
- _wasctime
- asctime
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
- _tasctime
- asctime
- _wasctime
helpviewer_keywords:
- asctime function
- tasctime function
- wasctime function
- _tasctime function
- _wasctime function
- time structure conversion
- time, converting
ms.assetid: 974f1727-10ff-4ed4-8cac-2eb2d681f576
ms.openlocfilehash: bc2d7a50442d9000eaaebf7a06bf336b3317e4df
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341814"
---
# <a name="asctime-wasctime"></a>asctime, _wasctime

Dönüştürme bir **tm** zaman yapısı için bir karakter dizesi. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [asctime_s, _wasctime_s](asctime-s-wasctime-s.md).

## <a name="syntax"></a>Sözdizimi

```C
char *asctime(
   const struct tm *timeptr
);
wchar_t *_wasctime(
   const struct tm *timeptr
);
```

### <a name="parameters"></a>Parametreler

*timeptr*<br/>
Saat/tarih yapısı.

## <a name="return-value"></a>Dönüş Değeri

**asctime** karakter dize sonucu; bir işaretçi döndürür **_wasctime** geniş karakterli dize sonucu için bir işaretçi döndürür. Hata dönüş değeri yoktur.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [asctime_s, _wasctime_s](asctime-s-wasctime-s.md).

**Asctime** işlevi dönüştürür bir yapıya bir karakter dizesi olarak depolanan bir süre. *Timeptr* değeri çağrısından alınan genellikle **gmtime** veya **localtime**, her ikisi de bir işaretçi döndürür bir **tm** yapısı ZAMAN içinde tanımlanır. H

|timeptr üyesi|Değer|
|--------------------|-----------|
|**tm_hour**|Saatleri gece yarısından (0-23)|
|**tm_isdst**|Gün ışığından yararlanma etkinse pozitif; gün ışığından yararlanma etkin değilse, 0; Yaz Saati durum bilinmiyorsa, negatif. C çalışma zamanı kitaplığı, gün ışığından yararlanma saatine (DST) hesaplanması uygulamak için ABD kurallarını varsayar.|
|**tm_mday**|Ayın günü (1-31)|
|**tm_min**|Saat (0-59) dakika|
|**tm_mon**|Ay (0-11; Ocak = 0)|
|**tm_sec**|(0-59) dakikadan sonra saniye|
|**tm_wday**|Haftanın günü (0-6; Pazar = 0)|
|**tm_yday**|(0-365; yılın günü 1 Ocak = 0)|
|**tm_year**|Yıl (mevcut yıl eksi 1900)|

Dönüştürülmüş karakteri dize ayrıca yerel saat dilimi ayarlarını göre ayarlanır. Yerel saat yapılandırma hakkında daha fazla bilgi için bkz: [zaman](time-time32-time64.md), [_ftime](ftime-ftime32-ftime64.md), ve [localtime](localtime-localtime32-localtime64.md) işlevleri ve [_tzset](tzset.md) işlevi Genel değişkenler ve saat dilimi ortamı tanımlama hakkında daha fazla bilgi için.

Tarafından üretilen dize sonucu **asctime** tam olarak 26 karakter içerir ve form `Wed Jan 02 02:03:55 1980\n\0`. 24 saatlik düzende kullanılır. Tüm alanlar, sabit bir genişliğe sahiptir. Yeni satır karakteri ve null karakteri, dizenin son iki konum kaplar. **asctime** tek, statik olarak ayrılan bir arabellek dizesini tutmak için kullanır. Bu işleve yapılan her çağrı, önceki çağrının sonucu yok eder.

**_wasctime** geniş karakterli sürümüdür **asctime**. **_wasctime** ve **asctime** aynı şekilde davranır.

Bu işlevler kendi parametrelerini doğrular. Varsa *timeptr* null bir işaretçiyse veya aralık dışı değerler içeriyorsa, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, işlev döndürür **NULL** ve ayarlar **errno** için **EINVAL**.

### <a name="generic-text-routine-mapping"></a>Genel metin yordam eşlemesi

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tasctime**|**asctime**|**asctime**|**_wasctime**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**asctime**|\<TIME.h >|
|**_wasctime**|\<TIME.h > veya \<wchar.h >|

## <a name="example"></a>Örnek

Bu program, sistem saatini uzun tamsayı olarak yerleştirir **aclock**, yapısına çevirir **newtime** ve ardından için dize biçiminde çıktı, kullanarak **asctime**işlevi.

```C
// crt_asctime.c
// compile with: /W3

#include <time.h>
#include <stdio.h>

int main( void )
{
    struct tm   *newTime;
    time_t      szClock;

    // Get time in seconds
    time( &szClock );

    // Convert time to struct tm form
    newTime = localtime( &szClock );

    // Print local time as a string.
    printf_s( "Current date and time: %s", asctime( newTime ) ); // C4996
    // Note: asctime is deprecated; consider using asctime_s instead
}
```

```Output
Current date and time: Sun Feb 03 11:38:58 2002
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
