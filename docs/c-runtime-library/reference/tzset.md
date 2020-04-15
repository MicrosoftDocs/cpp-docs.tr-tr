---
title: _tzset
ms.date: 4/2/2020
api_name:
- _tzset
- _o__tzset
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
- _tzset
helpviewer_keywords:
- _tzset function
- time environment variables
- environment variables, setting time
ms.assetid: 3f6ed537-b414-444d-b272-5dd377481930
ms.openlocfilehash: b2537a3bbfd2b5cec6bdf149c520aac7e3344b1e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362191"
---
# <a name="_tzset"></a>_tzset

Zaman ortamı değişkenlerini ayarlar.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
void _tzset( void );
```

## <a name="remarks"></a>Açıklamalar

**_tzset** işlevi üç küresel değişkene değer atamak için çevre **değişkeni TZ'nin** geçerli ayarını kullanır: **_daylight**, **_timezone**ve **_tzname.** Bu [değişkenler, _ftime](ftime-ftime32-ftime64.md) ve [yerel saat](localtime-localtime32-localtime64.md) işlevleri tarafından, eşgüdümlü evrensel zamandan (UTC) yerel saate ve sistem zamanından UTC'yi hesaplamak için [zaman](time-time32-time64.md) fonksiyonuna kadar düzeltmeler yapmak için kullanılır. **TZ** ortam değişkenini ayarlamak için aşağıdaki sözdizimini kullanın:

> **set TZ=**_tzn_ \[ **+**&#124;**-**]*hh*\[**:**_mm_\[**:**_ss_] ][*dzn*]

|Parametre|Açıklama|
|-|-|
| *tzn* | PST gibi üç harfli saat dilimi adı. Yerel saatle UTC'ye doğru mahsup belirtmelisiniz. |
| *Hh* | UTC ile yerel saat arasındaki saat farkı. Pozitif değerler için isteğe bağlı (+) imzalayın. |
| *Mm* | Dakika. Bir kolon ile *hh* ayrılmış (**:**). |
| *Ss* | Saniye. Bir kolon ile *mm* ayrılmış (**:**). |
| *dzn* | PDT gibi üç harfli gün ışığından yararlanma saati dilimi. Gün ışığından yararlanma saati yerellikte hiçbir zaman geçerli değilse, *dzn*için bir değer olmadan **TZ** ayarlayın. C çalışma zamanı kitaplığı, gün ışığından yararlanma saati (DST) hesaplamasını uygulamak için ABD'nin kurallarını varsayar. |

> [!NOTE]
> Saat farkının işaretini hesaplamaya özen kaydedin. Saat farkı yerel saatten UTC'ye (tam tersi değil) ofset olduğundan, işareti sezgisel olarak beklediğiniz şeyin tam tersi olabilir. UTC'den sonraki saat dilimleri için saat farkı negatiftir; UTC arkasında olanlar için, fark olumludur.

Örneğin, **TZ** ortam değişkenini Almanya'daki geçerli saat dilimine karşılık gelecek şekilde ayarlamak için komut satırına aşağıdakileri girin:

> **set TZ=GST-1GDT**

Bu komut, Almanya'nın standart saatini belirtmek için GST kullanır, UTC'nin Almanya'nın bir saat gerisinde olduğunu (veya başka bir deyişle Almanya'nın UTC'den bir saat önde olduğunu) ve Almanya'nın gün ışığından yararlanma saatini gözlemlediğini varsayar.

**TZ** değeri ayarlanmamışsa, **_tzset** işletim sistemi tarafından belirtilen saat dilimi bilgilerini kullanmaya çalışır. Windows işletim sisteminde, bu bilgiler Denetim Masası'ndaki Tarih/Saat uygulamasında belirtilir. **_tzset** bu bilgileri alamıyorsa, varsayılan olarak PST8PDT kullanır ve bu da Pasifik Saat dilimini belirtir.

**TZ** ortamı değişken değerine bağlı olarak, aşağıdaki değerler _daylight **,** **_timezone**ve **_tzset** çağrıldığında **_tzname** olan genel değişkenlere atanır:

|Küresel değişken|Açıklama|Varsayılan değer|
|---------------------|-----------------|-------------------|
|**_daylight**|**TZ** ayarında gün ışığından yararlanma saati belirtilmişse sıfır olmayan değer; aksi takdirde, 0.|1|
|**_timezone**|Yerel saat ile UTC arasındaki saniye farkı.|28800 (28800 saniye 8 saate eşittir)|
|**_tzname**[0]|**TZ** çevresel değişkeninden saat dilimi adının string değeri; **TZ** ayarlanmadıysa boş.|Pst|
|**_tzname**[1]|Gün ışığından yararlanma-saat diliminin dize değeri; **TZ** çevresel değişkeninden gün ışığından yararlanma saati dilimi atlanırsa boş.|Pdt|

**_daylight** için önceki tabloda gösterilen varsayılan değerler ve **_tzname** dizi "PST8PDT" karşılık gelir. DST bölgesi **TZ** çevresel değişkeninden atlanırsa, **_daylight** değeri 0'dır ve [_ftime](ftime-ftime32-ftime64.md), [gmtime](gmtime-gmtime32-gmtime64.md)ve [yerel saat](localtime-localtime32-localtime64.md) fonksiyonları DST bayrakları için 0 döndürer.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_tzset**|\<time.h>|

_tzset **_tzset** işlevi Microsoft'a özgüdür. Daha fazla bilgi için [Uyumluluk'a](../../c-runtime-library/compatibility.md)bakın.

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
