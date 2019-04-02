---
title: Derleyici Hatası C3541
ms.date: 11/04/2016
f1_keywords:
- C3541
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
ms.openlocfilehash: c56be16504dbdad0c441ad90182fa99ef0445dcf
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772637"
---
# <a name="compiler-error-c3541"></a>Derleyici Hatası C3541

'type': 'auto' içeren bir türe typeid uygulanamaz

[TypeID](../../extensions/typeid-cpp-component-extensions.md) işleci içerdiğinden belirtilen türe uygulanamaz `auto` tanımlayıcısı.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3541 verir.

```
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

## <a name="see-also"></a>Ayrıca Bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (Değişken Türünü Türet)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[typeid](../../extensions/typeid-cpp-component-extensions.md)