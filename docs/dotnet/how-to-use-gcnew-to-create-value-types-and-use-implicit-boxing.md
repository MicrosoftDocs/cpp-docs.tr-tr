---
title: 'Nasıl yapılır: Değer Türleri Oluşturmak için gcnew Kullanma ve Örtük Kutulamayı Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- gcnew keyword [C++], creating value types
- boxing, implicit
- value types, creating
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
ms.openlocfilehash: 891704d24ca7a7bf8724c8e57faa2aef20a7f982
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988140"
---
# <a name="how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing"></a>Nasıl yapılır: Değer Türleri Oluşturmak için gcnew Kullanma ve Örtük Kutulamayı Kullanma

Değer türünde [gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md) kullanılması, paketlenmiş bir değer türü oluşturur ve bu daha sonra yönetilen, atık toplanan yığına yerleştirilecektir.

## <a name="example"></a>Örnek

```cpp
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
