---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4534'
title: Derleyici Uyarısı (düzey 3) C4534
ms.date: 11/04/2016
f1_keywords:
- c4534
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
ms.openlocfilehash: 6a13b27716488fa04f6342da76fdcd32c5635f2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257894"
---
# <a name="compiler-warning-level-3-c4534"></a>Derleyici Uyarısı (düzey 3) C4534

Varsayılan bağımsız değişken nedeniyle ' constructor ', ' class ' sınıfı için varsayılan bir Oluşturucu olmayacaktır

Yönetilmeyen bir sınıf, varsayılan değerlere sahip parametrelere sahip bir oluşturucuya sahip olabilir ve derleyici bunu varsayılan oluşturucu olarak kullanır. Anahtar sözcüğüyle işaretlenmiş bir sınıf, `value` varsayılan bir Oluşturucu olarak parametreleri için varsayılan değerlere sahip bir Oluşturucu kullanmaz.

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
