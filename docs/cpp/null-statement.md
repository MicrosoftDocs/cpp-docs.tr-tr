---
title: Null deyimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 606f5953-55f0-40c8-ae03-3ee3a819b851
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab391bb75dd6e7a2ef1ccf0951fa93770e6cd316
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408523"
---
# <a name="null-statement"></a>Boş Deyim
"Boş deyim" bir ifade deyimidir *ifade* eksik. Dilin sözdizimi bir deyimi çağırdığında, ancak hiçbir ifade değerlendirmesini çağırmadığında yararlı olur. Noktalı virgül içerir.  
  
 Boş deyimler genellikle yineleme deyimlerinde yer tutucu olarak veya bileşik deyimlerin ya da işlevlerin sonunda üzerine etiket yerleştirilecek deyimler olarak kullanılır.  
  
 Aşağıdaki kod parçası, bir dizeyi diğerine nasıl kopyalayacağınızı gösterir ve boş deyim içerir:  
  
```cpp 
// null_statement.cpp  
char *myStrCpy( char *Dest, const char *Source )  
{  
    char *DestStart = Dest;  
  
    // Assign value pointed to by Source to  
    // Dest until the end-of-string 0 is  
    // encountered.  
    while( *Dest++ = *Source++ )  
        ;   // Null statement.  
  
    return DestStart;  
}  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [İfade Deyimi](../cpp/expression-statement.md)