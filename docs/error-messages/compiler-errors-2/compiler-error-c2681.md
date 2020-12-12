---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2681'
title: Derleyici hatası C2681
ms.date: 11/04/2016
f1_keywords:
- C2681
helpviewer_keywords:
- C2681
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
ms.openlocfilehash: 3b002e6260787e60377d726bcceb6db41fce532a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267787"
---
# <a name="compiler-error-c2681"></a>Derleyici hatası C2681

' Type ': ad için geçersiz ifade türü

Atama işleci geçersiz bir türden dönüştürmeye çalıştı. Örneğin, bir ifadeyi işaretçi türüne dönüştürmek için [dynamic_cast](../../cpp/dynamic-cast-operator.md) işlecini kullanırsanız, kaynak ifade bir işaretçi olmalıdır.

Aşağıdaki örnek C2681 oluşturur:

```cpp
// C2681.cpp
class A { virtual void f(); };

void g(int i) {
    A* pa;
    pa = dynamic_cast<A*>(i);  // C2681
}
```
