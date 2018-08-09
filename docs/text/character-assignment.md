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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 084cfd69a3742db10e09e9d97974a0666fa31a47
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010418"
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