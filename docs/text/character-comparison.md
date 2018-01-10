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
ms.workload: cplusplus
ms.openlocfilehash: 28c2cd3a2e868a595d73d06b5cae8e71ec8cc313
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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