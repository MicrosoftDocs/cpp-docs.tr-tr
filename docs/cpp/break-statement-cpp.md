---
title: break deyimi (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- break_cpp
dev_langs:
- C++
helpviewer_keywords:
- break keyword [C++]
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d1f9c9a09652eb76511c7d059cc70eae3fb99ffd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="break-statement-c"></a>break Deyimi (C++)
`break` Deyimi en yakın kapsayan, yürütme sona erdirir döngü ya da göründüğü koşullu ifade. Denetim, varsa, deyimin sonunu takip eden deyime geçer.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
break;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `break` Deyimi koşullu ile kullanılan [geçiş](../cpp/switch-statement-cpp.md) deyimi ile [yapmak](../cpp/do-while-statement-cpp.md), [için](../cpp/for-statement-cpp.md), ve [sırada](../cpp/while-statement-cpp.md) döngü deyimleri.  
  
 İçinde bir `switch` deyimi, `break` deyimi dışında next deyimi yürütmek program neden `switch` deyimi. Olmadan bir `break` deyimi, eşleşen her deyiminden `case` etiket sonuna `switch` deyimi dahil olmak üzere `default` yan tümcesi, yürütüldüğünde.  
  
 Döngüler içinde `break` deyimi en yakın kapsayan yürütülmesi biter `do`, `for`, veya `while` deyimi. Denetim, varsa, sonlandırılmış deyimi takip eden deyime geçirilir.  
  
 İç içe geçmiş deyimler içinde `break` deyimi yalnızca sona erdirir `do`, `for`, `switch`, veya `while` hemen barındırır deyimi. Kullanabileceğiniz bir `return` veya `goto` denetim daha derine aktarmak için deyimi, yapıları iç içe geçmiş.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösterir `break` deyiminde bir `for` döngü.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    // An example of a standard for loop  
    for (int i = 1; i < 10; i++)  
    {  
        cout << i << '\n';  
        if (i == 4)  
            break;  
    }  
  
    // An example of a range-based for loop  
int nums []{1, 2, 3, 4, 5, 6, 7, 8, 9, 10};  
  
    for (int i : nums) {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
    }  
}  
```  
  
```Output  
In each case:   
1  
2  
3  
```  
  
 Aşağıdaki kodu nasıl kullanılacağını gösterir `break` içinde bir `while` döngü ve `do` döngü.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main() {  
    int i = 0;  
  
    while (i < 10) {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
        i++;  
    }  
  
    i = 0;  
    do {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
        i++;  
    } while (i < 10);  
}  
```  
  
```Output  
In each case:  
0123  
```  
  
 Aşağıdaki kodu nasıl kullanılacağını gösterir `break` anahtar deyimi içinde. Kullanmalısınız `break` kullanmaz, her durumda ayrı ayrı; işlemek istiyorsanız, her durumda `break`, kod yürütmeyi sonraki duruma geçer.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
enum Suit{ Diamonds, Hearts, Clubs, Spades };  
  
int main() {  
  
    Suit hand;  
    . . .  
    // Assume that some enum value is set for hand  
    // In this example, each case is handled separately  
    switch (hand)  
    {  
    case Diamonds:  
        cout << "got Diamonds \n";  
        break;  
    case Hearts:  
        cout << "got Hearts \n";  
        break;  
    case Clubs:  
        cout << "got Clubs \n";  
        break;  
    case Spades:  
        cout << "got Spades \n";  
        break;  
    default:   
          cout << "didn't get card \n";  
    }  
    // In this example, Diamonds and Hearts are handled one way, and  
    // Clubs, Spades, and the default value are handled another way  
    switch (hand)  
    {  
    case Diamonds:  
    case Hearts:  
        cout << "got a red card \n";  
        break;  
    case Clubs:  
    case Spades:   
    default:  
        cout << "didn't get a red card \n";  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atlama deyimleri](../cpp/jump-statements-cpp.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [continue Deyimi](../cpp/continue-statement-cpp.md)