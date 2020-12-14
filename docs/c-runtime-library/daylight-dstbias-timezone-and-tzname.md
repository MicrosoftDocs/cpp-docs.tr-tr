---
description: 'Hakkında daha fazla bilgi edinin: _daylight, _dstbias, _timezone ve _tzname'
title: _daylight, _dstbias, _timezone ve _tzname
ms.date: 11/04/2016
f1_keywords:
- tzname
- _timezone
- timezone
- _daylight
- _tzname
- daylight
helpviewer_keywords:
- time zones
- time adjustments
- timezone variables
- _tzname function
- _daylight function
- _timezone function
- daylight function
- local time adjustments
- timezone function
- tzname function
- time-zone variables
ms.assetid: d06c7292-6b99-4aba-b284-16a96570c856
ms.openlocfilehash: aaa1d76276e4b4117d5f07695875481215c4122e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258791"
---
# <a name="_daylight-_dstbias-_timezone-and-_tzname"></a>_daylight, _dstbias, _timezone ve _tzname

`_daylight`, `_dstbias` , `_timezone` ve, `_tzname` yerel zaman ayarlamaları yapmak için bazı zaman ve Tarih yordamlarında kullanılır. Bu genel değişkenler, genel değişkenlerin yerine kullanılması gereken daha güvenli işlevsel sürümler için kullanımdan kaldırılmıştır.

|Genel değişken|İşlevsel eşdeğer|
|---------------------|---------------------------|
|`_daylight`|[_get_daylight](../c-runtime-library/reference/get-daylight.md)|
|`_dstbias`|[_get_dstbias](../c-runtime-library/reference/get-dstbias.md)|
|`_timezone`|[_get_timezone](../c-runtime-library/reference/get-timezone.md)|
|`_tzname`|[_get_tzname](../c-runtime-library/reference/get-tzname.md)|

Zaman. h 'de şu şekilde bildirilmiştir.

## <a name="syntax"></a>Syntax

```
extern int _daylight;
extern int _dstbias;
extern long _timezone;
extern char *_tzname[2];
```

## <a name="remarks"></a>Açıklamalar

,, Ve ' a yapılan bir çağrıda,, `_ftime` `localtime` `_tzset` ve değerleri, `_daylight` `_dstbias` `_timezone` `_tzname` `TZ` ortam değişkeninin değerinden belirlenir. Değerini açıkça ayarlamazsanız `TZ` `_tzname[0]` ve `_tzname[1]` sırasıyla "PST" ve "Pasifik" varsayılan ayarlarını içeriyorsa.  Zaman işleme işlevleri ([_tzset](../c-runtime-library/reference/tzset.md), [_ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md)ve [localtime](../c-runtime-library/reference/localtime-localtime32-localtime64.md)), değerlerini ayarlamaya çalışır `_daylight` `_dstbias` ve `_timezone` işletim sistemini her bir değişkenin varsayılan değeri için sorgular. Saat dilimi genel değişken değerleri aşağıdaki tabloda gösterilmiştir.

|Değişken|Değer|
|--------------|-----------|
|`_daylight`|Gün ışığından yararlanma saati (DST) bölgesi içinde veya işletim sisteminde belirtilmişse sıfır olmayan bir değer `TZ` ; Aksi takdirde, 0. Varsayılan değer 1’dir.|
|`_dstbias`|Gün ışığından yararlanma saati için fark.|
|`_timezone`|Eşgüdümlü Evrensel Saat ve yerel saat arasındaki saniye cinsinden fark. Varsayılan değer 28.800 ' dir.|
|`_tzname[0]`|Ortam değişkeninden türetilen saat dilimi adı `TZ` . Varsayılan değer "PST" dir.|
|`_tzname[1]`|Ortam değişkeninden türetilmiş DST bölge adı `TZ` . Varsayılan değer "pasıfık" değeridir (Pasifik yaz saati).|

## <a name="see-also"></a>Ayrıca bkz.

[Genel değişkenler](../c-runtime-library/global-variables.md)<br/>
[_get_daylight](../c-runtime-library/reference/get-daylight.md)<br/>
[_get_dstbias](../c-runtime-library/reference/get-dstbias.md)<br/>
[_get_timezone](../c-runtime-library/reference/get-timezone.md)<br/>
[_get_tzname](../c-runtime-library/reference/get-tzname.md)
