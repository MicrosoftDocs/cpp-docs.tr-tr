---
title: Derleyici Uyarısı (düzey 3) C4522
ms.date: 11/04/2016
f1_keywords:
- C4522
helpviewer_keywords:
- C4522
ms.assetid: 7065dc27-0b6c-4e68-a345-c51cdb99a20b
ms.openlocfilehash: 84f4785c670c4cc5c167c18b9f15c2417b61df34
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188964"
---
# <a name="compiler-warning-level-3-c4522"></a>Derleyici Uyarısı (düzey 3) C4522

' class ': birden çok atama işleci belirtildi

Sınıfta tek bir türün birden çok atama işleci vardır. Bu uyarı bilgilendirme amaçlıdır; oluşturucular, programınızda çağrılabilir.

Bu uyarıyı gizlemek için [Uyarı](../../preprocessor/warning.md) pragmasını kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4522 oluşturur.

```cpp
// C4522.cpp
// compile with: /EHsc /W3
#include <iostream>

using namespace std;
class A {
public:
   A& operator=( A & o ) { cout << "A&" << endl; return *this; }
   A& operator=( const A &co ) { cout << "const A&" << endl; return *this; }   // C4522
};

int main() {
   A o1, o2;
   o2 = o1;
   const A o3;
   o1 = o3;
}
```