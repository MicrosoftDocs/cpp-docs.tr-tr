---
title: Bağlantı türleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- no linkage
- linkage [C++], none
- linkage [C++], types of
- types [C++], linkage
- internal linkage, types of linkage
- external linkage, linkage types
ms.assetid: 41326c7f-4602-4bad-a648-697604858ba0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dfddf0105603311179340a0c6b0b2e8fb328b134
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="types-of-linkage"></a>Bağlantı Türleri
Nesne ve işlev adlarının çeviri birimleri arasında paylaşılma yöntemine bağlantı adı verilir. Bu adlarda şunlar olabilir:  
  
-   Yalnızca kendi çeviri birimlerindeki program öğelerine başvurdukları iç bağlantı; diğer çeviri birimleriyle paylaşılmazlar.  
  
     Başka bir çeviri birimindeki aynı ad, farklı bir nesne veya farklı bir sınıfa başvurabilir. İç bağlantıya sahip adlara, bazen çeviri birimlerinin yereli olarak başvurulabilir.  
  
     İç bağlantıya sahip bir adın örnek bildirimi şu şekildedir:  
  
    ```  
    static int i;   // The static keyword ensures internal linkage.  
    ```  
  
-   Programda herhangi bir çeviri birimindeki program öğelerine başvurabildikleri dış bağlantı; program öğesi çeviri birimleri arasında paylaşılır.  
  
     Başka bir çeviri birimindeki aynı adın, aynı nesneye veya sınıfa başvurması garanti edilir. Dış bağlantıya sahip adlara, bazen genel olarak başvurulur.  
  
     Dış bağlantıya sahip bir adın örnek bildirimi şu şekildedir:  
  
    ```  
    extern int i;  
    ```  
  
-   Bağlantı yok; bu durumda benzersiz varlıklara başvururlar. Başka bir kapsamdaki aynı ad, aynı nesneye başvurmayabilir. Örnek, bir numaralandırmadır. (Bununla birlikte, bir işaretçiyi nesneye bağlantı olmadan geçirebileceğinizi unutmayın. Bu, nesneyi diğer çeviri birimlerinde erişilebilir hale getirir.)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program ve Bağlantı](../cpp/program-and-linkage-cpp.md)