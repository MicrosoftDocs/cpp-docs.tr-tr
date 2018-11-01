---
title: Derleyici Uyarısı (Düzey 3) C4534
ms.date: 11/04/2016
f1_keywords:
- c4534
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
ms.openlocfilehash: a2af04502082f7fb30d59af5e6434161227c6d30
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437283"
---
# <a name="compiler-warning-level-3-c4534"></a>Derleyici Uyarısı (Düzey 3) C4534

'Oluşturucu' sınıfı 'class' nedeniyle varsayılan bağımsız değişken için bir varsayılan oluşturucu olmayacaktır.

Yönetilmeyen bir sınıf oluşturucu varsayılan değerlere sahip parametrelere sahip olabilir ve derleyicinin bu varsayılan oluşturucu olarak kullanır. Bir sınıf ile işaretlenen `value` anahtar sözcüğü kullanmaz bir oluşturucu varsayılan değerlerle parametreleri için bir varsayılan oluşturucu olarak.

Daha fazla bilgi için [sınıfları ve yapıları](../../windows/classes-and-structs-cpp-component-extensions.md).

Aşağıdaki örnek, C4534 oluşturur:

```
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