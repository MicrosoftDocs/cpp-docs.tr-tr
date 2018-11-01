---
title: alignof ve alignas (C++)
ms.date: 11/04/2016
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
ms.openlocfilehash: e5d023d7969764bdd36030a508abdd94068e48b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50493658"
---
# <a name="alignof-and-alignas-c"></a>alignof ve alignas (C++)

**Alignas** tür tanımlayıcısı, değişkenler ve kullanıcı tanımlı türler özel hizalaması belirtmek için bir taşınabilir, C++ standart yoludur. **Alignof** işleci benzer şekilde, belirtilen tür veya değişken hizalamasını elde etmek için standart, taşınabilir bir yoludur.

## <a name="example"></a>Örnek

Kullanabileceğiniz **alignas** büyük/küçük harfi, veya UNION, bir sınıf ya da tek tek üyeleri. Zaman birden çok **alignas** tanımlayıcıları karşılaştı, derleyici en katı bir (en büyük değere sahip olanla) seçersiniz.

```cpp
// alignas_alignof.cpp
// compile with: cl /EHsc alignas_alignof.cpp
#include <iostream>

struct alignas(16) Bar
{
    int i;       // 4 bytes
    int n;      // 4 bytes
    alignas(4) char arr[3];
    short s;          // 2 bytes
};

int main()
{
    std::cout << alignof(Bar) << std::endl; // output: 16
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Hizalama](../cpp/alignment-cpp-declarations.md)