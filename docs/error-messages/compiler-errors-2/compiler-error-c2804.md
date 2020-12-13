---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2804'
title: Derleyici hatası C2804
ms.date: 11/04/2016
f1_keywords:
- C2804
helpviewer_keywords:
- C2804
ms.assetid: b066e563-cca4-450c-8ba7-3b0d7a89f3ea
ms.openlocfilehash: c9281b93a67260e079b72ea70e7febc6a73faff3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339258"
---
# <a name="compiler-error-c2804"></a>Derleyici hatası C2804

ikili ' işleç işleci ' çok fazla parametreye sahip

Aşırı yüklenmiş ikili işleç üye işlevi birden fazla parametreyle tanımlanmış. Türü işlecin kapsayan türü olan bir ikili işleç üye işlevinin ilk işlenen parametresi, ima edilir.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C2804 oluşturur ve nasıl düzeltileceğini gösterir.

```cpp
// C2804.cpp
// compile by using: cl /c /W4 C2804.cpp
class X {
public:
   X& operator+= (const X &left, const X &right);   // C2804
   X& operator+= (const X &right);   // OK - left operand implicitly *this
};

int main() {
   X x, y;
   x += y;   // equivalent to x.operator+=(y)
}
```

Aşağıdaki örnek C2804 oluşturur ve nasıl düzeltileceğini gösterir.

```cpp
// C2804_2.cpp
// compile with: /clr /c
ref struct Y {
   Y^ operator +(Y^ hY, int i);   // C2804
   static Y^ operator +(Y^ hY, int i);   // OK
   Y^ operator +(int i);   // OK
};
```
