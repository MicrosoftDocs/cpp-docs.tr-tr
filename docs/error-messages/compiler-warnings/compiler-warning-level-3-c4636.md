---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4636'
title: Derleyici Uyarısı (düzey 3) C4636
ms.date: 11/04/2016
f1_keywords:
- C4636
helpviewer_keywords:
- C4636
ms.assetid: 59112a0f-850f-41c6-bd84-8ae8dc84706a
ms.openlocfilehash: 09ba549c4fcd7f48a1a6ed7e1e16bc293c7ad884
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238121"
---
# <a name="compiler-warning-level-3-c4636"></a>Derleyici Uyarısı (düzey 3) C4636

' Yapı ': etikete uygulanan XML belgesi yorumu boş olmayan ' ' özniteliği gerektiriyor.

Bir etiketinin `cref` bir değeri yoktu.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4636 oluşturur.

```cpp
// C4636.cpp
// compile with: /clr /doc /W3 /c
/// <see cref=''/>
// /// <see cref='System::Exception'/>
ref struct A {   // C4636
   void f(int);
};

// OK
/// <see cref='System::Exception'/>
ref struct B {
   void f(int);
};
```
