---
title: 'vektör&lt;bool&gt;:: reference::flip'
ms.date: 11/04/2016
f1_keywords:
- vector/std::vector<bool>::reference::flip
helpviewer_keywords:
- reference::flip method
ms.assetid: ef940365-cbe4-4a87-a3e2-1f3cfa357e29
ms.openlocfilehash: 68172de6e50a599d5b1822b83787be3a3a94e037
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62205131"
---
# <a name="vectorltboolgtreferenceflip"></a>vektör&lt;bool&gt;:: reference::flip

Başvurulan bir Boolean değerini tersine çevirir [vektör\<bool >](../standard-library/vector-bool-class.md) öğesi.

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

**Başlık:** \<vektör >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[vektör\<bool >:: reference sınıfı](../standard-library/vector-bool-reference-class.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
