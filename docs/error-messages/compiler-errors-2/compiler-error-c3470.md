---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3470'
title: Derleyici hatası C3470
ms.date: 11/04/2016
f1_keywords:
- C3470
helpviewer_keywords:
- C3470
ms.assetid: 170c7a9d-214d-41b1-8f15-d4a4fc38aaa5
ms.openlocfilehash: 1b8310a8bf7f4d69590baeebfc9e49ec01ad9d05
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168442"
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
