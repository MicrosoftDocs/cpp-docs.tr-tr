---
title: 'Nasıl yapılır: Gcnew değer türleri oluşturmak ve örtük kutulamayı kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- gcnew keyword [C++], creating value types
- boxing, implicit
- value types, creating
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
ms.openlocfilehash: c67f8e0b9511f4ed1610e72e4a7df41c949b1d27
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58770830"
---
# <a name="how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing"></a>Nasıl yapılır: Gcnew değer türleri oluşturmak ve örtük kutulamayı kullanma

Kullanarak [gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md) yönetilen, atık olarak toplanmış yığındaki yerleştirilebilir bir kutulanmış değer türü üzerinde bir değer türü oluşturur.

## <a name="example"></a>Örnek

```
// vcmcppv2_explicit_boxing4.cpp
// compile with: /clr
public value class V {
public:
   int m_i;
   V(int i) : m_i(i) {}
};

public ref struct TC {
   void do_test(V^ v) {
      if (v != nullptr)
         ;
      else
         ;
   }
};

int main() {
   V^ v = gcnew V(42);
   TC^ tc = gcnew TC;
   tc->do_test(v);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Kutulama](../extensions/boxing-cpp-component-extensions.md)
