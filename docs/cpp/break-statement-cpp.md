---
title: break Deyimi (C++)
ms.date: 11/04/2016
f1_keywords:
- break_cpp
helpviewer_keywords:
- break keyword [C++]
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
ms.openlocfilehash: 23d31e1456106d5f82c4a13079c72c231b8477bd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190488"
---
# <a name="break-statement-c"></a>break Deyimi (C++)

**Break** ifadesi, göründüğü en yakın kapsayan döngünün veya koşullu deyimin yürütmesini sonlandırır. Denetim, varsa, deyimin sonunu takip eden deyime geçer.

## <a name="syntax"></a>Sözdizimi

```
break;
```

## <a name="remarks"></a>Açıklamalar

**Break** deyimi, koşullu [anahtar](../cpp/switch-statement-cpp.md) ifadesiyle ve [Do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md), ve [while](../cpp/while-statement-cpp.md) Loop deyimleriyle birlikte kullanılır.

**Switch** ifadesinde, **Break** deyimleri programın **Switch** ifadesinin dışında bir sonraki ifadeyi yürütmesine neden olur. **Break** deyimi olmadan, **varsayılan** yan tümcesi dahil olmak üzere, eşleşen **Case** etiketinden **Switch** ifadesinin sonuna kadar her bir deyimi yürütülür.

Döngülerde **Break** ifadesinin en yakın kapsayan **Do**, **for**veya **while** deyimlerinin yürütülmesi sonlanır. Denetim, varsa, sonlandırılmış deyimi takip eden deyime geçirilir.

İç içe geçmiş deyimler içinde, **Break** deyimi yalnızca hemen kendisini kapsayan **Do**, **for**, **Switch**veya **while** deyimini sonlandırır. Daha derin iç içe yapıların denetimini aktarmak için **Return** veya **goto** ifadesini kullanabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki kod, **for** döngüsünde **Break** ifadesinin nasıl kullanılacağını gösterir.

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

Aşağıdaki kod, bir **while** döngüsünde ve **Do** döngüsünde **Break** 'in nasıl kullanılacağını gösterir.

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

Aşağıdaki kod, bir switch ifadesinde **Break** 'in nasıl kullanılacağını gösterir. Her bir durumu ayrı olarak işlemek istiyorsanız, her durumda **Break** kullanmanız gerekir; **Break**kullanmıyorsanız, kod yürütmesi bir sonraki durumda geçer.

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
