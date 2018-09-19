---
title: Derleyici Hatası C3540 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3540
dev_langs:
- C++
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6525812d56a82ce2f5d8cad7a63250c726ce5193
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103281"
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