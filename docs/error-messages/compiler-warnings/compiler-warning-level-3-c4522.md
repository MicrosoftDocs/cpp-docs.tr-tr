---
title: Derleyici Uyarısı (Düzey 3) C4522
ms.date: 11/04/2016
f1_keywords:
- C4522
helpviewer_keywords:
- C4522
ms.assetid: 7065dc27-0b6c-4e68-a345-c51cdb99a20b
ms.openlocfilehash: de163f0a3925b711f2f3437b700f75bbe994b3e7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401910"
---
# <a name="compiler-warning-level-3-c4522"></a>Derleyici Uyarısı (Düzey 3) C4522

'class': belirtilen birden fazla atama işleçleri

Sınıfın tek bir türde birden fazla atama işleci vardır. Bu uyarı, bilgi amaçlıdır; Oluşturucular, programınızda çağrılabilir.

Kullanım [uyarı](../../preprocessor/warning.md) Bu uyarının gösterilmemesi için pragması.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4522 oluşturur.

```
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