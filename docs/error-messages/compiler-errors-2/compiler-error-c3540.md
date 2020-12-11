---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3540'
title: Derleyici hatası C3540
ms.date: 11/04/2016
f1_keywords:
- C3540
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
ms.openlocfilehash: 85106061b2631d3a392b05a50c49f24566cdd4cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112459"
---
# <a name="compiler-error-c3540"></a>Derleyici hatası C3540

' Type ': sizeof ' Auto ' içeren bir türe uygulanamaz

Tür belirleyicisi içerdiğinden, belirtilen türe [sizeof](../../cpp/sizeof-operator.md) işleci uygulanamıyor **`auto`** .

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3540 verir.

```cpp
// C3540.cpp
// Compile with /Zc:auto
int main() {
    auto x = 123;
    sizeof(x);    // OK
    sizeof(auto); // C3540
    return 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-cpp.md)<br/>
[/Zc: Auto (değişken türünü türet)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[sizeof Işleci](../../cpp/sizeof-operator.md)
