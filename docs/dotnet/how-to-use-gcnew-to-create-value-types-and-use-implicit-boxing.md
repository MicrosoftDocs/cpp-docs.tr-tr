---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: değer türleri oluşturmak için gcnew kullanma ve örtük kutulamayı kullanma'
title: 'Nasıl yapılır: Değer Türleri Oluşturmak için gcnew Kullanma ve Örtük Kutulamayı Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- gcnew keyword [C++], creating value types
- boxing, implicit
- value types, creating
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
ms.openlocfilehash: e58b50be4399cef6a842ce0b02e951617f143e5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210900"
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
