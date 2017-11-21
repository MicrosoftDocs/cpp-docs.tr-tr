---
title: Yerel ayar kategorileri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LC_MAX
- LC_MIN
- LC_MONETARY
- LC_TIME
- LC_NUMERIC
- LC_COLLATE
- LC_CTYPE
- LC_ALL
dev_langs: C++
helpviewer_keywords:
- LC_MIN constant
- LC_MONETARY constant
- LC_CTYPE constant
- locale constants
- LC_MAX constant
- LC_ALL constant
- LC_TIME constant
- LC_NUMERIC constant
- LC_COLLATE constant
ms.assetid: 868f1493-fe5d-4722-acab-bfcd374a063a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dd57f24bd6d790cc03c3e5bbb1e58ec45eee86e0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="locale-categories"></a>Yerel Ayar Kategorileri
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <locale.h>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Yerel ayar kategorileri göre yerelleştirme yordamları bir programın yerel ayar bilgileri hangi kısmının kullanılacak belirtmek için kullanılan bildirim sabittir. Yerel ayar programınız belirli yönlerini özelleştirilebilir yerleşim yeri (veya ülke/bölge) ifade eder. Yerel ayara bağımlı alanlar, örneğin, tarihleri parasal değerleri için görüntüleme biçimi ve biçimlendirme içerir.  
  
|Yerel ayar kategorisi|Etkilenen program bölümleri|  
|---------------------|-------------------------------|  
|`LC_ALL`|Tüm yerel ayarlara özgü davranış (tüm kategorileri)|  
|`LC_COLLATE`|Davranışını `strcoll` ve `strxfrm` işlevleri|  
|`LC_CTYPE`|Karakter işleme işlevleri davranışını (dışında **isdigit**, `isxdigit`, `mbstowcs`, ve `mbtowc`, hangi etkilenmez)|  
|`LC_MAX`|Aynı`LC_TIME`|  
|`LC_MIN`|Aynı`LC_ALL`|  
|`LC_MONETARY`|Tarafından döndürülen bilgi biçimlendirme para `localeconv` işlevi|  
|`LC_NUMERIC`|Karakter biçimlendirilmiş çıktı yordamları için ondalık (örneğin, `printf`), veri dönüştürme yordamları ve tarafından döndürülen parasal biçimlendirme bilgilerini `localeconv` işlevi|  
|`LC_TIME`|Davranışını `strftime` işlevi|  
  
 Bkz: [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) bir örnek.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll işlevleri](../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [Genel sabitler](../c-runtime-library/global-constants.md)