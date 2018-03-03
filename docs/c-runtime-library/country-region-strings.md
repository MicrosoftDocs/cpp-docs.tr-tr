---
title: "Ülke bölge dizeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.strings
dev_langs:
- C++
helpviewer_keywords:
- country/region strings
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 94ad99ebd05fa9e37a56f2e12818f30f1f4b1212
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="countryregion-strings"></a>Ülke/Bölge Dizeleri
Ülke ve bölgeye dizeleri için bir yerel ayar belirtimi oluşturmak için bir dil dizesi ile birleştirilebilir `setlocale`, `_wsetlocale`, `_create_locale`, ve `_wcreate_locale` işlevleri. Çeşitli Windows işletim sistemi sürümleri tarafından desteklenen ülke/bölge adları bir listesi için bkz: [Ulusal dil desteği (NLS) API Başvurusu](https://www.microsoft.com/resources/msdn/goglobal/default.mspx). Listelerinde herhangi bir ülkede değerler ülke/bölge dize olması **yerel ayar - dil ülke/bölge** sütun veya içindeki kısaltmalar hiçbirini **ülke veya bölge adı kısaltması** sütun. Windows işletim sistemlerinde sürümüne göre ek dil destek bilgileri için bkz [ek A: Ürün davranışı](http://msdn.microsoft.com/goglobal/bb896001.aspx) [MS-LCID] içindeki: Windows dil kodu tanımlayıcısı (LCID) başvurusu.  
  
 C çalışma zamanı kitaplık uygulaması, aşağıdaki ek ülke/bölge dizeleri ve kısaltmalar da destekler:  
  
|Ülke/bölge dize|Kısaltması|Eşdeğer yerel ayar adı|  
|----------------------------|------------------|----------------------------|  
|Amerika|ABD|en-US|  
|Britanya|GBR|tr GB|  
|Çin|CHN|zh-CN|  
|Çekçe|CZE|cs-CZ|  
|İngiltere|GBR|tr GB|  
|İngiltere|GBR|tr GB|  
|Hollanda|NLD|NL-NL|  
|Hong kong|HKG|zh-HK|  
|Yeni Zelanda|NZL|tr NZ|  
|Nz|NZL|tr NZ|  
|pr Çin|CHN|zh-CN|  
|pr Çin|CHN|zh-CN|  
|Porto Riko|PRI|ES-PR|  
|Slovakça|SVK|SK SK|  
|Güney Afrika|ZAF|AF ZA|  
|Güney Kore|KOR|ko-KR|  
|Güney Afrika|ZAF|AF ZA|  
|Güney Kore|KOR|ko-KR|  
|Trinidad ve tobago|EŞİTLEMESİNİ|tr TT|  
|Birleşik Krallık|GBR|tr GB|  
|Birleşik Krallık|GBR|tr GB|  
|Birleşik Devletleri|ABD|en-US|  
|Bize|ABD|en-US|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Dil dizeleri](../c-runtime-library/language-strings.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)