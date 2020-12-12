---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4947'
title: Derleyici Uyarısı (düzey 1) C4947
ms.date: 11/04/2016
f1_keywords:
- C4947
helpviewer_keywords:
- C4947
ms.assetid: 5a1d484e-b4c7-4de2-a145-d8dcfc2fc1d2
ms.openlocfilehash: ff7cd472b5059df919ed294457589c326affd2b7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327982"
---
# <a name="compiler-warning-level-1-c4947"></a>Derleyici Uyarısı (düzey 1) C4947

' type_or_member ': eski olarak işaretlendi

Bir üye veya tür, sınıfıyla kullanım dışı olarak işaretlendi <xref:System.ObsoleteAttribute> .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4947 oluşturur:

```cpp
// C4947.cpp
// compile with: /clr /W1
// C4947 expected
using namespace System;

[System::ObsoleteAttribute]
ref struct S {
   [System::ObsoleteAttribute]
   int i;

   [System::ObsoleteAttribute]
   void mFunc(){}
};

// Any reference to Func1 should generate a warning
[System::ObsoleteAttribute]
Int32 Func1(Int32 a, Int32 b) {
   return (a + b);
}

// Any reference to Func2 should generate a warning with  message
[System::ObsoleteAttribute("Will be removed in next version")]
Int32 Func2(Int32 a, Int32 b) {
   return (a + b);
}

int main() {
   Int32 MyInt1 = ::Func1(2, 2);
   Int32 MyInt2 = ::Func2(2, 2);

   S^ s = gcnew S();
   s->i = 10;
   s->mFunc();
}
```
