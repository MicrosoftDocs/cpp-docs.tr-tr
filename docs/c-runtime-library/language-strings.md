---
title: Dil dizeleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.strings
dev_langs: C++
helpviewer_keywords: language strings
ms.assetid: bbee63b1-af0b-4e44-9eaf-dd3e265c05fd
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d65dc3b8d7dd62994eb0a8b546e290d1b6e47b9a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="language-strings"></a>Dil Dizeleri
`setlocale` Ve `_create_locale` işlevleri Unicode kod sayfası kullanmayın işletim sistemlerinde Windows NLS API desteklenen dilleri kullanabilirsiniz. İşletim sistemi sürümü tarafından desteklenen dillerin bir listesi için bkz: [Ulusal dil desteği (NLS) API Başvurusu](https://www.microsoft.com/resources/msdn/goglobal/default.mspx). Dil dize değerleri olabilir **dil** ve **dil kısaltması** desteklenen dillerin listesi sütunlarının. İşletim sistemi sürümüne göre dil desteği hakkında ek bilgi için bkz: [ek A: Ürün davranışı](http://msdn.microsoft.com/goglobal/bb896001.aspx) [MS-LCID] içindeki: Windows dil kodu tanımlayıcısı (LCID) başvurusu.   
  
C çalışma zamanı kitaplık uygulaması, ayrıca bu dil dizeleri destekler:  
  
|Dil dize|Eşdeğer yerel ayar adı|  
|---------------------|----------------------------|  
|American|en-US|  
|Amerikan İngilizcesi|en-US|  
|Amerikan İngilizcesi|en-US|  
|Avustralya|tr AU|  
|Belçika|NL-olabilir|  
|Kanada|tr-CA|  
|CHH|zh-HK|  
|Şi|zh-SG|  
|Çince|zh|  
|Çince-hongkong|zh-HK|  
|Çince (Basitleştirilmiş)|zh-CN|  
|Çince-Singapur|zh-SG|  
|Çince (Geleneksel)|zh-TW|  
|Felemenkçe-Belçika|NL-olabilir|  
|İngilizce-Amerika|en-US|  
|İngilizce-Avustralya|tr AU|  
|İngilizce belize|tr BZ|  
|İngilizce olabilir|tr-CA|  
|İngilizce Karayipler|tr-029|  
|İngilizce blo|tr-IE|  
|İngilizce Jamaika|tr JM|  
|İngilizce nz|tr NZ|  
|İngilizce-Güney Afrika|tr-ZA|  
|İngilizce-trinidad ve tobago|tr TT|  
|Birleşik Krallık İngilizce|tr GB|  
|İngilizce-ABD|en-US|  
|İngilizce-ABD|en-US|  
|Fransızca Belçika|FR-olabilir|  
|French-Canadian|fr-CA|  
|Fransızca Lüksemburg|FR LU|  
|Fransızca İsviçre|FR CH|  
|Almanca İrlanda|de AT|  
|Almanca lichtenstein|de LI|  
|Almanca Lüksemburg|de LU|  
|Almanca İsviçre|de CH|  
|İrlanda İngilizce|tr-IE|  
|İtalyanca-İsviçre|BT CH|  
|Norveç dili|Yok|  
|Norveççe bokmal|nb-NO|  
|Norveççe nynorsk|nn yok|  
|Portekizce-Brezilya|pt-BR|  
|İspanyolca-Arjantin|ES AR|  
|İspanyolca-Bolivya|ES-BO|  
|İspanyolca-Şili|ES-CL|  
|İspanyolca-Kolombiya|ES CO|  
|İspanyolca-Kosta Rika|ES CR|  
|İspanyolca-Dominik Cumhuriyeti|ES yapın|  
|İspanyolca-Ekvador|ES EC|  
|İspanyolca el salvador|ES SV|  
|İspanyolca-guatemala|ES-GT|  
|İspanyolca-honduras|ES-HN|  
|İspanyolca-Meksika|ES MX|  
|İspanyolca modern|es-ES|  
|İspanyolca-Nikaragua|ES-nı|  
|İspanyolca-panama|ES-PA|  
|İspanyolca-paraguay|ES-PY|  
|İspanyolca-peru|ES-PE|  
|İspanyolca-Porto Riko|ES-PR|  
|İspanyolca-uruguay|ES UY|  
|İspanyolca-venezuela|ES Taşı|  
|İsveççe Finlandiya|sv-FI|  
|İsviçre|de CH|  
|Birleşik Krallık|tr GB|  
|Bize|en-US|  
|ABD|en-US|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Ülke/bölge dizeleri](../c-runtime-library/country-region-strings.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)