---
title: Derleyici Uyarısı (düzey 4) C4610
ms.date: 11/04/2016
f1_keywords:
- C4610
helpviewer_keywords:
- C4610
ms.assetid: 23c1a16c-9ca9-4bf6-9911-a72b785560c2
ms.openlocfilehash: 1cf8b9bd3194d03f5cb57a32ac78bfe82962d07c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990682"
---
# <a name="compiler-warning-level-4-c4610"></a>Derleyici Uyarısı (düzey 4) C4610

' class ' nesnesi hiçbir şekilde örneklenemez-Kullanıcı tanımlı Oluşturucu gerekli

Sınıfta Kullanıcı tanımlı veya varsayılan oluşturucu yok. Hiçbir örnekleme yapılmaz. Aşağıdaki örnek C4610 oluşturur:

```cpp
// C4610.cpp
// compile with: /W4
struct A {
   int &j;

   A& A::operator=( const A& );
};   // C4610

/* use this structure definition to resolve the warning
struct B {
   int &k;

   B(int i = 0) : k(i) {
   }

   B& B::operator=( const B& );
} b;
*/

int main() {
}
```
