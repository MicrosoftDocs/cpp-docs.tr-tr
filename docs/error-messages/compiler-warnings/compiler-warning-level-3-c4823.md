---
title: Derleyici Uyarısı (Düzey 3) C4823 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4823
dev_langs:
- C++
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c3a6f24a32267f221dbc37e242bae48c0056af5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044658"
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
