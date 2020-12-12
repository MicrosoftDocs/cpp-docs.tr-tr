---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4823'
title: Derleyici Uyarısı (düzey 3) C4823
ms.date: 11/04/2016
f1_keywords:
- C4823
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
ms.openlocfilehash: b5f4efcf25e59025ad086832c2446d856918542a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332100"
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
