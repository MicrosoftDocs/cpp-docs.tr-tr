---
title: Derleyici hatası C3470
ms.date: 11/04/2016
f1_keywords:
- C3470
helpviewer_keywords:
- C3470
ms.assetid: 170c7a9d-214d-41b1-8f15-d4a4fc38aaa5
ms.openlocfilehash: e9bda55c7a65eb5eec4e1f5104a779a817ad5c36
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760497"
---
# <a name="compiler-error-c3470"></a>Derleyici hatası C3470

' Type ': bir sınıfta hem Dizin Oluşturucu (varsayılan dizinli özellik) hem de operator [] bulunamaz

Bir tür hem Default Indexer hem de operator [] tanımlayamazsınız.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3470 oluşturur

```cpp
// C3470.cpp
// compile with: /clr
using namespace System;

ref class R {
public:
   property int default[int] {
      int get(int i) {
         return i+1;
      }
   }

   int operator[](String^ s) { return Convert::ToInt32(s); }   // C3470
};

int main() {
   R ^ r = gcnew R;
   // return r[9] + r["32"] - 42;
}
```
