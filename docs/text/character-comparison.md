---
title: "Karakter karşılaştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 0b9098dc20c33cccfd64631e7732be0128cb5bb0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="character-comparison"></a>Karakter Karşılaştırma
Aşağıdaki ipuçlarını kullanın:  
  
-   Bilinen bir baytı bir ASCII karakter ile karşılaştırma doğru şekilde çalışır:  
  
    ```  
    if( *sz1 == 'A' )  
    ```  
  
-   İki bilinmeyen karakterleri karşılaştırma Mbstring.h içinde tanımlı makrolar birini kullanımını gerektirir:  
  
    ```  
    if( !_mbccmp( sz1, sz2) )  
    ```  
  
     Bu, hem çift bayt karakter baytını eşitlik için karşılaştırılmasını sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MBCS programlama ipuçları](../text/mbcs-programming-tips.md)   
 [Arabellek Taşması](../text/buffer-overflow.md)