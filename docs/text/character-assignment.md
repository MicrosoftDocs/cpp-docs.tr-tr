---
title: Karakter atama | Microsoft Docs
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
- characters [C++], assignments
- MBCS [C++], character assignments
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 266d3284716647fa073f76ef6ef871a3abd179bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="character-assignment"></a>Karakter Atama
Aşağıdaki örneğe göz önünde bulundurun `while` döngü tarar 'X' dışındaki tüm karakterleri başka bir dizeye kopyalama bir dize:  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
        *sz1++ = *sz2++;  
    else  
        sz2++;  
}  
```  
  
 Kodu baytta kopyalar `sz2` gösterdiği konuma `sz1`, ardından artırır `sz1` sonraki baytı almak için. Ancak sonraki karakteri `sz2` atamayı bir çift bayt karakter `sz1` yalnızca ilk baytı kopyalar. Aşağıdaki kod karakteri güvenle kopyalamak için taşınabilir bir işlev ve için başka bir tanesini kullanır `sz1` ve `sz2` doğru:  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
    {  
        _mbscpy_s( sz1, 1, sz2 );  
        sz1 = _mbsinc( sz1 );  
        sz2 = _mbsinc( sz2 );  
    }  
    else  
        sz2 = _mbsinc( sz2 );  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MBCS programlama ipuçları](../text/mbcs-programming-tips.md)   
 [Karakter Karşılaştırma](../text/character-comparison.md)