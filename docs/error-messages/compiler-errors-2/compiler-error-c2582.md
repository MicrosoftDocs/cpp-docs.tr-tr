---
title: Derleyici Hatası C2582
ms.date: 11/04/2016
f1_keywords:
- C2582
helpviewer_keywords:
- C2582
ms.assetid: ee1b9378-8bcd-4792-b87e-6d7a466d29ed
ms.openlocfilehash: 2becaf3cf955a9ed8dbbc22cbf11728bcc5bec34
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521283"
---
# <a name="compiler-error-c2582"></a>Derleyici Hatası C2582

'function' işlevi, 'type' içinde kullanılamıyor

Atama işleci sahip olmayan bir nesneye atamak için girişimde bulunuldu.

Aşağıdaki örnek, C2582 oluşturur:

```
// C2582.cpp
// compile with: /clr
using namespace System;

struct N {};
ref struct O {};
ref struct R {
   property O prop;   // C2582
   property O ^ prop2;   // OK
};

int main() {
   String ^ st1 = gcnew String("");
   ^st1 = gcnew String("");   // C2582
   st1 = "xxx";   // OK
}
```