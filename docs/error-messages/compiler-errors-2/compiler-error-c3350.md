---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3350'
title: Derleyici hatası C3350
ms.date: 11/04/2016
f1_keywords:
- C3350
helpviewer_keywords:
- C3350
ms.assetid: cfbbc338-92b5-4f34-999e-aa2d2376bc70
ms.openlocfilehash: edda71fdf8f1160d17099a7cee228a053ddd881b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326020"
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
