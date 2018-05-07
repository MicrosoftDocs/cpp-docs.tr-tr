---
title: ODBC bileşenlerini müşterilerinize yeniden dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC components, redistributing
- ODBC, distributing components
- components [C++], distributing
- ODBC Administrator
- components [C++]
- components [C++], redistributing
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e0427228b8fb3e852cf1d9ee66a10c9290b860b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="redistributing-odbc-components-to-your-customers"></a>ODBC Bileşenlerini Müşterilerinize Yeniden Dağıtma
ODBC Yöneticisi programları işlevselliğini uygulamanıza dahil, kullanıcılarınıza bu programları çalıştır dosyaları da dağıtmanız gerekir. Bu ODBC dosyaları Visual C++ CD-ROM \OS\System dizininde bulunur. Redistrb.wri dosyası ve lisans sözleşmesini aynı dizinde yeniden dağıtabilirsiniz ODBC dosyaların bir listesini içerir.  
  
 Dağıtmayı planladığınız herhangi bir ODBC sürücüleri için belgelere bakın. Hangi DLL'lerin ve diğer dosyaları dağıtmayı belirlemeniz gerekir. Ayrıca okumalısınız [ODBC bileşenlerini müşterilerinize yeniden dağıtma](../../data/odbc/redistributing-odbc-components-to-your-customers.md), nasıl ODBC bileşenleri yeniden dağıtacağınız açıklanmaktadır.  
  
 Ayrıca, çoğu durumda başka bir dosya eklemeniz gerekir. Odbccr32.dll ODBC İmleç Kitaplığı ' dir. Bu kitaplık düzey 1 sürücüleri, ileriye ve geriye doğru kaydırma yeteneği verir. Ayrıca, anlık görüntüleri destekleme özelliği sağlar. ODBC İmleç Kitaplığı hakkında daha fazla bilgi için bkz: [ODBC: ODBC İmleç Kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
 Aşağıdaki konular ODBC ile veritabanı sınıflarını kullanma hakkında daha fazla bilgi sağlar:  
  
-   [ODBC: ODBC İmleç Kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md)  
  
-   [ODBC: ODBC Veri Kaynağını Yapılandırma](../../data/odbc/odbc-configuring-an-odbc-data-source.md)  
  
-   [ODBC: ODBC API İşlevlerini Doğrudan Çağırma](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ODBC temelleri](../../data/odbc/odbc-basics.md)   
 [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md)