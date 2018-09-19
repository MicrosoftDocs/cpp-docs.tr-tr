---
title: Derleyici Hatası C3350 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3350
dev_langs:
- C++
helpviewer_keywords:
- C3350
ms.assetid: cfbbc338-92b5-4f34-999e-aa2d2376bc70
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 809145755242146b1d047947df26551d005ea002
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098468"
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
