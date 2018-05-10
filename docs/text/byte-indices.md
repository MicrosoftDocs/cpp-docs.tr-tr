---
title: Bayt Endeksleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 509e66c7ea458519eaa9dc4f52c8a6b65c789d0f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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