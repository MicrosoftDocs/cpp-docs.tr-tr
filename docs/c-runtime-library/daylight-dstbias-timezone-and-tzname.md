---
title: _daylight, _dstbias, _timezone ve _tzname | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 81ab3701ac99aece4710208a0a5d19ce645d287a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="daylight-dstbias-timezone-and-tzname"></a>_daylight, _dstbias, _timezone ve _tzname
`_daylight`, `_dstbias`, `_timezone`, ve `_tzname` bazı saat ve tarih yordamları yerel saat ayarlamaları yapmak için kullanılır. Genel değişkenler yerine kullanılmalıdır daha güvenli işlevsel sürümleri için bu genel değişkenler kullanım dışı bırakıldı.  
  
|Genel değişkeni|İşlev eşdeğeri|  
|---------------------|---------------------------|  
|`_daylight`|[_get_daylight](../c-runtime-library/reference/get-daylight.md)|  
|`_dstbias`|[_get_dstbias](../c-runtime-library/reference/get-dstbias.md)|  
|`_timezone`|[_get_timezone](../c-runtime-library/reference/get-timezone.md)|  
|`_tzname`|[_get_tzname](../c-runtime-library/reference/get-tzname.md)|  
  
 Bunlar Time.h içinde aşağıdaki gibi bildirilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
extern int _daylight;   
extern int _dstbias;   
extern long _timezone;   
extern char *_tzname[2];  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrı sırasında `_ftime`, `localtime`, veya `_tzset`, değerlerini `_daylight`, `_dstbias`, `_timezone`, ve `_tzname` değerinden belirlenir `TZ` ortam değişkeni. Değeri, açıkça ayarlanmazsa `TZ`, `_tzname[0]` ve `_tzname[1]` sırasıyla "PST" ve "Saati" varsayılan ayarları içerir.  Zaman işleme işlevleri ([_tzset](../c-runtime-library/reference/tzset.md), [_ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md), ve [damgasını](../c-runtime-library/reference/localtime-localtime32-localtime64.md)) değerini ayarlama girişimi `_daylight`, `_dstbias` ve `_timezone` tarafından Her bir değişken varsayılan değerini işletim sistemi sorgulama. Saat dilimi genel değişken değerleri aşağıdaki tabloda gösterilmiştir.  
  
|Değişken|Değer|  
|--------------|-----------|  
|`_daylight`|Gün ışığından yararlanma saati (DST) bölge belirtilmişse sıfır olmayan `TZ` veya işletim sisteminden belirlendiği Aksi halde 0. Varsayılan değer 1’dir.|  
|`_dstbias`|Yaz Saati için uzaklık.|  
|`_timezone`|Eşgüdümlü Evrensel Saat ve yerel saat arasındaki farkı saniye cinsinden. Varsayılan değer 28.800 ' dir.|  
|`_tzname[0]`|Saat dilimi adı türetilen `TZ` ortam değişkeni. Varsayılan değer "PST" dir.|  
|`_tzname[1]`|DST bölge adı türetilen `TZ` ortam değişkeni. "Saati" (Pasifik Saati) varsayılan değerdir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel değişkenler](../c-runtime-library/global-variables.md)   
 [_get_daylight](../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../c-runtime-library/reference/get-timezone.md)   
 [_get_tzname](../c-runtime-library/reference/get-tzname.md)