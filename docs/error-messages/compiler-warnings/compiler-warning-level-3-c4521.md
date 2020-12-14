---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4521'
title: Derleyici Uyarısı (düzey 3) C4521
ms.date: 11/04/2016
f1_keywords:
- C4521
helpviewer_keywords:
- C4521
ms.assetid: 057d770c-ebcf-44cd-b943-1b1bb1ceaa8c
ms.openlocfilehash: ff4f565fb243fb5dd2df165ed5f3e3b1baf40c5a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297414"
---
# <a name="compiler-warning-level-3-c4521"></a>Derleyici Uyarısı (düzey 3) C4521

' class ': birden fazla kopya Oluşturucusu belirtildi

Sınıfta tek bir türün birden fazla kopya Oluşturucusu vardır. Bu uyarı bilgilendirme amaçlıdır; oluşturucular, programınızda çağrılabilir.

Bu uyarıyı gizlemek için [Uyarı](../../preprocessor/warning.md) pragmasını kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4521 oluşturur.

```cpp
// C4521.cpp
// compile with: /EHsc /W3
#include <iostream>

using namespace std;
class A {
public:
   A() { cout << "A's default constructor" << endl; }
   A( A &o ) { cout << "A&" << endl; }
   A( const A &co ) { cout << "const A&" << endl; }   // C4521
};

int main() {
   A o1;         // Calls default constructor.
   A o2( o1 );   // Calls A( A& ).
   const A o3;   // Calls default constructor.
   A o4( o3 );   // Calls A( const A& ).
}
```
