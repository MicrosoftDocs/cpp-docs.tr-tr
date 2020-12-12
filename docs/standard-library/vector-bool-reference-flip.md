---
description: 'Daha fazla bilgi edinin: vector &lt; bool &gt; :: Reference:: Flip'
title: 'Vector &lt; bool &gt; :: Reference:: Flip'
ms.date: 11/04/2016
f1_keywords:
- vector/std::vector<bool>::reference::flip
helpviewer_keywords:
- reference::flip method
ms.assetid: ef940365-cbe4-4a87-a3e2-1f3cfa357e29
ms.openlocfilehash: fc07fada718e440d6e2ae76c75e7e5b24c6644d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280423"
---
# <a name="vectorltboolgtreferenceflip"></a>Vector &lt; bool &gt; :: Reference:: Flip

Başvurulan [Vector \<bool> ](../standard-library/vector-bool-class.md) öğesinin Boole değerini tersine çevirir.

## <a name="syntax"></a>Syntax

```cpp
void flip();
```

## <a name="example"></a>Örnek

```cpp
// vector_bool_ref_flip.cpp
// compile with: /EHsc /W4
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    cout << boolalpha;

    vector<bool> vb = { true, false, false, true, true };

    cout << "The vector is: " << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;

    vector<bool>::reference vbref = vb.front();
    vbref.flip();

    cout << "The vector with first element flipped is: " << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;
}
```

## <a name="output"></a>Çıktı

```Output
The vector is:
    true false false true true
The vector with first element flipped is:
    false false false true true
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<vector>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Vector \<bool> :: Reference sınıfı](../standard-library/vector-bool-reference-class.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
