---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3154'
title: Derleyici hatası C3154
ms.date: 11/04/2016
f1_keywords:
- C3154
helpviewer_keywords:
- C3154
ms.assetid: 78005c74-eaaf-4ac2-88ae-6c25d01a302a
ms.openlocfilehash: c43800aba54431041b13e70d9e94c80d98d8ee84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203984"
---
# <a name="compiler-error-c3154"></a>Derleyici hatası C3154

Üç nokta önüne ', ' bekleniyor. Virgülle ayrılmış olmayan üç nokta, parametre dizisi işlevlerinde desteklenmez.

Değişken bağımsız değişken işlevi doğru şekilde bildirilmemiş.

Daha fazla bilgi için bkz. [değişken bağımsız değişken listeleri (...) (C++/CLI)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3154 oluşturur.

```cpp
// C3154.cpp
// compile with: /clr
ref struct R {
   void Func(int ... array<int> ^);   // C3154
   void Func2(int i, ... array<int> ^){}   // OK
   void Func3(array<int> ^){}   // OK
   void Func4(... array<int> ^){}   // OK
};

int main() {
   R ^ r = gcnew R;
   r->Func4(1,2,3);
}
```
