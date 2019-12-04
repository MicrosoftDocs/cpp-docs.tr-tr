---
title: Derleyici hatası C3541
ms.date: 11/04/2016
f1_keywords:
- C3541
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
ms.openlocfilehash: 1308ff91bcebabc5495b015321494f3457cf2d1e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761510"
---
# <a name="compiler-error-c3541"></a>Derleyici hatası C3541

' Type ': TypeId, ' Auto ' içeren bir türe uygulanamaz

`auto` belirticisini içerdiğinden, [TypeId](../../extensions/typeid-cpp-component-extensions.md) işleci belirtilen türe uygulanamıyor.

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
[/Zc:auto (Değişken Türünü Türet)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[typeid](../../extensions/typeid-cpp-component-extensions.md)
