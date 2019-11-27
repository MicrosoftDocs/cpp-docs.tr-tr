---
title: Derleyici Uyarısı (düzey 3) C4534
ms.date: 11/04/2016
f1_keywords:
- c4534
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
ms.openlocfilehash: 2e617b18f2c7ed3b51d25eb44101629bbadcef9d
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189098"
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