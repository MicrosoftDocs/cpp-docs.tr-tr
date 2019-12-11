---
title: Derleyici Uyarısı (düzey 3) C4534
ms.date: 11/04/2016
f1_keywords:
- c4534
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
ms.openlocfilehash: 7d8ff442e84aa7563b1787e5a030297c034e1871
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74992059"
---
# <a name="compiler-warning-level-3-c4534"></a>Derleyici Uyarısı (düzey 3) C4534

Varsayılan bağımsız değişken nedeniyle ' constructor ', ' class ' sınıfı için varsayılan bir Oluşturucu olmayacaktır

Yönetilmeyen bir sınıf, varsayılan değerlere sahip parametrelere sahip bir oluşturucuya sahip olabilir ve derleyici bunu varsayılan oluşturucu olarak kullanır. `value` anahtar sözcüğüyle işaretlenmiş bir sınıf, varsayılan bir Oluşturucu olarak parametreleri için varsayılan değerlere sahip bir Oluşturucu kullanmaz.

Daha fazla bilgi için bkz. [sınıflar ve yapılar](../../extensions/classes-and-structs-cpp-component-extensions.md).

Aşağıdaki örnek C4534 oluşturur:

```cpp
// C4534.cpp
// compile with: /W3 /clr /WX
value class MyClass {
public:
   int ii;
   MyClass(int i = 9) {   // C4534, will not be the default constructor
      i++;
   }
};

int main() {
   MyClass ^ xx = gcnew MyClass;
   xx->ii = 0;
}
```
