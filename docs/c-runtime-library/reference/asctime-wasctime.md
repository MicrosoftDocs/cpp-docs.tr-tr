---
title: asctime, _wasctime
ms.date: 4/2/2020
api_name:
- _wasctime
- asctime
- _o__wasctime
- _o_asctime
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
ms.openlocfilehash: bda14f3b6046378ad23148371f354bb910163d3c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350486"
---
# <a name="asctime-_wasctime"></a>asctime, _wasctime

**TM** zaman yapısını karakter dizesine dönüştürün. Bu işlevlerin daha güvenli sürümleri mevcuttur; [asctime_s, _wasctime_s](asctime-s-wasctime-s.md)bakın.

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

**asctime** karakter dize sonucuna bir işaretçi döndürür; **_wasctime** geniş karakterli dize sonucuna bir işaretçi döndürür. Hata iade değeri yoktur.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin daha güvenli sürümleri mevcuttur; [asctime_s, _wasctime_s](asctime-s-wasctime-s.md)bakın.

**Asctime** işlevi, yapı olarak depolanan bir zamanı karakter dizesine dönüştürür. *Zaman ptr* değeri genellikle **gmtime** veya **localtime**için bir çağrı elde edilir , her ikisi de TIME tanımlanan bir **tm** yapısına bir işaretçi döndürün. H.

|timeptr üyesi|Değer|
|--------------------|-----------|
|**tm_hour**|Gece yarısından itibaren saatler (0-23)|
|**tm_isdst**|Yaz saati uygulaması geçerliyse pozitif; Yaz saati uygulaması geçerli değilse 0; gün ışığından yararlanma saatinin durumu bilinmiyorsa negatif. C çalışma zamanı kitaplığı, Gün Işığından Yararlanma Saati (DST) hesaplamasını uygulamak için ABD'nin kurallarını varsayar.|
|**tm_mday**|Ayın günü (1-31)|
|**tm_min**|Dakika sonra saat (0-59)|
|**tm_mon**|Ay (0-11; Ocak = 0)|
|**tm_sec**|Saniye dakika sonra (0-59)|
|**tm_wday**|Haftanın günü (0-6; Pazar = 0)|
|**tm_yday**|Yılın günü (0-365; 1 Ocak = 0)|
|**tm_year**|Yıl (şu anki yıl eksi 1900)|

Dönüştürülen karakter dizesi de yerel saat dilimi ayarlarına göre ayarlanır. Yerel saati yapılandırma hakkında bilgi için [saat,](time-time32-time64.md) [_ftime](ftime-ftime32-ftime64.md)ve [yerel saat](localtime-localtime32-localtime64.md) işlevlerive saat dilimi ortamını ve genel değişkenleri tanımlama hakkında bilgi için [_tzset](tzset.md) işlevine bakın.

**Asctime** tarafından üretilen dize sonucu tam olarak 26 karakter içerir ve formu `Wed Jan 02 02:03:55 1980\n\0`vardır. 24 saatlik bir saat kullanılır. Tüm alanların sabit bir genişliği vardır. Yeni satır karakteri ve null karakter dize son iki pozisyonları işgal. **asctime,** dönüş dizesini tutmak için tek, statik olarak ayrılmış bir arabellek kullanır. Bu işleve yapılan her çağrı, önceki çağrının sonucunu yok eder.

**_wasctime** **asctime**geniş karakterli bir sürümüdür. **_wasctime** ve **asctime** aynı şekilde başka türlü çalışır.

Bu işlevler parametrelerini doğrular. *Timeptr* bir null işaretçisi yse veya aralık dışı değerler içeriyorsa, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, işlev **NULL** döndürür ve **EINVAL** **için errno** ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mapping"></a>Genel Metin Rutin Eşleme

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tasctime**|**asctime**|**asctime**|**_wasctime**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**asctime**|\<time.h>|
|**_wasctime**|\<time.h> \<veya wchar.h>|

## <a name="example"></a>Örnek

Bu program uzun tamsayı **aclock**sistem zaman yerleştirir , yapı **ya da yeni zaman** çevirir ve daha sonra **asctime** işlevini kullanarak, çıkış için dize formuna dönüştürür.

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
