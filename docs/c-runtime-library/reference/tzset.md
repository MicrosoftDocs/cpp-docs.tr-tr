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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 0791fe6002b751906c6bc6f83dafe1ccf202bc8b
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562031"
---
# <a name="_tzset"></a>_tzset

Saat ortam değişkenlerini ayarlar.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
void _tzset( void );
```

## <a name="remarks"></a>Açıklamalar

**_Tzset** işlevi, üç genel değişkene değer atamak için **TZ** ortam değişkeninin geçerli ayarını kullanır: **_daylight**, **_timezone**ve **_tzname**. Bu değişkenler, Eşgüdümlü Evrensel Saat (UTC) ile yerel saate ve UTC 'yi sistem saatinden hesaplamak için [zaman](time-time32-time64.md) işlevine göre düzeltmeler yapmak üzere [_ftime](ftime-ftime32-ftime64.md) ve [localtime](localtime-localtime32-localtime64.md) işlevleri tarafından kullanılır. **TZ** ortam değişkenini ayarlamak için aşağıdaki sözdizimini kullanın:

> **TZ =**_tzn_ \[ **+**&#124;**-** ]*HH* \[ **:**_mm_ \[ **:**_SS_]] [*dzn*] ayarla

 *tzn* \
 PST gibi üç harfli saat dilimi adı. Yerel saatten UTC olarak doğru sapmayı belirtmeniz gerekir.

 *ss* \
 UTC ve yerel saat arasındaki saat cinsinden fark. İşaret (+) pozitif değerler için isteğe bağlıdır.

 *d* \
 Dakika. İki nokta üst üste (**:**) ile *HH* ile ayrılır.

 *ss* \
 Saniyeden. Bir iki nokta (**:**) ile *mm* 'den ayrılır.

 *dzn* \
 PASIFIK saati gibi üç harfli Yaz Saati dilimi. Gün ışığından yararlanma saati hiçbir zaman konum içinde etkin değilse, bir *dzn*değeri olmadan **TZ** ayarlayın. C çalışma zamanı kitaplığı, gün ışığından yararlanma zamanının (DST) hesaplanmasını uygulamak için Birleşik Devletler ' kurallarını varsayar.

> [!NOTE]
> Zaman farkının işaretini hesaplarken dikkatli olmak. Saat farkı, yerel saatten UTC 'ye (tersi değil) göre farklılık yaptığından, işareti, ne kadar çok beklendiğini tahmin edebileceğinize karşı bir değer olabilir. UTC 'nin önünde geçen saat dilimleri için saat farkı negatif olur; UTC 'nin gerisinde, fark pozitif bir değer.

Örneğin, **TZ** ortam değişkenini Almanya 'daki geçerli saat dilimine karşılık gelecek şekilde ayarlamak için komut satırına şunu girin:

> **TZ = GST-1GDT ayarla**

Bu komut, Almanya standart saatini göstermek için GST kullanır, UTC 'nin bir saat (veya başka bir deyişle Almanya 'nın bir saat UTC) olduğunu varsayar ve Almanya 'nın gün ışığından yararlanma saatine hizmet ettiği varsayılır.

**TZ** değeri ayarlanmamışsa, **_tzset** işletim sistemi tarafından belirtilen saat dilimi bilgilerini kullanmaya çalışır. Windows işletim sisteminde bu bilgiler Denetim Masası 'ndaki Tarih/Saat uygulamasında belirtilir. **_Tzset** bu bilgileri edinemez, varsayılan olarak Pasifik saati DILIMINI belirten PST8PDT kullanır.

**TZ** ortam değişkeni değerine bağlı olarak, **_tzset** çağrıldığında aşağıdaki değerler **_daylight**, **_timezone**ve **_tzname** genel değişkenlere atanır:

|Genel değişken|Açıklama|Varsayılan değer|
|---------------------|-----------------|-------------------|
|**_daylight**|**TZ** ayarında bir yaz saati zaman dilimi belirtilmişse sıfır olmayan değer; Aksi takdirde, 0.|1|
|**_timezone**|Saniye cinsinden yerel saat ve UTC arasındaki fark.|28800 (28800 saniye eşittir 8 saat)|
|**_tzname**[0]|**TZ** çevresel değişkeninden saat dilimi adının dize değeri; **TZ** ayarlanmamışsa boştur.|PASIFIK|
|**_tzname**[1]|Gün ışığından yararlanma saati diliminin dize değeri; **TZ** çevresel değişkenden günışığından yararlanma zaman dilimi atlanırsa boştur.|SAATI|

**_Daylight** ve **_tzname** dizisi için yukarıdaki tabloda GÖSTERILEN varsayılan değerler "PST8PDT" öğesine karşılık gelir. DST bölgesi **TZ** çevresel değişkeninden atlanırsa, **_daylight** değeri 0 ve [_ftime](ftime-ftime32-ftime64.md), [GMSAATI](gmtime-gmtime32-gmtime64.md)ve [localtime](localtime-localtime32-localtime64.md) işlevleri, DST bayrakları için 0 döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_tzset**|\<time.h>|

**_Tzset** Işlevi, Microsoft 'a özgüdür. Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
