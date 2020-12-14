---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2762'
title: Derleyici hatası C2762
ms.date: 11/04/2016
f1_keywords:
- C2762
helpviewer_keywords:
- C2762
ms.assetid: 8b81a801-fd48-40a1-8bee-0748795b12e4
ms.openlocfilehash: 849ed8a0f81edf2bea3af5dd054ad1e402a6896b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239616"
---
# <a name="compiler-error-c2762"></a>Derleyici hatası C2762

' class ': ' Argument ' için şablon bağımsız değişkeni olarak geçersiz ifade

[/Za](../../build/reference/za-ze-disable-language-extensions.md)kullanırken, derleyici bir integrali bir işaretçiye dönüştürmez.

Aşağıdaki örnek C2762 oluşturur:

```cpp
// C2762.cpp
// compile with: /Za
template<typename T, T *pT>
class X2 {};

void f2() {
   X2<int, 0> x21;   // C2762
   // try the following line instead
   // X2<int, static_cast<int *>(0)> x22;
}
```
