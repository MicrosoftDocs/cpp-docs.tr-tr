---
title: Bayt Endeksleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 594acadeedad06e9720180c38bd0bcd657391879
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="byte-indices"></a>Bayt Endeksleri
Aşağıdaki ipuçlarını kullanın:  
  
-   Bir dizede dizini ile çalışma bir dizeye işaretçi işleme tarafından teşkil benzer sorunları gösterir. Bu örnekte, bir dizesi bir ters eğik çizgi karakteri tarar göz önünde bulundurun:  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i++;  
    ```  
  
     Bu izi byte, bir ön bayt dizin ve böylece öğesine işaret değil bir `character`.  
  
-   Kullanım [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md) işlevi önceki sorunu çözmek için:  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i += _mbclen ( rgch + i );  
    ```  
  
     Bu ön bayt için bu nedenle doğru dizinler için bir `character`. `_mbclen` İşlevi bir karakter (1 veya 2 bayt) boyutunu belirler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MBCS programlama ipuçları](../text/mbcs-programming-tips.md)   
 [Dizedeki Son Karakter](../text/last-character-in-a-string.md)