---
title: Compiler Warning (level 3) C4521
ms.date: 11/04/2016
f1_keywords:
- C4521
helpviewer_keywords:
- C4521
ms.assetid: 057d770c-ebcf-44cd-b943-1b1bb1ceaa8c
ms.openlocfilehash: 362fd3c14037fa62ab73c928a45eaf7808de66bc
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189357"
---
# <a name="compiler-warning-level-3-c4521"></a>Compiler Warning (level 3) C4521

'class' : multiple copy constructors specified

The class has multiple copy constructors of a single type. This warning is informational; the constructors are callable in your program.

Use the [warning](../../preprocessor/warning.md) pragma to suppress this warning.

## <a name="example"></a>Örnek

The following sample generates C4521.

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