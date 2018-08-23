---
title: Karakter atama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- characters [C++], assignments
- MBCS [C++], character assignments
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5efdaefdfd961a10d40c00855261eb547164f95
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591407"
---
# <a name="character-assignment"></a>Karakter Atama
Aşağıdaki örnekte göz önünde bulundurun **sırada** döngü 'X' dışındaki tüm karakterlerle başka bir dizeye kopyalama, bir dize tarar:  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
        *sz1++ = *sz2++;  
    else  
        sz2++;  
}  
```  
  
 Kod bayt kopyalar `sz2` konumuna işaret ettiği `sz1`, ardından artırır `sz1` sonraki baytı almanın. Ancak sonraki karakteri `sz2` atama için bir çift bayt karakter `sz1` yalnızca ilk bayt kopyalar. Karakter güvenli bir şekilde kopyalamak için bir taşınabilir işlevi ve başka artırmak için aşağıdaki kodu kullanan `sz1` ve `sz2` doğru:  
  
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