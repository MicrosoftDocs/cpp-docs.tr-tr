---
description: 'Daha fazla bilgi edinin: break deyimleri (C++)'
title: break Deyimi (C++)
ms.date: 11/04/2016
f1_keywords:
- break_cpp
helpviewer_keywords:
- break keyword [C++]
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
ms.openlocfilehash: 13efaf55307f7f1d7decaf7cd0039c84b3141fc9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229580"
---
# <a name="break-statement-c"></a>break Deyimi (C++)

**`break`** İfadesi, göründüğü en yakın kapsayan döngünün veya koşullu deyimin yürütmesini sonlandırır. Denetim, varsa, deyimin sonunu takip eden deyime geçer.

## <a name="syntax"></a>Syntax

```
break;
```

## <a name="remarks"></a>Açıklamalar

**`break`** Deyimi, koşullu [anahtar](../cpp/switch-statement-cpp.md) ifadesiyle ve [Do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md), ve [while](../cpp/while-statement-cpp.md) Loop deyimleriyle birlikte kullanılır.

Bir **`switch`** bildiriminde, ifade, **`break`** programın deyimin dışında bir sonraki ifadeyi yürütmesine neden olur **`switch`** . Deyimi olmadan, **`break`** eşleşen **`case`** etiketten, **`switch`** yan tümcesini de içeren deyimin sonuna kadar her bir deyimi **`default`** yürütülür.

Döngüler ' de, **`break`** ifade en yakın kapsayan **`do`** , **`for`** veya bildiriminin yürütmesini sonlandırır **`while`** . Denetim, varsa, sonlandırılmış deyimi takip eden deyime geçirilir.

İç içe geçmiş deyimler içinde, **`break`** deyimi yalnızca **`do`** **`for`** **`switch`** **`while`** hemen kendisini kapsayan,, veya deyimini sonlandırır. **`return`** **`goto`** Daha derin iç içe yapıların denetimini aktarmak için bir veya ifadesini kullanabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki kod, **`break`** ifadesinin bir döngüde nasıl kullanılacağını gösterir **`for`** .

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

Aşağıdaki kod, **`break`** bir **`while`** döngüde ve döngüsünde nasıl kullanılacağını gösterir **`do`** .

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

Aşağıdaki kod, **`break`** bir switch ifadesinde nasıl kullanılacağını göstermektedir. **`break`** Her bir durumu ayrı olarak işlemek istiyorsanız, her durumda kullanmanız gerekir; kullanmıyorsanız **`break`** , kod yürütmesi bir sonraki durumda geçer.

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
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[Continue bildirisi](../cpp/continue-statement-cpp.md)
