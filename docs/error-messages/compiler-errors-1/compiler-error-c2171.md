---
title: Derleyici Hatası C2171
ms.date: 11/04/2016
f1_keywords:
- C2171
helpviewer_keywords:
- C2171
ms.assetid: a80343b5-ab3f-4413-b6f1-3ce9d7e519e5
ms.openlocfilehash: 9b51a3793f7ada131ef409ece05b866eb635b9b3
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51325776"
---
# <a name="compiler-error-c2171"></a>Derleyici Hatası C2171

'operator': 'type' türündeki işlenenlerde geçersizdir

Birli işleç bir geçersiz işleç türü ile kullanılır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2171 oluşturur.

```
// C2171.cpp
int main() {
   double d, d1;
   d = ~d1;   // C2171

   // OK
   int d2 = 0, d3 = 0;
   d2 = ~d3;
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2171 oluşturur.

```
// C2171_b.cpp
// compile with: /c
class A {
public:
   A() { STF( &A::D ); }

   void D() {}
   void DTF() {
      (*TF)();   // C2171
      (this->*TF)();   // OK
   }

   void STF(void (A::*fnc)()) {
      TF = fnc;
   }

private:
   void (A::*TF)();
};
```