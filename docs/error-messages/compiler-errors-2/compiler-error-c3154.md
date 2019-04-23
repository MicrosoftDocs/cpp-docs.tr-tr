---
title: Derleyici Hatası C3154
ms.date: 11/04/2016
f1_keywords:
- C3154
helpviewer_keywords:
- C3154
ms.assetid: 78005c74-eaaf-4ac2-88ae-6c25d01a302a
ms.openlocfilehash: 9f7af4e19fab5f5a0539e9fc3bf9dbeffb5c6fbf
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776294"
---
# <a name="compiler-error-c3154"></a>Derleyici Hatası C3154

Beklenen ',' üç nokta önce. Virgülle ayrılmamış üç nokta parametre dizisi işlevlerinde desteklenmeyen ayrılmış.

Bir değişken bağımsız değişken işlev doğru olarak bildirilmedi.

Daha fazla bilgi için [değişken bağımsız değişken listeleri (...) (C++/CLI) ](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3154 oluşturur.

```
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