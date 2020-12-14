---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3541'
title: Derleyici hatası C3541
ms.date: 11/04/2016
f1_keywords:
- C3541
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
ms.openlocfilehash: b579697de98556aa99077e43d28e6de828741fb5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315172"
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

[auto Anahtar Sözcüğü](../../cpp/auto-cpp.md)<br/>
[/Zc: Auto (değişken türünü türet)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[typeid](../../extensions/typeid-cpp-component-extensions.md)
