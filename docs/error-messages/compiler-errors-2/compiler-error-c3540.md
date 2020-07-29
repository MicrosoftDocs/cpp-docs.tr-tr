---
title: Derleyici hatası C3540
ms.date: 11/04/2016
f1_keywords:
- C3540
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
ms.openlocfilehash: a041961e8a91832be67d8def8f2a6a3ef70906d9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223401"
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

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)<br/>
[/Zc: Auto (değişken türünü türet)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[sizeof Işleci](../../cpp/sizeof-operator.md)
