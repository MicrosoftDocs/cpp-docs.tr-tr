---
title: 'Vector&lt;bool&gt;:: Reference:: Flip'
ms.date: 11/04/2016
f1_keywords:
- vector/std::vector<bool>::reference::flip
helpviewer_keywords:
- reference::flip method
ms.assetid: ef940365-cbe4-4a87-a3e2-1f3cfa357e29
ms.openlocfilehash: 1743df7773d577e53f054fa4e403cf0d00da8ce7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452167"
---
# <a name="vectorltboolgtreferenceflip"></a>Vector&lt;bool&gt;:: Reference:: Flip

Başvurulan [\<vector bool >](../standard-library/vector-bool-class.md) öğesinin Boole değerini tersine çevirir.

## <a name="syntax"></a>Sözdizimi

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

## <a name="output"></a>Çıkış

```Output
The vector is:
    true false false true true
The vector with first element flipped is:
    false false false true true
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<vektör >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Vector\<bool >:: Reference sınıfı](../standard-library/vector-bool-reference-class.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
