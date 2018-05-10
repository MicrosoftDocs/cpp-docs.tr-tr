---
title: Karakter karşılaştırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b969783a19c0836a8ab81d75820fc688df3ef31e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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