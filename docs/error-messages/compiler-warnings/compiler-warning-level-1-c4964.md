---
title: Derleyici Uyarısı (düzey 1) C4964
ms.date: 11/04/2016
f1_keywords:
- C4964
helpviewer_keywords:
- C4964
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
ms.openlocfilehash: 556c6e0963fc41d76cd123373cc4cd85edc66962
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492068"
---
# <a name="compiler-warning-level-1-c4964"></a>Derleyici Uyarısı (düzey 1) C4964

İyileştirme seçeneği belirtilmedi; profil bilgileri toplanmayacak değil

[/GL](../../build/reference/gl-whole-program-optimization.md) ve [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) herhangi bir iyileştirme belirtilmiş istendi, böylece .pgc dosyası oluşturulur ve bu nedenle, herhangi bir profil temelli iyileştirme mümkün olacaktır.

.Pgc dosyası, uygulamanızı çalıştırdığınızda oluşturulmasını istiyorsanız, aşağıdakilerden birini belirtin [/O](../../build/reference/o-options-optimize-code.md) derleyici seçenekleri.

Aşağıdaki örnek, C4964 oluşturur:

```
// C4964.cpp
// compile with: /W1 /GL /link /ltcg:pgi
// C4964 expected
// Add /O2, for example, to the command line to resolve this warning.
int main() {
   int i;
}
```