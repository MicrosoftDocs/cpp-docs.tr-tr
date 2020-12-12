---
description: 'Hakkında daha fazla bilgi: Derleyici Hatası C2139'
title: Derleyici Hatası C2139
ms.date: 11/04/2016
f1_keywords:
- C2139
helpviewer_keywords:
- C2139
ms.assetid: 31e047c0-5bf9-46c2-b6de-b627ea6a5768
ms.openlocfilehash: 240d1cdd4144e77a31063985a8a1fffb6992196c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323070"
---
# <a name="compiler-error-c2139"></a>Derleyici Hatası C2139

' Type ': tanımsız bir sınıfa, ' nitelik ' derleyici iç tür nitelik bağımsız değişkeni olarak izin verilmez

Nitelik türüne geçersiz bir bağımsız değişken geçirildi.

Daha fazla bilgi için bkz. [tür nitelikleri Için derleyici desteği](../../extensions/compiler-support-for-type-traits-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2139 oluşturur.

```cpp
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
