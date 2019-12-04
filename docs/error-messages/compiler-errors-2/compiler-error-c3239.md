---
title: Derleyici hatası C3239
ms.date: 11/04/2016
f1_keywords:
- C3239
helpviewer_keywords:
- C3239
ms.assetid: 22a518b7-020f-4f3c-9963-a094667fd1ac
ms.openlocfilehash: e3143714ff0080ff6890f4afb72521d212e31a4e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756407"
---
# <a name="compiler-error-c3239"></a>Derleyici hatası C3239

' Type ': iç/sabitleme işaretçisine yönelik işaretçiye ortak dil çalışma zamanı tarafından izin verilmiyor

Derleyici geçersiz bir türle karşılaştı.

Aşağıdaki örnek C3229 oluşturur:

```cpp
// C3239.cpp
// compile with: /clr
int main() {
   interior_ptr<int>* pip0;   // C3239

   // OK
   int * pip1;
   interior_ptr<int> pip2;
   int ** pip;
}
```
