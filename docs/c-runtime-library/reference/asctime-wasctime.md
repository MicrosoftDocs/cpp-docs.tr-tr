---
description: 'Hakkında daha fazla bilgi edinin: asctime, _wasctime'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 3ae075481b364af01bfa75f1cc29423de9fcdbf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260806"
---
# <a name="asctime-_wasctime"></a>asctime, _wasctime

Bir **TM** zaman yapısını bir karakter dizesine Dönüştür. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [asctime_s, _wasctime_s](asctime-s-wasctime-s.md).

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

**asctime** karakter dizesi sonucuna bir işaretçi döndürür; **_wasctime** geniş karakterli dize sonucuna bir işaretçi döndürür. Bir hata dönüş değeri yok.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [asctime_s, _wasctime_s](asctime-s-wasctime-s.md).

**Asctime** işlevi bir yapı olarak depolanan bir saati bir karakter dizesine dönüştürür. *Timeptr* değeri genellıkle, Time. H içinde tanımlanan bir **TM** yapısına işaretçi döndüren **gmtime** veya **localtime** çağrısından elde edilir.

|timeptr üyesi|Değer|
|--------------------|-----------|
|**tm_hour**|Gece yarısından itibaren saat (0-23)|
|**tm_isdst**|Günışığından yararlanma süresi etkinse pozitif; gün ışığından yararlanma saati etkin değilse 0; gün ışığından yararlanma zamanının durumu bilinmiyorsa negatif olur. C çalışma zamanı kitaplığı, gün ışığından yararlanma zamanının (DST) hesaplanmasını uygulamak için Birleşik Devletler ' kurallarını varsayar.|
|**tm_mday**|Ayın günü (1-31)|
|**tm_min**|Saat sonra dakika (0-59)|
|**tm_mon**|Ay (0-11; Ocak = 0)|
|**tm_sec**|Dakika sonra saniye (0-59)|
|**tm_wday**|Haftanın günü (0-6; Pazar = 0)|
|**tm_yday**|Yılın günü (0-365; 1 Ocak = 0)|
|**tm_year**|Yıl (geçerli yıl eksi 1900)|

Dönüştürülen karakter dizesi de yerel saat dilimi ayarlarına göre ayarlanır. Yerel saati yapılandırma hakkında daha fazla bilgi için saat, [_ftime](ftime-ftime32-ftime64.md)ve [localtime](localtime-localtime32-localtime64.md) işlevlerine ve [_tzset](tzset.md) [işlevine, saat](time-time32-time64.md)dilimi ortamı ve genel değişkenleri tanımlama hakkında bilgi için bkz..

**Asctime** tarafından üretilen dize sonucu tam 26 karakter içerir ve forma sahiptir `Wed Jan 02 02:03:55 1980\n\0` . 24 saatlik bir saat kullanılır. Tüm alanların sabit bir genişliği vardır. Yeni satır karakteri ve null karakter, dizenin son iki konumunu kaplar. **asctime** , dönüş dizesini tutmak için tek ve statik olarak ayrılmış bir arabellek kullanır. Bu işleve yapılan her çağrı, önceki çağrının sonucunu yok eder.

**_wasctime** , **astime**'ın geniş karakterli bir sürümüdür. **_wasctime** ve **yoksaati** aynı şekilde davranır.

Bu işlevler, parametrelerini doğrular. *Timeptr* null bir işaretçisiyse veya Aralık dışı değerler Içeriyorsa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlev **null** değerini döndürür ve **errno** 'ı **EINVAL** olarak ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mapping"></a>Generic-Text rutin eşleme

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tasctime**|**asctime**|**asctime**|**_wasctime**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**asctime**|\<time.h>|
|**_wasctime**|\<time.h> veya \<wchar.h>|

## <a name="example"></a>Örnek

Bu program, sistem saatini uzun tamsayı **ACLOCK**'a koyar, bunu **Newtime** yapısına çevirir ve sonra da **asctime** işlevini kullanarak çıktı için dize biçimine dönüştürür.

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
