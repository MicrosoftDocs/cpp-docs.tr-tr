---
title: "ODBC bileşenlerini müşterilerinize yeniden dağıtma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC components, redistributing
- ODBC, distributing components
- components [C++], distributing
- ODBC Administrator
- components [C++]
- components [C++], redistributing
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 861eceef234b77b96179c51979cb7d1c0d09eeeb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="redistributing-odbc-components-to-your-customers"></a>ODBC Bileşenlerini Müşterilerinize Yeniden Dağıtma
ODBC Yöneticisi programları işlevselliğini uygulamanıza dahil, kullanıcılarınıza bu programları çalıştır dosyaları da dağıtmanız gerekir. Bu ODBC dosyaları Visual C++ CD-ROM \OS\System dizininde bulunur. Redistrb.wri dosyası ve lisans sözleşmesini aynı dizinde yeniden dağıtabilirsiniz ODBC dosyaların bir listesini içerir.  
  
 Dağıtmayı planladığınız herhangi bir ODBC sürücüleri için belgelere bakın. Hangi DLL'lerin ve diğer dosyaları dağıtmayı belirlemeniz gerekir. Ayrıca okumalısınız [ODBC bileşenlerini müşterilerinize yeniden dağıtma](../../data/odbc/redistributing-odbc-components-to-your-customers.md), nasıl ODBC bileşenleri yeniden dağıtacağınız açıklanmaktadır.  
  
 Ayrıca, çoğu durumda başka bir dosya eklemeniz gerekir. Odbccr32.dll ODBC İmleç Kitaplığı ' dir. Bu kitaplık düzey 1 sürücüleri, ileriye ve geriye doğru kaydırma yeteneği verir. Ayrıca, anlık görüntüleri destekleme özelliği sağlar. ODBC İmleç Kitaplığı hakkında daha fazla bilgi için bkz: [ODBC: ODBC İmleç Kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
 Aşağıdaki konular ODBC ile veritabanı sınıflarını kullanma hakkında daha fazla bilgi sağlar:  
  
-   [ODBC: ODBC imleç kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md)  
  
-   [ODBC: ODBC veri kaynağını yapılandırma](../../data/odbc/odbc-configuring-an-odbc-data-source.md)  
  
-   [ODBC: ODBC API işlevlerini doğrudan çağırma](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ODBC temelleri](../../data/odbc/odbc-basics.md)   
 [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md)