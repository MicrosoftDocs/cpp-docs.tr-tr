---
title: Derleyici Hatası C3540
ms.date: 11/04/2016
f1_keywords:
- C3540
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
ms.openlocfilehash: d0c4f1b71ccd12ad39fb25ef3411d2fb46b89da7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665822"
---
# <a name="compiler-error-c3540"></a>Derleyici Hatası C3540

'type': 'auto' içeren bir türe sizeof uygulanamaz

[Sizeof](../../cpp/sizeof-operator.md) işleci içerdiğinden belirtilen türe uygulanamaz `auto` tanımlayıcısı.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3540 verir.

```
// C3540.cpp
// Compile with /Zc:auto
int main() {
    auto x = 123;
    sizeof(x);    // OK
    sizeof(auto); // C3540
    return 0;
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (Değişken Türünü Türet)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[sizeof İşleci](../../cpp/sizeof-operator.md)