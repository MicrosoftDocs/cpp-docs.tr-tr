---
title: Derleyici Hatası C3350
ms.date: 11/04/2016
f1_keywords:
- C3350
helpviewer_keywords:
- C3350
ms.assetid: cfbbc338-92b5-4f34-999e-aa2d2376bc70
ms.openlocfilehash: a19dbde6409afaae29e9110315c7c68fe9d43d62
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300550"
---
# <a name="compiler-error-c3350"></a>Derleyici Hatası C3350

'temsilci': temsilci Oluşturucu sayı bağımsız değişken bekliyor

Bir temsilci örneğini oluştururken, iki bağımsız değişken, temsilci işlevi ve işlev içeren türün örneğini geçmesi gerekir.

Aşağıdaki örnek, C3350 oluşturur:

```
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
