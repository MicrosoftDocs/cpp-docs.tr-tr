---
title: Son bir dizedeki karakter | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- last character in string
- MBCS [C++], last character in string
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 88cde1d2eb30103462f7ae8f8c06274a2977fc36
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="last-character-in-a-string"></a>Dizedeki Son Karakter
Aşağıdaki ipuçlarını kullanın:  
  
-   ASCII karakter birçok durumda kümesini izi bayt aralıkları çakışıyor. Bu gibi durumlarda, dizede taramaları güvenle herhangi bir denetim karakteri için (değerinden 32) kullanabilirsiniz.  
  
-   Bir dizedeki son karakter bir ters bölü karakteri olup olmadığını denetleme kod aşağıdaki satırı göz önünde bulundurun:  
  
    ```  
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?  
        // . . .  
    ```  
  
     Çünkü `strlen` MBCS kullanmayan birden çok baytlı dizedeki karakter sayısını değil bayt sayısı döndürür. Bazı kod sayfalarında (örneğin, 932), ayrıca, unutmayın '\\' (0x5c) geçerli sondaki bayt olduğu (`sz` C dizedir).  
  
     Bu şekilde kodu yeniden için olası bir çözüm şöyledir:  
  
    ```  
    char *pLast;  
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz  
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )  
        // . . .  
    ```  
  
     Bu kod MBCS işlevlerini kullanan `_mbsrchr` ve `_mbsinc`. Bu işlevler MBCS algılayan olduğundan, bunlar ayırt edebilirsiniz bir '\\'karakter ve sondaki bayt'\\'. Dizedeki son karakter ('\0') null ise kod bazı eylemleri gerçekleştirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MBCS programlama ipuçları](../text/mbcs-programming-tips.md)   
 [Karakter Atama](../text/character-assignment.md)