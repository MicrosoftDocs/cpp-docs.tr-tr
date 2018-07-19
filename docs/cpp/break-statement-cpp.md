---
title: break deyimi (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- break_cpp
dev_langs:
- C++
helpviewer_keywords:
- break keyword [C++]
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00a1122dffac0bdb61ba3799ce78ed3403e6d478
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948118"
---
# <a name="break-statement-c"></a>break Deyimi (C++)
**Sonu** deyimi en yakın kapsayan yürütme sona erer döngü ya da içinde göründüğü koşullu deyimin. Denetim, varsa, deyimin sonunu takip eden deyime geçer.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
break;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Sonu** deyimi koşullu kullanılır [geçiş](../cpp/switch-statement-cpp.md) deyimi ile [yapmak](../cpp/do-while-statement-cpp.md), [için](../cpp/for-statement-cpp.md), ve [oluştu](../cpp/while-statement-cpp.md) döngü deyimleriyle.  
  
 İçinde bir **geçiş** deyimi **sonu** deyimi, programın dışındaki bir sonraki deyimin yürütmesine neden olur **geçiş** deyimi. Olmadan bir **sonu** deyimi, eşleşen her deyim **çalışması** sonuna etiket **geçiş** deyimi de dahil olmak üzere **varsayılan**yan tümcesi yürütülür.  
  
 Döngülerde, **sonu** deyimi, en yakın kapsayan yürütülmesini sonlandırır **yapmak**, **için**, veya **sırada** deyimi. Denetim, varsa, sonlandırılmış deyimi takip eden deyime geçirilir.  
  
 İç içe geçmiş deyimler içinde **sonu** deyimini sonlandırır yalnızca **yapmak**, **için**, **geçiş**, veya **çalışırken**hemen kendisini kapsayan deyimi. Kullanabileceğiniz bir **dönüş** veya **goto** denetimi daha derin bir şekilde aktarmak için deyimi iç içe yapılar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod nasıl kullanılacağını gösterir **sonu** deyiminde bir **için** döngü.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    // An example of a standard for loop  
    for (int i = 1; i < 10; i++)  
    {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
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
  
 Aşağıdaki kod nasıl kullanılacağını gösterir **sonu** içinde bir **sırada** döngü ve **yapmak** döngü.  
  
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
  
 Aşağıdaki kod nasıl kullanılacağını gösterir **sonu** switch deyiminde. Kullanmalısınız **sonu** değil kullanırsanız, her durumda ayrı olarak; işlemek isterseniz, her durumda **sonu**, kod yürütme sonraki duruma geçer.  
  
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
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [continue Deyimi](../cpp/continue-statement-cpp.md)