---
description: 'Daha fazla bilgi edinin: genel türleri kullanma (C++/CLı)'
title: Genel Türleri Kullanma (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- generics [C++], consuming from .NET languages
ms.assetid: e6330ef5-e907-432e-b527-7a22f5899639
ms.openlocfilehash: 3ecfd9f98a8397f96b18ff916bdf9eafe6444a33
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220688"
---
# <a name="consuming-generics-ccli"></a>Genel Türleri Kullanma (C++/CLI)

Bir .NET (veya UWP) dilinde yazılan genel türler, diğer dillerde kullanılabilir. Şablonların aksine, derlenmiş bir derlemede genel hala genel kalır. Bu nedenle, bir diğeri genel türü farklı bir derlemede, hatta genel türün tanımlandığı derlemeden farklı bir dilde örnekleyebilirsiniz.

## <a name="example-generic-class-defined-in-c"></a>Örnek: C 'de tanımlanmış genel sınıf #

### <a name="description"></a>Açıklama

Bu örnek, C# dilinde tanımlanmış bir genel sınıfı gösterir.

### <a name="code"></a>Kod

```csharp
// consuming_generics_from_other_NET_languages.cs
// compile with: /target:library
// a C# program
public class CircularList<ItemType> {
   class ListNode    {
      public ItemType m_item;
      public ListNode next;
      public ListNode(ItemType item) {
         m_item = item;
      }
   }

   ListNode first, last;

   public CircularList() {}

   public void Add(ItemType item) {
      ListNode newnode = new ListNode(item);
      if (first == null) {
         first = last = newnode;
         first.next = newnode;
         last.next = first;
      }
      else {
         newnode.next = first;
         first = newnode;
         last.next = first;
      }
   }

   public void Remove(ItemType item) {
      ListNode iter = first;
      if (first.m_item.Equals( item )) {
         first =
         last.next = first.next;
      }
      for ( ; iter != last ; iter = iter.next )
         if (iter.next.m_item.Equals( item )) {
              if (iter.next == last)
                  last = iter;
              iter.next = iter.next.next;
              return;
          }
   }

   public void PrintAll() {
      ListNode iter = first;
      do {
         System.Console.WriteLine( iter.m_item );
         iter = iter.next;
      } while (iter != last);
   }
}
```

## <a name="example-consume-assembly-authored-in-c"></a>Örnek: C 'de yazılan derlemeyi kullan #

### <a name="description"></a>Açıklama

Bu örnek, C# dilinde yazılan derlemeyi kullanır.

### <a name="code"></a>Kod

```cpp
// consuming_generics_from_other_NET_languages_2.cpp
// compile with: /clr
#using <consuming_generics_from_other_NET_languages.dll>
using namespace System;
class NativeClass {};
ref class MgdClass {};

int main() {
   CircularList<int>^ circ1 = gcnew CircularList<int>();
   CircularList<MgdClass^>^ circ2 = gcnew CircularList<MgdClass^>();

   for (int i = 0 ; i < 100 ; i += 10)
      circ1->Add(i);
   circ1->Remove(50);
   circ1->PrintAll();
}
```

```Output
90
80
70
60
40
30
20
10
```

## <a name="see-also"></a>Ayrıca bkz.

[Genel Türler](generics-cpp-component-extensions.md)
