---
title: "Kod sayfaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.international
dev_langs: C++
helpviewer_keywords:
- character sets [C++], code pages
- ANSI [C++], code pages
- system-default code page
- multibyte code pages [C++]
- localization [C++], code pages
- code pages [C++], types of
- locale code pages [C++]
ms.assetid: 4a26fc42-185a-4add-98bf-a7b314ae6186
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 02c1b7de9a8ed5f560a5999af453970785c487f5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="code-pages"></a>Kod Sayfaları
A `code page` sayı, noktalama işaretleri ve diğer karakterlerin içerebilen bir karakter kümesidir. Farklı diller ve yerel ayarlar farklı kod sayfaları kullanabilir. Örneğin, ANSI kod sayfası 1252 İngilizce ve en Avrupa dilleri için kullanılır; OEM kod sayfası 932 Japonca Kanji için kullanılır.  
  
 Kod sayfası bir tablodaki bir veya birden çok baytlı değerler tek baytlı değerler karakter eşlemesi olarak temsil edilebilir. Çok sayıda kod sayfaları ASCII karakter aralığı 0x00 - 0x7F karakter kümesini paylaşır.  
  
 Microsoft çalışma zamanı kitaplığı aşağıdaki kod sayfaları türlerini kullanır:  
  
-   Sistem varsayılan ANSI kod sayfası. Varsayılan olarak, başlangıçta çalışma zamanı sistem otomatik olarak birden çok baytlı kod sayfası işletim sisteminden alınan sistem varsayılan ANSI kod sayfası için ayarlar. Arayın:  
  
    ```  
    setlocale ( LC_ALL, "" );  
    ```  
  
     Ayrıca yerel sistem varsayılan ANSI kod sayfasına ayarlar.  
  
-   Yerel ayar kod sayfası. Çalışma zamanı yordamları sayısı davranışını yerel ayar kod sayfası içerir geçerli yerel ayarda bağlıdır. (Daha fazla bilgi için bkz: [yerel ayara bağımlı yordamlar](../c-runtime-library/locale.md).) Varsayılan olarak, tüm yerel ayara bağımlı yordamlar Microsoft Çalışma Zamanı Kitaplığı'ndaki "C" yerel karşılık gelen kod sayfasını kullanın. Çalışma zamanında değiştirme veya yerel ayar kod sayfası çağrısıyla kullanımda sorgu [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
-   Birden çok baytlı kod sayfası. Çok baytlı karakter yordamları Çalışma Zamanı Kitaplığı'nda çoğunu davranışını geçerli çok baytlı kod sayfası ayarına bağlıdır. Varsayılan olarak, bu yordamlar sistem varsayılan ANSI kod sayfasını kullanın. Çalışma zamanında sorgulamak ve çok baytlı kod sayfası ile değiştirmek [_getmbcp](../c-runtime-library/reference/getmbcp.md) ve [_setmbcp](../c-runtime-library/reference/setmbcp.md)sırasıyla.  
  
-   "C" yerel ayarını ANSI C programları geleneksel imzalayan yerel karşılık gelecek şekilde tanımlanır. ("C" kod sayfası) "C" yerel ayar kod sayfası ASCII karakter kümesi karşılık gelir. Örneğin, "C" yerel olarak `islower` değerlerini 0x61 - yalnızca 0x7A true değerini döndürür. Başka bir yerel olarak `islower` bu yerel ayara tarafından tanımlandığı şekilde bu yanı sıra diğer değerler doğru döndürebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uluslararası duruma getirme](../c-runtime-library/internationalization.md)   
 [Kategorilere göre çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)