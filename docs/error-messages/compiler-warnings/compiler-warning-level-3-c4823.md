---
title: Derleyici Uyarısı (düzey 3) C4823
ms.date: 11/04/2016
f1_keywords:
- C4823
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
ms.openlocfilehash: a96877252b0b7699f5e4033f8e695f4d9016a6c9
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541262"
---
# <a name="compiler-warning-level-3-c4823"></a>Derleyici Uyarısı (düzey 3) C4823

' function ': sabitleme işaretçileri kullanır, ancak geriye doğru izleme semantiği etkin değildir. /EHa kullanmayı düşünün

Bir blok kapsamında belirtilen sabitleme işaretçisi tarafından işaret edilen yönetilen yığında bir nesneyi çıkarmak için, derleyici yerel sınıfların yıkıcılarının davranışını taklit eder, "önceden tanımlanmış" sabitleme işaretçisi, işaretçiyi null eden bir yıkıcıya sahiptir. Bir özel durum oluşturduktan sonra bir yıkıcı çağrısını etkinleştirmek için, [/EHsc](../../build/reference/eh-exception-handling-model.md)kullanarak yapabileceğiniz nesne geri sarma özelliğini etkinleştirmeniz gerekir.

Ayrıca, nesneyi el ile de serbest bırakabilirsiniz ve uyarıyı yoksayabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4823 oluşturur.

```cpp
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
