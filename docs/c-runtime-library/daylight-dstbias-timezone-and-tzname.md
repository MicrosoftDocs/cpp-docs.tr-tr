---
title: _daylight, _dstbias, _timezone ve _tzname | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- tzname
- _timezone
- timezone
- _daylight
- _tzname
- daylight
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7428251531c0b57855941ed06c658c7b60224bab
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034440"
---
# <a name="daylight-dstbias-timezone-and-tzname"></a>_daylight, _dstbias, _timezone ve _tzname

`_daylight`, `_dstbias`, `_timezone`, ve `_tzname` bazı tarih yordamları yerel saat ayarlamaları yapmak için kullanılır. Global değişkenler yerine kullanılması gereken daha güvenli işlevsel sürümleri için bu genel değişkenler kullanım dışı bırakıldı.

|Genel değişkeni|İşlevsel eşdeğeri|
|---------------------|---------------------------|
|`_daylight`|[_get_daylight](../c-runtime-library/reference/get-daylight.md)|
|`_dstbias`|[_get_dstbias](../c-runtime-library/reference/get-dstbias.md)|
|`_timezone`|[_get_timezone](../c-runtime-library/reference/get-timezone.md)|
|`_tzname`|[_get_tzname](../c-runtime-library/reference/get-tzname.md)|

Bunlar TIME.h içinde şu şekilde bildirilir.

## <a name="syntax"></a>Sözdizimi

```
extern int _daylight; 
extern int _dstbias; 
extern long _timezone; 
extern char *_tzname[2];
```

## <a name="remarks"></a>Açıklamalar

Çağırması `_ftime`, `localtime`, veya `_tzset`, değerlerini `_daylight`, `_dstbias`, `_timezone`, ve `_tzname` değerinden belirlenir `TZ` ortam değişkeni. Açıkça değerini ayarlamazsanız `TZ`, `_tzname[0]` ve `_tzname[1]` "PST" ve "Pasifik Yaz SAATİ'ne" varsayılan ayarlarını içerir.  Zaman işleme işlevleri ([_tzset](../c-runtime-library/reference/tzset.md), [_ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md), ve [localtime](../c-runtime-library/reference/localtime-localtime32-localtime64.md)) değerini ayarlama girişimi `_daylight`, `_dstbias` ve `_timezone` tarafından işletim sistemi her değişkenin varsayılan değeri için Sorgulanıyor. Saat dilimi genel değişken değerleri aşağıdaki tabloda gösterilmektedir.

|Değişken|Değer|
|--------------|-----------|
|`_daylight`|Gün ışığından yararlanma saatinin (DST) bölgesi belirtilmişse sıfır dışı `TZ` veya işletim sisteminden belirlenen; Aksi takdirde 0. Varsayılan değer 1’dir.|
|`_dstbias`|Gün ışığından yararlanma saatine uzaklığı.|
|`_timezone`|Eşgüdümlü Evrensel Saat ve yerel saat arasındaki saniye farkı. Varsayılan değer 28.800 ' dir.|
|`_tzname[0]`|Saat dilimi adının türetilen `TZ` ortam değişkeni. "PST" varsayılan değerdir.|
|`_tzname[1]`|DST bölgesi adı türetilen `TZ` ortam değişkeni. "Pasifik Yaz SAATİ'ne" (Pasifik Yaz Saati) varsayılan değerdir.|

## <a name="see-also"></a>Ayrıca Bkz.

[Global Değişkenler](../c-runtime-library/global-variables.md)<br/>
[_get_daylight](../c-runtime-library/reference/get-daylight.md)<br/>
[_get_dstbias](../c-runtime-library/reference/get-dstbias.md)<br/>
[_get_timezone](../c-runtime-library/reference/get-timezone.md)<br/>
[_get_tzname](../c-runtime-library/reference/get-tzname.md)