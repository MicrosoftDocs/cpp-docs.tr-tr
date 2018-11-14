---
title: _tzset
ms.date: 11/04/2016
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
helpviewer_keywords:
- _tzset function
- time environment variables
- environment variables, setting time
ms.assetid: 3f6ed537-b414-444d-b272-5dd377481930
ms.openlocfilehash: 6312297e6daa9b4790674bd26d21812d5bee34c6
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330261"
---
# <a name="tzset"></a>_tzset

Zaman ortam değişkenlerini ayarlar.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
void _tzset( void );
```

## <a name="remarks"></a>Açıklamalar

**_Tzset** işlevi, ortam değişkeninin geçerli ayarını kullanan **TZ** üç genel değişkenlerine değer atamak için: **_daylight**, **_timezone** , ve **_tzname**. Bu değişkenler tarafından kullanılan [_ftime](ftime-ftime32-ftime64.md) ve [localtime](localtime-localtime32-localtime64.md) Eşgüdümlü Evrensel Saat (UTC), yerel saat ve tarafından düzeltmeler yapmak için işlevleri [zaman](time-time32-time64.md) işlevi UTC sistem saatinden hesaplamak. Ayarlamak için aşağıdaki sözdizimini kullanın **TZ** ortam değişkeni:

> **TZ ayarlamak =**_tzn_ \[ **+** &#124; **-**]*hh* \[ **:**_mm_\[**:**_ss_]] [*dzn*]

|Parametre|Açıklama|
|-|-|
| *tzn* | Üç harfli saat dilim adı, PDT gibi. UTC yerel saatinden doğru sapmayı belirtmeniz gerekir. |
| *hh* | UTC ve yerel saat arasındaki saat farkı. İşaretini (+) pozitif değerler için isteğe bağlıdır. |
| *aa* | Dakika. Ayrılmıştır *hh* bir virgülle (**:**). |
| *ss* | Saniye sayısı. Ayrılmıştır *mm* bir virgülle (**:**). |
| *Dzn* | Üç harfli Yaz Saati dilimi, PDT gibi. Gün ışığından yararlanma hiçbir zaman yürürlükte yerleşim içinde değilse, **TZ** için bir değer olmadan *dzn*. C çalışma zamanı kitaplığı, gün ışığından yararlanma saatinin (DST) hesaplanmasını uygulamak için ABD kurallarını varsayar. |

> [!NOTE]
> Al, saat farkının işaretini hesaplarken dikkatli olun. Zaman farkı yerel saat uzaklığı için UTC (tersi yerine) olduğundan, işareti beklediğinizin zıttı tersi olabilir. Utc'den saat dilimleri için saat farkı negatiftir; Bu gerisindekiler için fark pozitiftir.

Örneğin, ayarlanacak **TZ** ortam değişkenini Almanya'daki geçerli saat dilimine karşılık gelecek şekilde, komut satırında aşağıdakileri girin:

> **TZ ayarlamak GST 1GDT =**

Bu komut, Alman standart saatini göstermek için GST kullanır UTC Almanya, utc'nin (veya Almanya, utc'nin bir saat olan başka bir deyişle,), bir saat olduğunu varsayar ve Almanya'nın Yaz Saati uygulamasını gözlediğini varsayar.

Varsa **TZ** değeri ayarlanmazsa, **_tzset** işletim sisteminin belirttiği zaman dilimini kullanmaya çalışır. Windows işletim sisteminde, Denetim Masası'ndaki Tarih/saat uygulamasında bu bilgiler belirtilir. Varsa **_tzset** bu bilgiyi elde PST8PDT Pasifik Saat dilimini varsayılan olarak kullanır.

Temel **TZ** ortam değişken değerini, aşağıdaki değerleri genel değişkenlerine atanır **_daylight**, **_timezone**, ve **_tzname** olduğunda **_tzset** çağrılır:

|Genel değişkeni|Açıklama|Varsayılan değer|
|---------------------|-----------------|-------------------|
|**_daylight**|Gün ışığından yararlanma saat dilimi belirtilmişse sıfır olmayan bir değer **TZ** ayarlama; Aksi takdirde 0.|1.|
|**_timezone**|Yerel saat ile UTC arasındaki saniye farkı.|28800 (28800 saniye 8 saate eşittir)|
|**_tzname**[0]|Dize değeri saat dilimi adının **TZ** ortam değişkeni; boş ise **TZ** ayarlanmadı.|PASİFİK SAATİ|
|**_tzname**[1]|Gün ışığından yararlanma saat dilimi dize değeri; gün ışığından yararlanma saat dilimi atlanırsa boş **TZ** ortam değişkeni.|PDT|

Önceki tabloda gösterilen varsayılan değerler **_daylight** ve **_tzname** dizi karşılık gelen "PST8PDT" DST bölgesi atlanırsa **TZ** ortam değişkeni, değerini **_daylight** 0'dır ve [_ftime](ftime-ftime32-ftime64.md), [gmtime](gmtime-gmtime32-gmtime64.md)ve [localtime](localtime-localtime32-localtime64.md) İşlevler, kendi DST bayrakları için 0 döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_tzset**|\<TIME.h >|

**_Tzset** Microsoft'a özgü işlevidir. Daha fazla bilgi için [Uyumluluk](../../c-runtime-library/compatibility.md).

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
