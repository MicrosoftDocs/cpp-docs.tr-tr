---
title: Derleyici hatası C3541
ms.date: 11/04/2016
f1_keywords:
- C3541
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
ms.openlocfilehash: 32926d0ef9343bad9ed73458e4d52d317b628109
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221048"
---
# <a name="compiler-error-c3541"></a>Derleyici hatası C3541

' Type ': TypeId, ' Auto ' içeren bir türe uygulanamaz

Tür belirleyicisi içerdiğinden, belirtilen türe [TypeId](../../extensions/typeid-cpp-component-extensions.md) işleci uygulanamıyor **`auto`** .

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3541 verir.

```cpp
// C3541.cpp
// Compile with /Zc:auto
#include <typeinfo>
int main() {
    auto x = 123;
    typeid(x);    // OK
    typeid(auto); // C3541
    return 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)<br/>
[/Zc: Auto (değişken türünü türet)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[typeid](../../extensions/typeid-cpp-component-extensions.md)
