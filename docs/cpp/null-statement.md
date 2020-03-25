---
title: Boş Deyim
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 606f5953-55f0-40c8-ae03-3ee3a819b851
ms.openlocfilehash: 167a1e579c15fd59da1979efd9aa979184318115
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177813"
---
# <a name="null-statement"></a>Boş Deyim

"Null deyimi" *ifadesi* eksik olan bir ifade deyimidir. Dilin sözdizimi bir deyimi çağırdığında, ancak hiçbir ifade değerlendirmesini çağırmadığında yararlı olur. Noktalı virgül içerir.

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
