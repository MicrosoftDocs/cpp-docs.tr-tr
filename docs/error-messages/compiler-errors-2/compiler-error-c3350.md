---
title: Derleyici hatası C3350
ms.date: 11/04/2016
f1_keywords:
- C3350
helpviewer_keywords:
- C3350
ms.assetid: cfbbc338-92b5-4f34-999e-aa2d2376bc70
ms.openlocfilehash: 39d4b4c1cef0febe8845db3e74799b2d240dbdb3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736964"
---
# <a name="compiler-error-c3350"></a>Derleyici hatası C3350

' Delegate ': bir temsilci Oluşturucu, sayı bağımsız değişkeni bekliyor

Temsilcinin bir örneğini oluşturduğunuzda, iki bağımsız değişken geçirmeniz gerekir, temsilci işlevini içeren türün bir örneği ve işlevi.

Aşağıdaki örnek C3350 oluşturur:

```cpp
// C3350.cpp
// compile with: /clr
delegate void SumDelegate();

public ref class X {
public:
   void F() {}
   static void F2() {}
};

int main() {
   X ^ MyX = gcnew X();
   SumDelegate ^ pSD = gcnew SumDelegate();   // C3350
   SumDelegate ^ pSD1 = gcnew SumDelegate(MyX, &X::F);
   SumDelegate ^ pSD2 = gcnew SumDelegate(&X::F2);
}
```
