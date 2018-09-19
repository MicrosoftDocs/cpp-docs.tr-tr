---
title: Derleyici Hatası C2680 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2680
dev_langs:
- C++
helpviewer_keywords:
- C2680
ms.assetid: d6f7129e-dd17-4661-b680-18d6b925b1cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34a8674dcf16f43482c1e881c6264744be40cb3e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016175"
---
# <a name="compiler-error-c2680"></a>Derleyici Hatası C2680

'type': adı için geçersiz hedef türü

Bir işaretçi veya başvuru olmayan bir türe dönüştürmek bir atama işleci çalıştı. [Dynamic_cast](../../cpp/dynamic-cast-operator.md) işleci yalnızca işaretçiler veya başvurular için kullanılabilir.

Aşağıdaki örnek, C2680 oluşturur:

```
// C2680.cpp
// compile with: /c
class A { virtual void f(); };
class B : public A {};

void g(B b) {
   A a;
   a = dynamic_cast<A>(b);   // C2680  target not a reference type
   a = dynamic_cast<A&>(b);   // OK
}
```

Hedef tanımlanmadığında C2680 da meydana gelebilir:

```
// C2680b.cpp
// compile with: /clr /c
// C2680 expected
using namespace System::Collections;

// Delete the following line to resolve.
ref class A;   // not defined

// Uncomment the following line to resolve.
// ref class A{};

public ref class B : ArrayList {
   property A^ C[int] {
      A^ get(int index) {
         return dynamic_cast<A^>(this->default::get(index));
      }
      void set(int index, A^ value) {
         this->default::set(index, value);
      }
   }
};
```