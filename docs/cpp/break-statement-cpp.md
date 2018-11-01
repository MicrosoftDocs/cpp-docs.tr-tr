---
title: break Deyimi (C++)
ms.date: 11/04/2016
f1_keywords:
- break_cpp
helpviewer_keywords:
- break keyword [C++]
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
ms.openlocfilehash: 3dda0b19fffaaf725ab363a0c4fe70d2ca54e3f7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662507"
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

## <a name="see-also"></a>Ayrıca bkz.

[Atlama Deyimleri](../cpp/jump-statements-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[continue Deyimi](../cpp/continue-statement-cpp.md)