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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 246801abcb04cc8d9c2fd1a005183501bde240d1
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612332"
---
# <a name="character-comparison"></a>Karakter Karşılaştırma
Aşağıdaki ipuçlarını kullanın:  
  
-   ASCII karakterleriyle ile bilinen bir ön bayt karşılaştırma düzgün şekilde çalışır:  
  
    ```  
    if( *sz1 == 'A' )  
    ```  
  
-   İki bilinmeyen karakterleri karşılaştırma Mbstring.h içinde tanımlanan makroları birini gerektirir:  
  
    ```  
    if( !_mbccmp( sz1, sz2) )  
    ```  
  
     Bu, her iki baytlık bir çift baytlı karakter eşitlik için karşılaştırılması, sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MBCS programlama ipuçları](../text/mbcs-programming-tips.md)   
 [Arabellek Taşması](../text/buffer-overflow.md)