---
title: Derleyici Uyarısı (düzey 3) C4521
ms.date: 11/04/2016
f1_keywords:
- C4521
helpviewer_keywords:
- C4521
ms.assetid: 057d770c-ebcf-44cd-b943-1b1bb1ceaa8c
ms.openlocfilehash: 79e0866262b2db18424355de0702288d0f24592d
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74992066"
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
