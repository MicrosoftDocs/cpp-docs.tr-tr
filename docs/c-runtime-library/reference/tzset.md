---
title: _tzset | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _tzset
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
- _tzset
dev_langs:
- C++
helpviewer_keywords:
- _tzset function
- time environment variables
- environment variables, setting time
ms.assetid: 3f6ed537-b414-444d-b272-5dd377481930
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15464ac8be075d44a9a42223964239538508a683
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417382"
---
# <a name="tzset"></a>_tzset

Ayarlar, ortam değişkenleri zaman.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
void _tzset( void );
```

## <a name="remarks"></a>Açıklamalar

**_Tzset** işlevini kullanır ve ortam değişkeninin geçerli ayar **TZ** üç genel değişkenleri için değerleri atamak için: **_daylight**, **_timezone** , ve **_tzname**. Bu değişkenler tarafından kullanılan [_ftime](ftime-ftime32-ftime64.md) ve [damgasını](localtime-localtime32-localtime64.md) yerel saate ve tarafından Eşgüdümlü Evrensel Saat (UTC) düzeltmeler yapmak için işlevleri [zaman](time-time32-time64.md) için işlevi Sistem saati UTC işlem. Ayarlamak için aşağıdaki sözdizimini kullanın **TZ** ortam değişkeni:

> **TZ ayarlamak =**_tzn_ \[ **+** &#124; **-**]*hh* \[ **:**_mm_\[**:**_ss_]] [*dzn*]

|Parametre|Açıklama|
|-|-|
*tzn*|PST gibi üç harfli saat dilimi adı. Yerel saat UTC doğru uzaklık belirtmeniz gerekir.
*hh*|UTC ve yerel saat arasındaki farkı saat. İşareti (+) pozitif değer isteğe bağlıdır.
*mm*|Dakika. Gelen ayrılmış *hh* bir virgülle (**:**).
*ss*|Saniye sayısı. Gelen ayrılmış *mm* bir virgülle (**:**).
*Dzn*|Üç harfli gün ışığından yararlanma saati dilimi saati gibi. Yaz Saati hiçbir zaman yürürlükte yerleşim ise, **TZ** için bir değer olmadan *dzn*. C çalışma zamanı kitaplığı gün ışığından yararlanma saati (DST) hesaplama uygulamak için Amerika Birleşik Devletleri kuralları varsayar.

> [!NOTE]
> Bilgisayar zaman farkı oturum dikkatli olun. UTC (geriye doğru yerine) için yerel saat uzaklığı zaman farkı olduğu için onun oturum sezgisel beklediğiniz tersi olabilir. Öncesinde UTC saat dilimleri için saat farkı negatifse; Bu UTC arkasında pozitif farktır.

Örneğin, ayarlamak için **TZ** Almanya, geçerli saat diliminizde karşılık gelecek şekilde ortam değişkeni komut satırında aşağıdakileri girin:

> **TZ ayarlamak GST 1GDT =**

Bu kullanımları GST Almanca Standart Saati, belirtmek için komut UTC Almanya arkasında (veya Almanya UTC öncesinde bir saattir diğer sözcükler,), bir saat olduğunu varsayar ve Almanya – ışığından gözlemleyen varsayar.

Varsa **TZ** değeri ayarlanmazsa, **_tzset** işletim sistemi tarafından belirtilen saat dilimi bilgilerini kullanmaya çalışır. Windows işletim sisteminde, Denetim Masası'ndaki Tarih uygulama bu bilgileri belirtildi. Varsa **_tzset** bu bilgileri elde edemiyor Pasifik saat diliminde güveninin varsayılan PST8PDT kullanır.

Temel **TZ** ortam değişkeni değeri, aşağıdaki değerleri genel değişkenler atanır **_daylight**, **_timezone**, ve **_tzname** zaman **_tzset** adı verilir:

|Genel değişkeni|Açıklama|Varsayılan değer|
|---------------------|-----------------|-------------------|
|**_daylight**|Bir gün ışığından yararlanma saati bölge belirtilmişse sıfır olmayan bir değer **TZ** ayarlama; Aksi takdirde, 0.|1.|
|**_timezone**|Yerel saat ile UTC arasındaki farkı saniye cinsinden.|28800 (28800 saniye eşittir 8 saat)|
|**_tzname**[0]|Saat dilimi adı değeri dize **TZ** ortam değişkeni; boş ise **TZ** ayarlanmadı.|PST|
|**_tzname**[1]|Dize değeri gün ışığından yararlanma saati bölgenin; gelen gün ışığından yararlanma saati dilimi atlanırsa boş **TZ** ortam değişkeni.|SAATİ|

Önceki tabloda gösterilen varsayılan değerler **_daylight** ve **_tzname** dizi karşılık gelen "PST8PDT." Gelen DST bölge atlanırsa **TZ** ortam değişkeni, değeri **_daylight** 0'dır ve [_ftime](ftime-ftime32-ftime64.md), [gmtime](gmtime-gmtime32-gmtime64.md)ve [damgasını](localtime-localtime32-localtime64.md) işlevler için kendi DST bayraklar 0 döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_tzset**|\<time.h >|

**_Tzset** Microsoft'a özgü işlevdir. Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_tzset.cpp
// This program uses _tzset to set the global variables
// named _daylight, _timezone, and _tzname. Since TZ is
// not being explicitly set, it uses the system time.

#include <time.h>
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
    _tzset();
    int daylight;
    _get_daylight( &daylight );
    printf( "_daylight = %d\n", daylight );
    long timezone;
    _get_timezone( &timezone );
    printf( "_timezone = %ld\n", timezone );
    size_t s;
    char tzname[100];
    _get_tzname( &s, tzname, sizeof(tzname), 0 );
    printf( "_tzname[0] = %s\n", tzname );
    exit( 0 );
}
```

```Output
_daylight = 1
_timezone = 28800
_tzname[0] = Pacific Standard Time
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](utime-utime32-utime64-wutime-wutime32-wutime64.md)<br/>
