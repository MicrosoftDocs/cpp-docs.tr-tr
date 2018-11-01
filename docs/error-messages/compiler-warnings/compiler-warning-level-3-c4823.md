---
title: Derleyici Uyarısı (Düzey 3) C4823
ms.date: 11/04/2016
f1_keywords:
- C4823
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
ms.openlocfilehash: 28d490c341c4d14c2e6c03e13007b5a8be423622
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625926"
---
# <a name="compiler-warning-level-3-c4823"></a>Derleyici Uyarısı (Düzey 3) C4823

'function': kullanır ancak sabitleme işaretçileri geriye doğru izlenen semantik etkin değil. / Eha kullanmayı düşünün

Yönetilen yığındaki bir blok kapsamı içinde bildirilen bir sabitleme işaretçisi tarafından işaret edilen nesneyi çıkarmak için derleyici yerel sınıfların "gibi davranan sabitleme işaretçisi işaretçi nullifies bir yok Edicisi olan" yok ediciler davranışını taklit eder. Bir özel durum sonra bir yok edici bir çağrı etkinleştirmek için nesne geriye doğru izleme, kullanarak bunu etkinleştirmelisiniz [/ehsc](../../build/reference/eh-exception-handling-model.md).

El ile nesne kaldırın ve uyarıyı yok sayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4823 oluşturur.

```
// C4823.cpp
// compile with: /clr /W3 /EHa-
using namespace System;

ref struct G {
   int m;
};

void f(G ^ pG) {
   try {
      pin_ptr<int> p = &pG->m;
      // manually unpin, ignore warning
      // p = nullptr;
      throw gcnew Exception;
   }
   catch(Exception ^) {}
}   // C4823 warning

int main() {
   f( gcnew G );
}
```
