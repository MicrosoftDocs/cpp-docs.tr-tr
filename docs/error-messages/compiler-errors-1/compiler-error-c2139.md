---
title: Derleyici Hatası C2139
ms.date: 11/04/2016
f1_keywords:
- C2139
helpviewer_keywords:
- C2139
ms.assetid: 31e047c0-5bf9-46c2-b6de-b627ea6a5768
ms.openlocfilehash: f462b7d26e21b9313949bb3968b5b39e81bb30b4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437143"
---
# <a name="compiler-error-c2139"></a>Derleyici Hatası C2139

'type': tanımsız bir sınıfın derleyici iç tür niteliğine 'ayırt edici nitelik' bağımsız değişken olarak geçirilmesine izin verilmez

Bir türü niteliğine için geçersiz bağımsız değişken geçirildi.

Daha fazla bilgi için [tür özellikleri için derleyici desteği](../../windows/compiler-support-for-type-traits-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2139 oluşturur.

```
// C2139.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

template <class T>
struct is_polymorphic {
   static const bool value = __is_polymorphic(T);
};

class C;
class D {};

class E {
public:
   virtual void Test() {}
};

int main() {
   cout << is_polymorphic<C>::value << endl;   // C2139
   cout << is_polymorphic<D>::value << endl;   // OK
   cout << is_polymorphic<E>::value << endl;   // OK
}
```