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
ms.openlocfilehash: 624ff1051977804e6cefd97a813dce36cacdc3e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="null-statement"></a>Boş Deyim
"Null" ile bir ifade deyimi açıklamadır *ifade* eksik. Dilin sözdizimi bir deyimi çağırdığında, ancak hiçbir ifade değerlendirmesini çağırmadığında yararlı olur. Noktalı virgül içerir.  
  
 Boş deyimler genellikle yineleme deyimlerinde yer tutucu olarak veya bileşik deyimlerin ya da işlevlerin sonunda üzerine etiket yerleştirilecek deyimler olarak kullanılır.  
  
 Aşağıdaki kod parçası, bir dizeyi diğerine nasıl kopyalayacağınızı gösterir ve boş deyim içerir:  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade Deyimi](../cpp/expression-statement.md)