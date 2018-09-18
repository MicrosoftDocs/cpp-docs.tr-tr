---
title: Derleyici Uyarısı (Düzey 3) C4534 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- c4534
dev_langs:
- C++
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad85a6b9dff1715cbdce9738608f26c8680319d0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099817"
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